<template>
   
    <h2>Parameter:  {{user}}</h2>


</template>

<script>
export default {
  name: 'IndexPage1',

  data(){


      return{
          
        user:'',
      }
  },

  mounted(){

      console.log(this.$route.params.userId);
      this.user = this.$route.params.userId;
      
      
  },


methods:{


  }



}





</script>