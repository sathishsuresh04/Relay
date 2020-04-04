<template>
    <div class="wrapper">
<ExitBtn />
    </div>
</template>

<script>
import ExitBtn from "../components/buttons/exitBtn";

export default {
    components: {
        ExitBtn
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/variables.scss";
@import "../assets/scss/buttons.scss";

.wrapper {
    background: $darkBlue;
    width: 100vw;
    height: 100vh;
}

</style>