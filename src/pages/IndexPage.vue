<template>
  <q-page padding>

    <ul>

      <TaskCompo
          v-for="(task, i) in tasks"
          :key="i"
          :task="task"
          :i="i"
          :tasks="tasks"
      >
        {{ task.name }}
      </TaskCompo>

    </ul>


  </q-page>
</template>

<script>

  import TaskCompo from '../components/TaskCompo.vue'

export default {
    name: "IndexPage",
    data() {
        return {
            tasks: [
                {
                    name: "go to shop",
                    dueDate: "1/1/2022",
                    dueTime: "7:45"
                },
                {
                    name: "get bananas",
                    dueDate: "11/1/2022",
                    dueTime: "8:45"
                },
                {
                    name: "get apples",
                    dueDate: "16/1/2022",
                    dueTime: "20:45"
                }
            ]
        };
    },

    components: { TaskCompo },

    methods: {
        deleteTask(index) {
            this.tasks.splice(index, 1);
        }
    },
};
</script>

<style scoped>

</style>
