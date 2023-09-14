npm <template>
  <div class="splash-screen">
    <div :class="{ loader: true, fadeout: !isLoading, keys}">
      <img src="@/assets/home/keyanimated.gif" alt="">
    </div>
  </div>
</template>

<script>
export default{
  name: "splashScreen",
  props: ["isLoading"],
}
</script>

<style>
.splash-screen{
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  width: 100vw;
  height: 100vh;
  background-color: transparent;
  z-index: 1;
  overflow: hidden;
}

.keys{
  width: 38%;
}

.fadeout {
  animation: fadeout 0.2s forwards;
}

@keyframes fadeout {
  to {
    opacity: 0;
    visibility: hidden;
  }
}

@media (max-width: 480px) { 
  .splash-screen {
    margin-left: 5vw;
  }
  .keys {
    width: 10%;
  }
}


</style>