
<template>
    <div class="matrix">
     
      <div
        v-for="(cell, displayIndex) in reversedCells"
        :key="displayIndex"
        class="matrix-cell"
      >
        <img
          v-if="playerPosition === cell"
          src="@/assets/media/חייל.png"
          class="player"
        />
  
        <img
          v-if="images[cell]"
          :src="images[cell]"
          class="cell-image"
        />
      </div>
  
      
      <div v-if="showPopup" class="popup">
        <div class="popup-content">
          <img :src="popupImage" class="popup-image" />
          <p class="popup-question">{{ currentQuestion.question }}</p>
          <div class="popup-buttons">
            <button
              v-for="(answer, index) in currentQuestion.answers"
              :key="index"
              @click="handleAnswer(answer)"
              :class="{
                correct: selectedAnswer === answer && answer === currentQuestion.correct,
                wrong: selectedAnswer === answer && answer !== currentQuestion.correct
                }"
              >
               {{ answer }}
            </button>
          </div>
        </div>
      </div>
  
      
      <div class="controls">
        <img src="@/assets/media/joystick.png" class="arrow-pad" />
        <div class="arrow-overlay up" @click="move('up')"></div>
        <div class="arrow-overlay down" @click="move('down')"></div>
        <div class="arrow-overlay left" @click="move('right')"></div>
        <div class="arrow-overlay right" @click="move('left')"></div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "GameMatrix",
    data() {
      return {
        rows: 6,
        cols: 4,
        playerPosition: 0,
        showPopup: false,
        popupImage: "",
        currentItemPosition: null,
        currentQuestion: {},
        selectedAnswer: null,
        images: {
          6: "/media/קסדה.png",
          8: "/media/חליפה.png",
          19: "/media/בלון.png",
          23: "/media/אסטרונאוט.png",
        },
        itemNames: {
          6: "קסדה",
          8: "חליפת חלל",
          19: "בלון חמצן",
          23: "אסטרונאוט חדש!",
        },
        trivia: {
          6: {
            question: "מהו אסטרואיד",
            answers: ["כדור דיסקו שחור שרוף בחלל", "כדור לבן גדול בחלל", "אסטרואיד הוא יצור מרושע שמטרתו להשמיד את כדור הארץ ואנחנו בברוגז איתו, ממש.   הוא נראה כמו כדור עגול כזה אבל לא חלק כי יש לו בליטות ממש מכוערות שנראות כמו חצ'קונים"],
            correct: "אסטרואיד הוא יצור מרושע שמטרתו להשמיד את כדור הארץ ואנחנו בברוגז איתו, ממש.   הוא נראה כמו כדור עגול כזה אבל לא חלק כי יש לו בליטות ממש מכוערות שנראות כמו חצ'קונים"
          },
          8: {
            question: "כמה סוגי אסטרואידים יש?",
            answers: ["3- בייבי מתבגר ובוגר - כל אחד מהם הרסני במידה שונה ואף יכול להשמיד את כדור הארץ כולו", "2 - בייבי ובוגר - הרסניים במידות שונות ", "3 - בייבי, מתבגר ובוגר - כולם הרסנייים באותה מידה "],
            correct: "3- בייבי מתבגר ובוגר - כל אחד מהם הרסני במידה שונה ואף יכול להשמיד את כדור הארץ כולו",
          },
          19: {
            question: "איך מפוצצים אסטרואיד?",
            answers: ["לירות על אוטומט" ,  
            "1. חישוב קואורדינטות מיקום האסטרואיד לפי תחנת השיגור 2. 3. לחכות שיתקרב האסטרואיד לירות ולפוצץ את האסטרואיד",
            "1. חישוב קואורדינטות מיקום האסטרואיד לפי תחנת השיגור 2. לכוון את משגר הפצצות לכיוון האסטרואיד 3. לירות ולפוצץ את האסטרואיד"],
            correct: "1. חישוב קואורדינטות מיקום האסטרואיד לפי תחנת השיגור 2. לכוון את משגר הפצצות לכיוון האסטרואיד 3. לירות ולפוצץ את האסטרואיד",
          },
          23: { 

          }
        },
      };
    },
    computed: {
      totalCells() {
        return this.rows * this.cols;
      },
      reversedCells() {
        return Array.from({ length: this.totalCells }, (_, i) => this.totalCells - 1 - i);
      },
    },
    methods: {
      move(direction) {
       
        if (this.showPopup) return;
  
        let newPosition = this.playerPosition;
  
        switch (direction) {
          case "up":
            if (newPosition + this.cols < this.totalCells) newPosition += this.cols;
            break;
          case "down":
            if (newPosition - this.cols >= 0) newPosition -= this.cols;
            break;
          case "left":
            if (newPosition % this.cols !== this.cols - 1) newPosition++;
            break;
          case "right":
            if (newPosition % this.cols !== 0) newPosition--;
            break;
        }
  
        this.playerPosition = newPosition;
  
        
        if (this.images[this.playerPosition]) {
          this.openTriviaPopup(this.playerPosition);
        }
      },
  
      openTriviaPopup(position) {
        this.popupImage = this.images[position];
        this.currentItemPosition = position;
        this.currentQuestion = this.trivia[position];
        this.showPopup = true;
      },
  
      handleAnswer(answer) {
        this.selectedAnswer = answer;
        setTimeout(() => {
          delete this.images[this.currentItemPosition];
          this.$emit("collect-item");

          this.showPopup = false;
          this.selectedAnswer = null;
          this.currentItemPosition = null;
        }, 600);
      
      },
    },
  };
  </script>
  
  <style scoped>
  .matrix {
    position: relative;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(6, 1fr);
    gap: 0%;
    width: 80vw;
    height: 55vh;
    top: 12vh;
    left: 10vw;
    background-color: #f4a460;
    border: 0.5ch solid #000;
    direction: rtl;
  }
  
  .matrix-cell {
    border: 0.2vw solid black;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .cell-image {
    width: 60%;
    height: 70%;
  }
  
  .player {
    width: 50%;
    height: auto;
  }
  
  .popup {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .popup-content {
    background: #fffff6;
    border-radius: 1ch;
    padding: 2ch;
    text-align: center;
    font-family: "karantina-bold";
    font-size: 2rem;
    color: black;
    animation: pop 0.3s ease;
    width: 100%;
    height: 98%;
    
  }
  
  .popup-image {
    width: 6vw;
    height: auto;
    margin-bottom: 1ch;
  }
  
  .popup-question {
    font-size: 1.6rem;
    margin-bottom: 1ch;
  }
  
  .popup-buttons {
    margin-top: 1rem;
    display: flex;
    flex-direction: column;
    gap: 0.8ch;
  }
  
  .popup-buttons button {
    background-color: #f4a460;
    border: 2px solid black;
    border-radius: 0.7ch;
    padding: 0.5ch 1.5ch;
    font-size: 1.2rem;
    cursor: pointer;
    transition: 0.2s;
  }
  
  .popup-buttons button:hover {
    transform: scale(1.1);
    background-color: #ffd48a;
  }

  .popup-buttons button.correct {
    background-color: #21ad0f !important;
    transform: scale(1.1);
  }

  .popup-buttons button.wrong {
    border-color: #dd3416 !important;
    color: white;
    transform: scale(1.1);
  }

  
  @keyframes pop {
    0% {
      transform: scale(0.7);
    }
    100% {
      transform: scale(1);
    }
  }
  
  .controls {
    position: absolute;
    bottom: -18vh;
    left: 70vw;
    transform: translateX(-50%);
    width: 10vh;
    height: 10vh;
  }
  
  .arrow-pad {
    width: 100%;
    height: 100%;
    object-fit: contain;
    pointer-events: none;
    opacity: 0.9;
  }
  
  .arrow-overlay {
    position: absolute;
    width: 33%;
    height: 33%;
  }
  
  .up {
    top: 0;
    left: 33%;
  }
  
  .down {
    bottom: 0;
    left: 33%;
  }
  
  .left {
    top: 33%;
    left: 0;
  }
  
  .right {
    top: 33%;
    right: 0;
  }
  </style>