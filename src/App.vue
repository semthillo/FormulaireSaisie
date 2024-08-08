<script >
import { ref } from 'vue';
export default {
  setup(){
    const nom = ref("")
    const email = ref("")
    const tel = ref("")
    const validation = ref("")
    
    
   
    function validerForm(){
      try {
        if (!nom.value || !email.value || !tel.value) {
          validation.value = "erreur veuillez remplir tout les champs"
          throw new Error("veuillez remplir les champs")
          
        }
        validation.value = "Utilisateur ajouté avec succee"
          } catch (error) {
            console.error("erreur de saisie", error.message)
          }
    

  nom.value =""
  email.value =""
  tel.value =""
}

return{
  validerForm,
  nom,
  email,
  tel,
  validation,
}
  }
}
  


// 
//  validerForm()




</script>

<template>
  
  

  
  <div class="bloc">
    <h1 class="titre">Formulaire De Saisie et Validation</h1>
    <form @submit.prevent="validerForm">
    <label >Nom</label>
    <input v-model="nom" nom="nom">
    <label >Email</label>
    <input v-model="email" email="email">
    <label >N° téléphone</label>
    <input v-model="tel" tel="tel">
    <button>Valider</button>
  </form> 
  <p v-if="validation" :style="{ color:'white' }" class="message">
    {{ validation }}
  </p>
  </div>
   

  
  
</template>

<style scoped>



</style>
