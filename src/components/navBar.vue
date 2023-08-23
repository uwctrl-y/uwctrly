<template>
  <nav class="nav-bar">
    <img class="logo" src="@/assets/home/CTRL+y-Nav.png" alt="Logo">
    <ul class="navbar-list">
      <li class="navbar-item">about</li>
      <li class="navbar-item">sponsors</li>
      <li class="navbar-item">judges</li>
      <li class="navbar-item">faq</li>
      <li class="navbar-item">team</li>
    </ul>
    <div class="navbar-item">
      <div>
        interested?
        <br>
        <span>Contact Us</span>
      </div>
    </div>
  </nav>
</template>

<style>
.nav-bar {
  padding-top: 15px;
  display: flex;
  justify-content: space-between;
  align-items: center; /* Add this line to vertically align items */
  width: 100vw;
}

.navbar-list {
  display: flex;
  list-style-type: none;
  justify-content: center;
}

.navbar-item {
  margin: 0 50px;
  font-size: 14px;
  font-style: normal;
  font-weight: 500;
  line-height: normal;
  color: #09702C;
  text-decoration: underline;
}


.logo {
  width: 100px; /* Adjust the width as needed */
  height: auto;
  margin-left: 2rem;
}

</style>

<script setup>
</script>
