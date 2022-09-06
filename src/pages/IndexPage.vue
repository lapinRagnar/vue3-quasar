<template>
  <q-page padding>
    <input type="text" v-model="message">
    <h1>{{ message}}</h1>
  </q-page>
</template>

<script>


  export default{
    name: 'IndexPage',
    data (){
      return {
        message: 'Bonjour tout le monde!'
      }
    }
  }

</script>
