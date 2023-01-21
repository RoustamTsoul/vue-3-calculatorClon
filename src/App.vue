<template>
<div id="app" class="container">
  <Calculator msg="My Calculator is a clon of yours"/>
</div>

</template>

<script>
import Calculator from './components/Calculator.vue'

export default {
  name: 'App',
  components: {
    Calculator 
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Audiowide&display=swap');

*{
    font-family: 'Audiowide', cursive;
    transition: 0.3s all;
    font-weight: 660;
    color: goldenrod;
}

body{
  background:linear-gradient(90deg, rgb(199, 51, 199) 4%, rgba(0, 209, 255, 1) 86%);
}

.container{
  width: 95%;
  height: 100vh;
  margin: auto;
  display: flex;
  justify-content: center;
  align-items:center;
}

#app{
  width:400px;
  margin: auto;   
}
</style>
