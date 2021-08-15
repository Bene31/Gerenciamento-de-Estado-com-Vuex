<template>
  <h1> To-do </h1>
  <ul>
    <li v-for="todo in $allTodos" :key="todo.id">
      {{todo.text}}
    </li>
  </ul>

  <h1> Done </h1>
  <ul>
    <li v-for="todo in $doneTodos" :key="todo.id">
      {{todo.text}}
    </li>
  </ul>
</template>

<script>

export default {
  created(){
    this.$store.dispatch('fetchTodos')
  },
  computed:{
    $allTodos(){
      return this.$store.getters.$allTodos
    },
    $doneTodos(){
      return this.$store.getters.$doneTodos
    }
  }
};
</script>


