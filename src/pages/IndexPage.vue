<template>
  <q-page padding>

    <button @click="counter++"> {{ counter }} </button>

    <input
      type="text"
      @keyup.esc="effacerMessage"
      @keyup.enter="alertMessage"

      v-model="message"
    />

    <h1 class="border-grey" v-if="message.length" >{{ message }}</h1>
    <h4 v-else>pas de message!</h4>

    <button @click="message = ''">effacer</button>

    <hr>

    <p>uppercase message : {{ messageUppercase }} </p>
    <p>lowercase message : {{ messageLowercase(message) }} </p>

  </q-page>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      message: "Bonjour tout le monde!",
      counter: 0
    };
  },
  computed: {
    messageUppercase(){
      console.log('message uppercase')
      return this.message.toUpperCase()
    },
    messageLowercase(value){
      return value.toLowerCase()
    }
  },
  methods: {
    effacerMessage() {
      this.message = "";
    },
    handleKeyup(e) {
      console.log(e);
    },
    alertMessage(e) {
      console.log(e);
      alert("Bonjour");
    },
  }
};
</script>

<style>
  .border-grey {
    border: 1px solid grey;
    background-color: aqua;
  }
</style>
