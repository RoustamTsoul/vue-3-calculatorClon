<template>
  <div class="title">
    <h1>{{ msg }}</h1>
  </div>
  <div class="calculate">
    <input v-model="result" type="text" placeholder="0">
    <button v-on:click="input(num)" class="cell num" v-for="num in numbers" v-bind:key="num">{{num}}</button>
    <button v-on:click="input(op)" class="cell op" v-for="op in operations" v-bind:key="op">{{op}}</button>
    <button v-on:click="reset()" class="cell op">R</button>
    <button v-on:click="calc()" class="cell op">=</button>
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  props: {
    msg: String
  },

  data(){
    return {
      result:'',
      numbers: [1,2,3,4,5,6,7,8,9,0],
      operations: ['+','-','*','/'],
    }
  },

  methods:{
    input: function(char){
    this.result = this.result.toString(); // фиксится баг eval()
    this.result += char;
    },

    reset: function(){
    this.result = '';
    },

    calc: function(){
    this.result = eval(this.result);
    }
  }
}
</script>


<style scoped>
input{
    box-sizing: border-box;
    width: 100%;
    height: 50px;
    border: 0;
    border-top-left-radius:10px;
    border-top-right-radius: 10px;
    color:rgb(190, 136, 0);
    font-size: 20px;
    box-shadow: 0px 0px 4px 4px tomato;
    padding: 5px 5px;
    text-align: right;
}

.calculate{
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.cell{
    flex: 33%;
    height: 50px;
    font-size: 18px;
    border: none;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    box-shadow: 0px 0px 4px 4px tomato;
}

.cell:hover{
    background-color:rgb(16, 55, 63);
}

.num{
    background-color:rgb(161, 215, 227);
    color: rgb(185, 133, 0);
    font-weight: 700;
}

.op{
    background-color:rgb(140, 48, 140);
    color: rgb(138, 110, 39);
    font-weight: 700;
}

.title{
  width: 500px;
  text-align: center;
  justify-items: center;
  padding: 10px;
}
</style>
