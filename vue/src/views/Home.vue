<template>
  <div class="mainDiv">
    <div class="subDiv">
      <span class="wiseText">Wise</span>
      <span class="goatText">Goat</span>
      <router-link to="/advice" tag="button" class="btn">Pedir conselho</router-link>
    </div>
    <img class="wiseGoat" alt="A nice bode" width="30%" src="@/assets/bodezinho.png" />
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
};
</script>

<style>
.wiseGoat {
  animation: floatingGoat 2s infinite;
  animation-direction: alternate;
}

@keyframes floatingGoat {
  100% {
    transform: translateY(-5%);
    top: 100%;
  }
}
.mainDiv {
  display: flex;
  justify-content: center;
  align-items: center;
}
.subDiv {
  margin-right: 96px;
  display: flex;
  flex-direction: column;
  text-align: start;
  /* flex-grow: 1 */
}
.wiseText {
  color: #baa193;
  font-weight: 700;
  font-size: 48px;
  padding: 0px;
}
.goatText {
  color: #72005f;
  font-weight: 700;
  font-size: 108px;
  padding: 0px;
}
.btn {
  border-radius: 16px;
  border: #72005f;
  background: #72005f;
  color: white;
  font-size: 32px;
  font-weight: 700;
  padding: 16px 36px 16px 36px;
  margin-top: 36px;
}
.btn:active {
  border: #4f0042;
  background: #4f0042;
}
</style>