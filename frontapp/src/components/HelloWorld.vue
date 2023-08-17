<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
  <button @click="callApi">call api</button>
</template>

<script>
import axios from "axios";
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods: {
    callApi: async function() {
      try {
        const result = await axios.get('http://localhost/api/');
        alert(result.data);
      } catch (err) {
        alert(JSON.stringify(err));
      }
    }
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
