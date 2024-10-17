<script setup>
import { ref,reactive } from 'vue'
import Computed1 from './components/computed1.vue'

// exemple funció ref()

// variable reactiva
const usuari = reactive({
  nom: 'Ana',
  edat: 24
})

// variable reactiva
const contador =  ref(0)

// modifiquem el valor
const incrementar = () =>{
    contador.value++
}

// resetear valor
const reset =() =>{
  contador.value =0
}

// decrementar valor
const decremenar =() =>{
  contador.value--
}

// funció que aumenta l'edat
const aumentaEdat =() =>{
  usuari.edat++
}

// funció que reseteja edat
const resetEdat =() =>{
  usuari.edat = 24
}

// funció que decrementa l'edat
const decrEdat =() =>{
  usuari.edat--
}

// v-bind
const titol = "Francesc, mira la foquita y apruebame"

//url imagen
const urliImagen = "https://i.pinimg.com/236x/56/5a/cb/565acb22ed9343b6bff8e574bbd39104.jpg"

// usuari v-model
const nomUsuari = ref("");

// objeto v-for
const productos =[
  {
    id:1,
    nombre: "falda",
    color: "azul"
  },
  {
    id:2,
    nombre: "camiseta",
    color: "blanco"
  },
  {
    id:3,
    nombre: "lazo",
    color: "rojo"
  }
]

// Condicionales
const logat = ref(false);

const logarse = () =>{
  logat.value=!logat.value
}

// v-show
const mostrar = ref(false)

// computed 



</script>

<template>
<div>
  <h2>Función Ref()</h2>
    <p>El comptador és: {{ contador }} </p>
    <button @click="incrementar">Incrementar</button>
    <button @click="decremenar">Decrementar</button>
    <button @click="reset">Resetear cuanta</button>
</div>

<div>
  <h2>Variables Reactive</h2>
  <p>Nom: {{ usuari.nom }}</p>
  <p>Edat: {{ usuari.edat }}</p>
  <button @click="aumentaEdat">Incrementar edad</button>
  <button @click="decrEdat">Decrementar edad</button>
  <button @click="resetEdat">Reset</button>
</div>

<!-- v-bind -->
<div>
  <h2 v-bind:title="titol">Hover me!</h2>
  <img :src="urliImagen" alt="Imatge">
</div>

<!-- v-model -->
 <div>
  <p>Nom usuari: {{ nomUsuari }} </p>
  <input type="text" placeholder="Introduce su nombre" v-model="nomUsuari">
 </div>

 <!-- v-for -->
  <div>
    <h2>V-for</h2>
    <ul>
      <li v-for="producto in productos" :key="producto.id"> {{ producto.nombre}} Color: {{ producto.color }}</li>
    </ul>
  </div>

  <!-- Condicionales -->
   <div>
    <h2>Condicionales v-if/v-else</h2>
    <p v-if="logat" style="color: green;">Benvingut/da a l'espai</p>
    <p v-else style="color: red;">No t'has logat</p>
    <button @click="logarse">Te prometo por Snoopy que soy yo, déjame entrar</button>

   </div>

   <!-- Directiva v-show -->
    <div>
      <h2>Directiva v-show</h2>
      <button @click="mostrar=!mostrar">No pulsar</button>
      <p v-show="mostrar">Qué haces? Te he dicho que no pulses el botón!</p>
    </div>

    <!-- Directiva v-on -->
     <!-- Es equivalente a @click -->
     <div>
      <h2>Directiva v-on</h2>
      <p>Es equivalente a @click, mira el código</p>
     </div>
    <!-- Computed -->
     <div>
      <h2>Computed</h2>
      <Computed1></Computed1>
     </div>

</template>

<style scoped>
/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
