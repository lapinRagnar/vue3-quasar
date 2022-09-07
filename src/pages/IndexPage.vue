<template>
  <q-page padding>

    <ul>
      <li v-for="(task, i) in tasks" :key="i"> {{ task }} </li>
    </ul>


  </q-page>
</template>

<script>
export default {
  name: "IndexPage",
  data(){
    return {
      tasks: ['go to shop', 'get bananas', 'get apples']
    }
  }


};
</script>

<style scoped>

</style>
