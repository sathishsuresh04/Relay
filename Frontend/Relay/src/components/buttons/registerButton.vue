<template>
    <div>
        <button class="registerButton">{{buttonText}}</button>
    </div>
</template>

<script>
export default {
    props: {
        buttonText: String
    }
}
</script>

<style lang="scss" scoped>
@import "../../assets/scss/buttons.scss";


</style>