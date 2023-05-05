<template>
  <footer class="footer">
    <div class="container">
      <span class="text-muted">&copy; BACANCY TECHNOLOGY {{ new Date().getFullYear() }}</span>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 60px;
  line-height: 60px;
  background-color: #ff8c12;
}

.container {
  text-align: center;
}
</style>
