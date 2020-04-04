<template>
  <div class="wrapper">
    <section class="headline">
      <h2>Lender - Teams</h2>
      <p class>Tell us about your workforce</p>
    </section>

    <section class="registerForm">
      <label for="name">Name team</label>
      <input v-model="name" type="text" name="name" placeholder="team name" class="registerInput" />

      <label for="skillset">Skillset</label>
      <input
        v-model="skillset"
        type="text"
        name="skillset"
        placeholder="skillset"
        class="registerInput"
      />

      <label for="location">Location/ workplace</label>
      <input
        v-model="location"
        type="text"
        name="location"
        placeholder="Online or specify city"
        class="registerInput"
      />
      <label for="number">Number in team</label>
      <input
        v-model="teamNumber"
        type="text"
        name="number"
        placeholder="number available"
        class="registerInput"
      />
      <label for="cost">Av cost per team member</label>
      <input
        v-model="cost"
        type="text"
        name="cost"
        placeholder="rounded to nearest 1000sek"
        class="registerInput"
      />
    </section>
    <div class="addTeam">
      <button class="add">
        <img src="../../assets/graphics/add.svg" alt="+" /> add another team
      </button>
    </div>
    <RegisterButton :buttonText="buttonText" />
        <p class="previousStep">Go back to previous step</p>
    <img src="../../assets/graphics/progress-2.svg" alt="step 2" />
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
      buttonText: "save % move to next step"
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
      opacity: 0.5;
      font-size: $primary;
      font-weight: 500;
    }
  }

  .addTeam {
    display: flex;
    .add {
      display: flex;
      align-items: center;

      background: none;
      border: none;
      font-size: $primary;
      color: $white;
      cursor: pointer;
      img {
        margin-right: 1.5rem;
      }
    }
  }

    .previousStep {
    text-decoration: underline;
    align-self: center;
    cursor: pointer;
  }
}
</style>