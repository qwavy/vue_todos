<template>
  <li class="todo_item" :class="{important_task:important,done:done,delete_task:delete_task}">
    {{text}}
    <button>important</button>
    <button @click="onDone()">done</button>
    <button >delete</button>
  </li>
</template>
<script>
export default {
  props: {
    text: { type: String, required: true },
    done: { type: Boolean, default: false },
    important: {
      type: Boolean,
      default: false
    },
    onDone: Function,
  },
  // methods: {
  //   onDone() {
  //     this.done = !this.done;
  //     console.log(this);
  //   }
  // }
};
</script>
<style scoped>
.todo_item {
  border: 2px dotted red;
  font-family: fantasy;
  list-style: none;
  padding: 8px 12px;
  display: block;
  border: 1px solid #ccc;
  border-radius: 8px;
  margin-bottom: 12px;
}
.important_task {
  font-weight: bold;
  color: blue;
}
.done {
  text-decoration: line-through;
}
.delete_task {
  display: none;
}
</style>