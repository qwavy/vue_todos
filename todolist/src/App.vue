<template>
  <div>
    <test-counter/>
    <!-- <header-title v-bind:title="title" /> -->
    <search-panel v-model="searchValue"/>
    <filter-buttons/>
    <todo-list :todos="todos" :onToggleDone="onDone"/>
    <!-- asdasdas -->
    <form-add-task @onAdd="onAdd"/>
  </div>
</template>


<script>
// import HeaderTitle from "./components/HeaderTitle.vue";
import SearchPanel from "./components/SearchPanel.vue";
import TodoList from "./components/TodoList.vue";
import FormAddTask from "./components/FormAddTask.vue";
import FilterButtons from "./components/FilterButtons.vue"
// import TestCounter from "./components/TestCounter.vue"
export default {
  components: {
    FilterButtons,
    // TestCounter,
    // HeaderTitle,
    SearchPanel,
    TodoList,
    FormAddTask
  },
  data() {
    return {
      title: "welcome to my todolista",
      isLogin: false,
      selected:null,
      todos: [
        { id: 1, text: "learn vue" , important : false, done:true},
        { id: 2, text: "Drink cofee" , important : true, done:false}
      ],
      searchValue: ''
      // passwordV: true
    };
  },
  computed:{
    foundTasks(){
      return this.todos.filter(todo => todo.text.toLowerCase().includes(this.searchValue.toLowerCase()));
    },
    onFiltered(){
      const data = this.selected
      ? this.todos.filter((item) => item.important === this.selected)
      : this.todos
      return data
    }
    // filteredCategory(){
    //   const data
    // }
  },
  methods:{
    onSearch(value){
      this.searchValue = value
    },
    onFilter(category){
      this.selected = category
    },
    onDone(){
      console.log('todos',this.todos)
    },
    onDelete(id){
      const idx = this.todos.findIndex((item) => item.id === id);
      this.todos.splice(idx,1)
    },
    onAdd(text = "TASK"){
      const obj = {
        id: this.todos.length + 1,
        text,
        done:false,
        important:false
      }
      this.todos.push(obj)
    }
  }
};
</script>
// https://codesandbox.io/s/vue-3-article-category-filter-forked-vqiboz?file=/src/components/Articles.vue
<style>
</style>