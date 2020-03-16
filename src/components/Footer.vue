<template>
  <footer>
    <div class="footer-contaner">
      <p>Made with &#x2764; by <a href="https://twitter.com/geschenck__">geschenk__</a></p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
};
</script>


<style scoped>
footer {
  width: 100%;
  padding: .5rem 0;
  margin-top: .25rem;
  position: fixed;
  bottom: 0;
  right: 0;
  background: #fff;
  box-shadow: 0 -4px 4px 0 #eee;
  z-index: 5;
}

.footer-container {
  width: 90%;
  margin: 0 auto;
}

p {
  font-size: 1rem;
  text-align: center;
  /* color: #eee; */
}

a {
  color: #2c3e50;
  text-decoration: none;
}
</style>
