<template>
  <!-- <p>Learn vue</p> -->
  <div>
    <ul>
      <todo-list-item v-for="item in todos" :key="item.id" :text="item.text" :important="item.important" :done="item.done" :onDone="onToggleDone" />
    </ul>
  </div>
</template>
<script>
import TodoListItem from "./TodoListItem.vue";
export default {
  props: {
    todos: Array,
    onToggleDone:Function,
  },
  components: { TodoListItem }
};
</script>
