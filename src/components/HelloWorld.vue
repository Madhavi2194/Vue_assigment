 <template>
  <div>
    <h2>Filter LearnVue Articles</h2>
    <input type="text" placeholder="Filter Search" v-model="query" />
    <br />
    <button v-on:click="reset()">Reset</button>
    <search-results v-bind:query='query'/>

  </div>
</template>


<script>
    
import { ref } from "vue";
import SearchResults from './TitleResults.vue'

  export default {
    name: 'HelloWorld',
    props: {
      msg: String
    },
    components: {
      SearchResults
    },
    setup() {
    const query = ref("");

    const reset = () => {
      query.value = "";
    };

    return {
      reset,
      query,
    };
  },
};

  
  
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
input {
    margin-bottom: 24px;
    border: 2px solid darkcyan;
    padding: 10px;
    border-radius: 3px;
    outline: none;
}

button {
  margin-bottom: 20px;
}
</style>
