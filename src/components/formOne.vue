<template>
    <div>
      <form-helper>
        <div slot="form-header">
          <h3>Form One - Log in</h3>
          <p>Enter your details to log in</p>
        </div>
        <div slot="form-fields">
           <input type="text" placeholder="name" required />
           <input type="password" placeholder="password" required />
        </div>
        <div slot="form-controls">
           <button v-on:click="handleSubmit">Submit</button>
        </div>
      </form-helper>
    </div>
</template>

<script>
import formHelper from './formHelper.vue';
export default {
  name: 'formHelper',
  components: {
     'form-helper': formHelper
  },
  data () {
    return {

    }
  },
  methods:{
    handleSubmit:function(){
      alert('thanks for logging in (fortm One)');
    }
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
