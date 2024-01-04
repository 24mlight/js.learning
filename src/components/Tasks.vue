<template>
  <div :key="task.id" v-for="task in tasks">
    <Task @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)"
      :task="task" />
  </div>
</template>

<script>
import Task from './Tasks.vue' // from child 

export default {
  name: 'Tasks',
  props: { 				// to be dilivered to father 
    tasks: Array,
  },
  components: { 		// from child 
    Task,
  },
  emits: ['delete-task', 'toggle-reminder'],
}
</script>
