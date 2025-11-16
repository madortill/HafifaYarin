<template>
  <div id="DefinitionPage" class="definition-page">
    <div class="definition-text">
      אסטרואיד הוא יצור מרושע שמטרתו להשמיד את כדור הארץ ואנחנו בברוגז איתו,
      ממש. הוא נראה כמו כדור עגול כזה אבל לא חלק כי יש לו בליטות ממש מכוערות
      שנראות כמו חצ'קונים.
    </div>
    <img
      src="/src/assets/media/Artboard36.svg"
      alt="astroid"
      class="over-image"
    />
  </div>
</template>

<script>
export default {
  name: "definition-page",
  data() {
    return {};
  },
};
</script>

<style scoped>
.definition-page {
  background-image: url("../assets/media/background.svg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  width: 402px;
  height: 91vh;
  margin: 0;
  padding: 0;
  overflow: hidden;
}

.definition-text {
  display: flex;
  flex-wrap: wrap;
  background-color: #fffff6;
  border-radius: 10%;
  height: 12rem;
  width: 15rem;
  margin-top: 10rem;
  margin-left: 5rem;
  font-size: 1.8rem;
  font-family: "karantina-light";
  color: black;
  direction: rtl;
  line-height: 2rem;
  padding-right: 1rem;
}

.over-image {
  display: flex;
  margin-top: 3rem;
  margin-left: 50%;
  transform: translateX(-50%);
  width: 13rem;
  z-index: 10;
}
</style>
