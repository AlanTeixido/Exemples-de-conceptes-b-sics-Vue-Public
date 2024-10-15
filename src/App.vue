<script setup>
// Exemple ref
import {ref} from 'vue'

const num = ref(0)

const incrementar = () => {
  num.value++
}


// Exemple reactive
import { reactive } from 'vue'

const usuario = reactive({
  nombre: 'Juan',
  apellido: 'Perez',
  edad: 30
})


// Exemple computed
import { computed } from 'vue'

const nombreCompleto = computed(() => {
  return `${usuario.nombre} ${usuario.apellido}`
})



// Exemple v-bind
const url = 'https://www.google.com'
const isDisabled = true
const isHidden = true
const isUnderline = true
const isBold = true

const titol = 'hola pesicola'


// 
const nomUsuari = (ref(''));


//Directiva v-for

const productos =[ {id: 1,  nombre: "Colacao",  preu: "31"},
{id: 2, nombre: "Nocilla", preu: "20"},
{id: 3, nombre: "Oreos", preu: "10"}]

// Directiva v-if
const mostrar = ref(true)
// Directiva v-show
const mostrarshow = ref(true)






</script>

<template>

  <body>
  <div>
    <h1>{{ num }}</h1>
    <button v-on:click="incrementar">Incrementar</button>
  </div>


  <div>
    <h1>Exemple reactive</h1>  
    <p>Nombre: {{ usuario.nombre }}</p>
    <p>Apellido: {{ usuario.apellido }}</p>
    <p>Edad: {{ usuario.edad }}</p>
    <button v-on:click="usuario.edad++">Incrementar edad</button>
  </div>


  <div>
    <h1>Exemple computed</h1>  
    <p>Nombre completo: {{ nombreCompleto }}</p> 
  </div>


  <div>
    <h1>Exemple v-bind</h1>
    <a v-bind:href="url">Google</a>
    <button v-bind:disabled="isDisabled">Boton deshabilitado</button>
    <p v-bind:hidden="isHidden">Parrafo oculto</p>  
    <p v-bind:class="{ underline: isUnderline, bold: isBold }">Texto con estilos</p>
    <p v-bind:title="titol">Pasa el ratoli per sobre</p>    
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRYNWiXngJ3CZzvSaHOlxHRViPni19kEtYjMA&s" alt="imatge" />   
  </div>

  <div>
    <h1>Exemple v-model</h1>
    <input v-model="nomUsuari" type="text" placeholder="Escriu el teu nom aqui"/>
    <p>{{ nomUsuari }}</p>
  </div>


  <div>
    <h1>Directiva v-for</h1>
    <ul>
      <li v-for="producto in productos" :key="producto.id">{{ producto.nombre }} - {{ producto.preu }}€    </li>
    </ul>
  </div>


  <div>
    <h1>Directiva v-if</h1>
    <p v-if="mostrar">Aquest parrafo es mostrara si mostrar es true</p>
    <p v-else>Aquest parrafo es mostrara si mostrar es false</p>
    <button v-on:click="mostrar =! mostrar">Mostrar/ocultar</button>    
  </div>


  <div>
  <h1>Directiva v-show</h1>
  <p v-show="mostrarshow">Aquest parrafo es mostrara si mostrar es true</p>
  <p v-show="!mostrarshow">Aquest parrafo es mostrara si mostrar es false</p>
  <button v-on:click="mostrarshow =! mostrarshow">Mostrar/ocultar</button>
  
  
  </div>


</body>


</template>

<style scoped>
/* General styles */
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  color: #675f5f;
}

h1 {
  color: #4a90e2;
  font-size: 24px;
  margin-bottom: 20px;
}

p {
  font-size: 18px;
  margin-bottom: 10px;
}

button {
  background-color: #4a90e2;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: 16px;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

button:hover {
  background-color: #357ab7;
}

button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}

/* Style for v-model input */
input {
  padding: 8px;
  font-size: 16px;
  border: 2px solid #ccc;
  border-radius: 5px;
  margin-bottom: 10px;
}

input:focus {
  outline: none;
  border-color: #4a90e2;
}

a {
  text-decoration: none;
  color: #4a90e2;
  transition: color 0.3s ease;
}

a:hover {
  color: #357ab7;
}

img {
  max-width: 100%;
  height: auto;
  border-radius: 10px;
  margin-top: 10px;
}

ul {
  list-style-type: none;
  padding-left: 0;
}

li {
  background-color: #e9e9e9;
  margin: 5px 0;
  padding: 10px;
  border-radius: 5px;
}

.underline {
  text-decoration: underline;
}

.bold {
  font-weight: bold;
}

/* Responsive design */
@media (min-width: 1024px) {
  body {
    max-width: 1200px;
    margin: 0 auto;
  }

  div {
    margin-top: 40px;
  }
}

</style>
