<template>
    <div class="square">
        <AppHeader/>
        <nuxt/>
    </div>
</template>

<script>
  import AppHeader from '../components/AppHeader.vue'
  
  
  export default{
    components: {
        AppHeader,
        
    }
  }
  </script>
<style>
* {
    font-family:Arial, Helvetica, sans-serif
}
.square{
    background-color: rgb(245, 243, 243);
    width: 80vw;
    height: 100%; 
    margin: auto;
    padding-bottom: 2vw;  
}
</style>