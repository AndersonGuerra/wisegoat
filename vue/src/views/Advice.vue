<template>
  <div>
    <div class="subDiv" @click="goHome">
      <span class="wiseText">Wise</span>
      <span class="goatText">Goat</span>
    </div>
    <div style="display: flex; justify-content: center; margin-top: 44px">
      <div style="display: flex; width: 800px">
        <div class="quote">
          <span class="goatQuote">"{{advice}}"</span>
          <span class="goatCredit">- A nice bode</span>
        </div>
        <div>
          <img class="img" src="http://placegoat.com/300/300" alt="A nice bode" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data: () => ({
    advice: "",
  }),
  async created() {
    let result = await axios.get("https://api.adviceslip.com/advice");
    this.advice = result.data.slip.advice;
  },
  methods: {
    goHome() {
      this.$router.push("/");
    },
  },
};
</script>
<style>
.subDiv {
  cursor: pointer;
}
.wiseText {
  color: #baa193;
  font-weight: 700;
  font-size: 24px;
  padding: 0px;
}
.goatText {
  color: #72005f;
  font-weight: 700;
  font-size: 54px;
  padding: 0px;
}
.quote {
  padding-left: 36px;
  padding-right: 36px;
  background: #ece4e1;
  display: flex;
  flex-direction: column;
  height: 300px;
  justify-content: center;
  border-bottom-left-radius: 8px;
  border-top-left-radius: 8px;
}
.goatQuote {
  color: #72005f;
  font-weight: 700;
  font-size: 36px;
}
.goatCredit {
  color: #baa193;
}
.img {
  border-bottom-right-radius: 8px;
  border-top-right-radius: 8px;
}
</style>