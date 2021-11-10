<template>
  <div class="body" :class="{ dark: mode }">
    <Header  @current_mode="current_mode"/>
    <Main />
    <Footer />   
  </div>
</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer'
import Main from './components/Main'

export default {
  name: 'App',
  data() {
    return {
      mode: ''
    }
  },
  methods: {
    current_mode(dataValue){
      this.mode = dataValue
    }
  },
  components: {
    Header,
    Main,
    Footer
  },
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
  }
  .body{
    max-width: 2560px;
    overflow-x: hidden;
    margin: 0 auto;
    font-size: 1em;
    font-family: 'Poppins', sans-serif;
  }

  .body.dark .header{
    transition: 1s;
    background: #0a0a0a;
    color: #e6e6e6;
  }

  .body.dark .main{
    transition: 1s;
    background: #222324;
  }

  .body.dark .footer{
    transition: 1s;
    background: #0a0a0a;  
  }

  .body.dark .footer .text{
    transition: 1s;
    color: #5e6268;  
  }
  
  .body.dark .main .block{
    transition: 1s;
    background: #5e6268;
  }

  .body.dark .main .button{
    transition: 1s;
    background: #0a0a0a; 
    color: #ebebeb;
  }

  .body.dark .card{
    transition: 1s;
    background: #b9b9b9;;
  }

  .body.dark .modal-wrapper{
    background: #8f8f8f;
  }

  .body.dark .block h2{
    transition: 1s;
    color: #ffffff;  
  }

</style>
