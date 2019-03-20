<template>
    <div>
      <h1>Please fill out our form</h1>
      <form>
         <div id="form-header">
              <slot name="form-header"></slot>
         </div>
         <div id="form-fields">
              <slot name="form-fields"></slot>
         </div>
         <div id="form-controls">
              <slot name="form-controls"></slot>
         </div>
         <div id="useful-links">
             <ul>
               <li><a href="#">Link 1</a></li>
               <li><a href="#">Link 2</a></li>
               <li><a href="#">Link 3</a></li>
               <li><a href="#">Link 4</a></li>
             </ul>
         </div>
      </form>
    </div>
</template>

<script>
export default {
  name: 'formHelper',
  data () {
    return {

    }
  },
  methods:{

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
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
