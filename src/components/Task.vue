<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }}

      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>
      {{ task.day }}
    </p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
};
</script>

<style scoped>
h3 {
  display: flex;
  justify-content: space-between;
}

.task {
  display: flex;
  flex-direction: column;

  background: lightblue;
  padding: 10px;
  margin-bottom: 5px;
}

.reminder {
  background: lightcoral;
}

.fas {
  cursor: pointer;
}
</style>
