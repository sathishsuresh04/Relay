<template>
  <div class="wrapper">
    <section class="headline">
      <h2>Lender - Profile creation</h2>
      <p class>Welcome!</p>
    </section>

    <section class="registerForm">
      <label for="name">Your name</label>
      <input
        v-model="name"
        type="text"
        name="name"
        placeholder="Firstname Lastname"
        class="registerInput"
      />

      <label for="company">Your company</label>
      <input
        v-model="company"
        type="text"
        name="company"
        placeholder="company name"
        class="registerInput"
      />
      <label for="role">Role</label>
      <select v-model="role" name="role" id="role" class="registerInput">
        <option value>CEO/ Owner</option>
        <option value>CEO</option>
        <option value>Owner</option>
        <option value>Other</option>
        <option value>Other</option>
      </select>

      <label for="location">Location/ Workplace</label>
      <input
        v-model="location"
        type="text"
        name="location"
        placeholder="Online"
        class="registerInput"
      />
      <label for="name">Your name</label>
      <input
        v-model="name"
        type="text"
        name="name"
        placeholder="Firstname Lastname"
        class="registerInput"
      />
      <label for="sector">Sector</label>
      <input
        v-model="sector"
        type="text"
        name="sector"
        placeholder="Data/ It"
        class="registerInput"
      />
      <label for="linkedin">Company linkedin profile</label>
      <input
        v-model="linkedin"
        type="text"
        name="linkedin"
        placeholder="www.linkedin.com/company/ab"
        class="registerInput"
      />
    </section>
    <RegisterButton @click="gotonextstep" :buttonText="buttonText" />
    <img src="../../assets/graphics/progress-1.svg" alt="step 1">
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
      buttonText: "save & move to next step"
    };
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
  justify-content: space-around;
  color: $white;
  margin: auto 0 4rem 0;

  .headline {
    display: flex;
    flex-direction: column;
    align-items: center;
    align-self: center;
    width: 40rem;
    a {
      font-size: $primary;
      font-weight: 600;
      text-decoration: underline;
    }
  }

  .registerForm {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
margin: 2.4rem 0;
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

      img {
    margin-top: auto;
  }
}
</style>