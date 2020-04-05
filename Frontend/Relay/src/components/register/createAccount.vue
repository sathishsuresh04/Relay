<template>
  <div class="wrapper">
    <section class="headline">
      <h2>Create an account</h2>
      <p class>
        Already have an account?
        <a>Sign in here</a>
      </p>
    </section>
    <section class="accountChoice">
      <p class="small">I am a</p>
      <button @click="lender" :class="['accountChoiceBtn']">Lender and i have staff</button>
      <button @click="renter" :class="['accountChoiceBtn']">Renter and i need staff</button>
    </section>
    <section class="registerForm">
      <label for="email">Your e-mail</label>
      <input v-model="email" type="email" name="email" placeholder="email" class="registerInput" />

      <label for="password">Password</label>
      <input
        v-model="password"
        type="password"
        name="password"
        placeholder="password"
        class="registerInput"
      />
    </section>
    <RegisterButton @click="signUp" :buttonText="buttonText" />
  </div>
</template>

<script>
import RegisterButton from "../buttons/registerButton";

export default {
  components: {
    RegisterButton
  },
  data: () => {
    return {
      buttonText: "create my account",
      selected: "",
      email: "",
      password: "",
    };
  },
  methods: {
    signUp() {
      const user = {
        selected: this.selected,
        email: this.email,
        password: this.password
      };

      if (
        this.selected.length > 1 &&
        this.password.length > 6 &&
        this.email.includes("@")
      ) {
        // Action in store goes here or implement ...map if you like
        //  this.$store.dispatch("registerAPI", user)
      }
    },
    lender() {
      this.selected = "lender";
    },
    renter() {
      this.selected = "renter";
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../../assets/scss/variables.scss";
@import "../../assets/scss/buttons.scss";
@import "../../assets/scss/fontStyles.scss";

.wrapper {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  color: $white;


  .headline {
    display: flex;
    flex-direction: column;
    align-items: center;
    a {
      font-size: $primary;
      font-weight: 600;
      text-decoration: underline;
    }
  }

  .accountChoice {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 16rem;
  }

  .registerForm {
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    label {
      color: $pink;
      font-size: $small;
      text-transform: uppercase;
    }

    .registerInput {
      border: none;
      border-bottom: 2px solid $white;
      background: none;
      margin-bottom: 1.6rem;
      padding: 1rem 0 0.3rem 0;
      font-size: $primary;
      color: $white;
    }

    .registerInput::placeholder {
      color: $white;
      font-size: $primary;
      font-weight: 500;
    }
  }
}
</style>