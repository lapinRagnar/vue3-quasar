<template>
  <q-page padding>
    <input
      type="text"
      @keyup.esc="effacerMessage"
      @keyup.enter="alertMessage"
      @mouseenter="alertMessage"
      v-model="message"
      >
    <h1>{{ message}}</h1>
    <button @click="message = ''">effacer</button>
  </q-page>
</template>

<script>


  export default{
    name: 'IndexPage',
    data (){
      return {
        message: 'Bonjour tout le monde!'
      }
    },
    functions: {
      effacerMessage(){
        this.message = ''
      },
      handleKeyup(e){
        console.log(e)
      },
      alertMessage(e){
        console.log(e)
        alert('Bonjour')
      }
    }
  }

</script>
