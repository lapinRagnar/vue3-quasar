<template>
  <q-page padding>

    <button @click="counter++"> {{ counter }} </button>

    <input
      type="text"
      @keyup.esc="effacerMessage"
      @keyup.enter="alertMessage"

      v-model="message"
      v-autofocus

      :style="errorStyle"

      ref="messageInput"

    />

    <div>logueur du message : {{message.length }}</div>

    <h1 class="border-grey" v-if="message.length" >{{ message }}</h1>
    <h4 v-else>pas de message!</h4>

    <button @click="message = ''">effacer</button>

    <hr>

    <p>uppercase message : {{ messageUppercase }} </p>
    <!-- <p>lowercase message : {{ messageLowercase(message) }} </p> -->

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
    },
    errorStyle(){
      if (this.message.length > 22){
        return {
          'color': 'red',
          'background': 'pink'
        }
      } else {

        return {}
      }
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
  },
  directives: {
    autofocus: {
      inserted(el){
        console.log('input inserted')
        el.focus()
      }
    }
  },
  mounted() {
    console.log(this.$refs)
    this.$refs.messageInput.className = 'bg-green'
  },


};
</script>

<style scoped>
  .border-grey {
    border: 1px solid grey;
    background-color: aqua;
  }

  .error {
    color: red;
    background: pink;
  }

  input, button {
    font-size: 23px;
  }
</style>
