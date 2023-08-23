<template>
    <div class="SplashScreen">
        <div v-if="isLoading" class="loader">
            <img src="@/assets/home/keyanimated.gif" alt="">
        </div>
    </div>
</template>

<script>
export default {
    name: "SplashScreen",
    props: ["isLoading"],
    mounted() {
        console.log("isLoading:", this.isLoading);
    }
};
</script>

<style scoped>
.SplashScreen {
    display: flex;
    justify-content: center;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    width: 100vw;
    height: 100vh;
    background-color: white;
    z-index: 1;
    overflow: hidden;
}

.loader {
    opacity: 1;
    transition: opacity 0.4s ease-in-out;
}

.loader.hidden {
    opacity: 0;
    visibility: hidden;
}
</style>
