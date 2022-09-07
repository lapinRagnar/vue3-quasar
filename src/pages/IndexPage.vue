<template>
  <q-page padding>

    <ul>
      <li v-for="(task, i) in tasks" :key="i">

        <div> {{ task.name }} - {{ i }} </div>
        <small>{{ task.dueDate}} @ {{ task.dueTime }}</small>
        <button @click="deleteTask(i)">x</button>

      </li>
    </ul>


  </q-page>
</template>

<script>
export default {
  name: "IndexPage",
  data(){
    return {
      tasks: [
        {
          name: 'go to shop',
          dueDate: '1/1/2022',
          dueTime: '7:45'
        },
        {
          name: 'get bananas',
          dueDate: '11/1/2022',
          dueTime: '8:45'
        },
        {
          name: 'get apples',
          dueDate: '16/1/2022',
          dueTime: '20:45'
        }
      ]
    }
  },
  methods: {
    deleteTask(index){
      this.tasks.splice(index, 1)
    }
  }


};
</script>

<style scoped>

</style>
