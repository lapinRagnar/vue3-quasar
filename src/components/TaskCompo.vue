<template>

  <li>

    <div> {{ task.name }} - {{ i }} </div>
    <small>{{ task.dueDate}} @ {{ task.dueTime }}</small>
    <button @click="deleteTask(i)">x</button>

  </li>

</template>

<script>
  export default {

    props: ['task', 'i'],


  }
</script>

<style>

</style>
