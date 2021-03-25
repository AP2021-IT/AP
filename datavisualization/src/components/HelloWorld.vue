<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
     <h3>We are on the way to build interactive Data analysis application! </h3>
     we are going to use most advanced technologies
     <br>
      <a href="https://v3.vuejs.org/guide/installation.html#release-notes" target="_blank" rel="noopener">vue-cli documentation</a>
    <br>
    <a href="https://v3.vuejs.org/guide/installation.html#release-notes"></a>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
