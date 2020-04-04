<template>
  <div class="wrapper">
    <ExitBtn class="exit" />
    <CreateAccount class="registerForm" />
  </div>
</template>

<script>
import ExitBtn from "../components/buttons/exitBtn";
import CreateAccount from "../components/register/createAccount";

export default {
  components: {
    ExitBtn,
    CreateAccount
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/variables.scss";
@import "../assets/scss/buttons.scss";
@import "../assets/scss/fontStyles.scss";

.wrapper {
  background: $darkBlue;
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;

  .exit {
    display: flex;
    justify-content: flex-end;
  }

  .registerForm {
    width: 32rem;
    height: 62rem;
    align-self: center;
  }
}
</style>