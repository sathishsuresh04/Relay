<template>
  <div :class="['wrapper', background]" id="register-view">
    <ExitBtn class="exit" />
    <CreateAccount v-if="this.$store.state.register.show.createAccount" class="register" />
    <LenderProfileCreation
      v-if="this.$store.state.register.show.lenderProfileCreation"
      class="createAccount"
    />
    <LenderTeams v-if="this.$store.state.register.show.lenderTeams" class="lenderTeams" />
    <LenderSign v-if="this.$store.state.register.show.lenderSign" class="lenderSign" />
    <RegisterCompleted
      v-if="this.$store.state.register.show.registerCompleted"
      class="registerCompleted"
    />
  </div>
</template>

<script>
import ExitBtn from "../components/buttons/exitBtn";
import CreateAccount from "../components/register/createAccount";
import LenderProfileCreation from "../components/register/lenderProfileCreation";
import LenderTeams from "../components/register/lenderTeams";
import LenderSign from "../components/register/lenderSign";
import RegisterCompleted from "../components/register/registerCompleted";

export default {
  components: {
    ExitBtn,
    CreateAccount,
    LenderProfileCreation,
    LenderTeams,
    LenderSign,
    RegisterCompleted
  },
  data: () => {
    return {
      CreateAccount: false
    };
  },
  computed: {
    background() {
      if (this.$store.state.register.show.registerCompleted === true)
        return "background";
    }
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

  .registerCompleted {
    width: 32rem;
    height: 50rem;
    align-self: center;
    background: none;
  }
}

.background {
  background: $white;
}
</style>