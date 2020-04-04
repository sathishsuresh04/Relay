<template>
  <div class="wrapper">
    <section class="headline">
      <h2>Lender - Sign</h2>
      <p class>A few final details</p>
    </section>

    <section class="terms">
      <p class="termHeadline">Terms & Conditions</p>
      <section class="termScroll">
        <p
          class="termsDoc"
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis ipsa, vero culpa placeat adipisci voluptate reprehenderit ea facere fuga cupiditate.</p>
        <p
          class="termsDoc"
        >Lorem, ipsum dolor sit amet consectetur adipisicing elit. Minus, doloremque!</p>
        <p
          class="termsDoc"
        >Lorem, ipsum dolor sit amet consectetur adipisicing elit. Animi pariatur quod minima, veritatis nulla blanditiis inventore omnis quos alias! Animi voluptatem omnis provident commodi.</p>
        <p
          class="termsDoc"
        >Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repellat obcaecati, eos autem accusantium repellendus magnam tempore esse debitis?</p>
        <p
          class="termsDoc"
        >Lorem, ipsum dolor sit amet consectetur adipisicing elit. Minus, doloremque!</p>
        <p
          class="termsDoc"
        >Lorem, ipsum dolor sit amet consectetur adipisicing elit. Animi pariatur quod minima, veritatis nulla blanditiis inventore omnis quos alias! Animi voluptatem omnis provident commodi.</p>
        <p
          class="termsDoc"
        >Lorem ipsum dolor sit amet, consectetur adipisicing elit. Repellat obcaecati, eos autem accusantium repellendus magnam tempore esse debitis?</p>
      </section>
    </section>
    <section class="approve">
      <div class="check">
        <button @click="termsAccept = !termsAccept" class="checkmark">
          <img v-if="termsAccept" src="../../assets/graphics/checkmark.svg" alt="check" />
        </button>
        <p>I have read & approve the terms of service</p>
      </div>
      <div class="check">
        <button @click="staffAccept = !staffAccept" class="checkmark">
          <img v-if="staffAccept" src="../../assets/graphics/checkmark.svg" alt="check" />
        </button>
        <p>My staff have opted in</p>
      </div>
    </section>
    <RegisterButton @click="gotonextstep" :buttonText="buttonText" />
    <p @click="gotopreviousstep" class="previousStep">Go back to previous step</p>
    <img src="../../assets/graphics/progress-3.svg" alt="step 3" />
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
      buttonText: "save & complete sign up",
      termsAccept: false,
      staffAccept: false
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

  .terms {
    display: flex;
    flex-direction: column;
    text-align: center;
    color: $black;
    background: $white;
    padding: 1rem 0.4rem 0 0.4rem;
    border-radius: 8px;
    height: 24rem;

    .termHeadline {
      font-weight: 600;
    }

    .termsDoc {
      margin: 0.5rem 0;
      color: $black;
      font-size: 12px;
    }
  }

  .termScroll {
    overflow-y: scroll;
    margin: 1rem 0 0 0;
  }

  .termScroll::-webkit-scrollbar {
    background: $scrollbar;
    border-radius: 4px;
    width: 4px;
  }
  .termScroll::-webkit-scrollbar-thumb {
    background: $scrollbarThumb;
    opacity: 0.5;
    border-radius: 4px;
  }

  .approve {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 6rem;

    .check {
      display: flex;
      align-items: center;
      .checkmark {
        display: flex;
        width: 24px;
        height: 24px;
        background: none;
        border: 2px solid $white;
        border-radius: 4px;
        justify-content: center;
        cursor: pointer;
        img {
          margin-top: -0.2rem;
        }
      }

      p {
        font-size: $xsmall;
        margin-left: 1.5rem;
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