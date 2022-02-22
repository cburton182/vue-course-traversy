<template>
  <footer>
    <p>Copyright &copy; 2022</p>
    <!-- should not be an a tag -->
    <router-link to="/about">About</router-link>
  </footer>
</template>

<style scoped>
a {
  color: #333;
}
footer {
  margin-top: 30px;
  text-align: center;
}
</style>
