<template>
    <div v-theme:column="'column'" id="show-blogs">
       <h1>List blogs</h1>
       <input type="text" placeholder="search" v-model="search">
       <div v-for="blog in filteredBlogs" class="single-blog">
            <h2 v-rainbow>{{ blog.title | to-uppercase }}</h2>
       </div>
    </div>
</template>

<script>
import searchMixin from '../mixins/searchMixin';
export default {

  data () {
    return {
       blogs:[],
       search:''
    }
  },
  methods:{

  },
  created(){
     this.$http.get('https://vue-test-da662.firebaseio.com/posts.json').then(function(data){
        console.log(data);
        this.blogs = data.body.slice(0,10);
     })
  },
  computed: {

  },
  filters:{
    // 'to-uppercase':function(value){
    //   return value.toUpperCase();
    // }
    toUppercase(value){
      return value.toUpperCase();
    }
  },
  directives:{
    'rainbow':{
      bind(el, binding, vnode){
         el.style.color = '#' + Math.random().toString().slice(2,8);
      }
    }
  },
  mixins: [searchMixin]
}
</script>


<style>
    #show-blogs{
      max-width: 800px;
      margin: 0 auto;
    }
    .single-blog{
      padding:20px;
      margin:20px 0;
      box-sizing:border-box;
      background: #eee;
    }
</style>
