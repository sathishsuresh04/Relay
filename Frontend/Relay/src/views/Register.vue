<template>
  <div class="wrapper">
    <ExitBtn class="exit" />
    <CreateAccount v-if="this.$store.state.register.show.createAccount" class="register" />
    <LenderProfileCreation v-if="this.$store.state.register.show.lenderProfileCreation" class="createAccount" />
    <LenderTeams v-if="this.$store.state.register.show.lenderTeams" class="lenderTeams" />
    <LenderSign v-if="this.$store.state.register.show.lenderSign" class="lenderSign" />
  </div>
</template>

<script>
import ExitBtn from "../components/buttons/exitBtn";
import CreateAccount from "../components/register/createAccount";
import LenderProfileCreation from "../components/register/lenderProfileCreation";
import LenderTeams from "../components/register/lenderTeams";
import LenderSign from "../components/register/lenderSign";

export default {
  components: {
    ExitBtn,
    CreateAccount,
    LenderProfileCreation,
    LenderTeams,
    LenderSign
  },
  data: () => {
    return {
      CreateAccount: false
    };
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

  .register {
    width: 32rem;
    height: 60rem;
    align-self: center;
  }

  .createAccount {
    width: 32rem;
    height: 72rem;
    align-self: center;
  }

  .lenderTeams {
    width: 32rem;
    height: 72rem;
    align-self: center;
  }

  .lenderSign {
        width: 32rem;
    height: 72rem;
    align-self: center;

  }
}
</style>