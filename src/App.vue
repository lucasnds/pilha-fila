<template>
  <div>
    <h1>Estrutura de Dados</h1>

    <button @click="this.fila=true; this.pilha=false" :class="{selected : this.fila}">Fila</button>
    &ensp;
    <button @click="this.fila = false; this.pilha=false">Home</button>
    &ensp;
    <button @click="this.fila=false; this.pilha=true" :class="{selected : this.pilha}">Pilha</button>
    <div v-if="this.pilha">
      <p v-for="item in n" :key="item">{{item}}</p>
      <button @click="this.n.shift()">Sai</button>
      &ensp;
      <button @click="this.n.unshift(1)">Entra</button>
      <p>Dicas:<br> <li>Use o 'X' como referência.</li> <li>Clique em 'Entrar' primeiro.</li> </p>
      
    </div>
    <div v-if="this.fila">
      <p v-for="item in n" :key="item">{{item}}</p>
      <button @click="this.n.shift()">Sai</button>
      &ensp;
      <button @click="this.n.push(1)">Entra</button>
      <p> <b> Dicas:</b><br> <li>Use o 'X' como referência.</li> <li>Clique em 'Entrar' primeiro.</li> </p>
    </div>
  </div>
</template>

<script>
export default{
  data(){
    return{
      fila:false,
      pilha:false,
      n:['X','X','X','X','X','X']
    }
  }
}
</script>

<style scoped>
body{
  width: 100%;
  height: 100%;
  background-color: #f9f9f9 !important;
}
.selected{
  background-color: lightskyblue;
  color: #fff;
  border: 1px solid #fff;
}
</style>
