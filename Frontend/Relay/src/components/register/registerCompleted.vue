<template>
  <div class="wrapper">
    <section class="headline">
      <h2>Congratulations</h2>
      <p>You're signed up & ready to go!</p>
      <p>Click below to explore matches.</p>
    </section>
    <RegisterButton @click="gotonextstep" :buttonText="buttonText" class="exploreMatchesBtn" />
    <img src="../../assets/graphics/progress-4.svg" alt="step 4" />
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
      buttonText: "explore matches now"
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
  color: $black;
  margin: auto 0 4rem 0;
  
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

  .exploreMatchesBtn {
    margin: 3rem 0;
  }

  img {
    margin-top: auto;
  }
}
</style>