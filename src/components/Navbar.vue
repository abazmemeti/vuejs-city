<template>
  <nav>
    <img src="../assets/logo.png" alt="City tour logo">
    <ul>
      <li>
        <a href="/">home</a>
      </li>
       <li>
        <a href="/">about</a>
      </li>
       <li>
        <a href="/" class="active">tours</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  props: {}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  nav {
    background-color: #444;
    display: grid;
    grid-template-columns: auto 1fr;
    padding: 0.3rem 1rem;
  }
  ul {
    list-style-type: none;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    align-self: center;
    text-align: center;
  }
  a {
    color: #eee;
    text-decoration: none;
    text-transform: capitalize;
    transition: all 0.3s linear;
  }
  a:hover, .active {
    color: #42b983;
  }
</style>
