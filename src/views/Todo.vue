<template>
  <div class="content">
    <h1>todos</h1>
    <input type="text" autofocus v-model="input" @keypress.enter="newTodo"/>
    <div v-if="todos.length" v-cloak>Double click to complete todo.</div>
    <ul class="todos">
      <li 
        v-for="todo in todos" 
        :key="todo.id" 
        @dblclick="completedTodo(todo)"
        :class="{ completed: todo.completed }"
      >
        {{ todo.name }}
      </li>
    </ul>
    <div class="footer" v-if="todos.length">
      <div class="count">{{ todos.length }}</div>
      <div class="stat">
        <a href="#all">All</a>
        <a href="#active">Active</a>
        <a href="#completed">Completed</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      input: '',
      todos: [],
    }
  },
  methods: {
    newTodo() {
      var todo = this.input && this.input.trim()
      if(todo) {
        this.todos.push({ 
          id: this.todos.length, 
          name: todo,
          completed: false
        })
        this.input = ''
      }
    },
    completedTodo(todo) {
      todo.completed = !todo.completed
    }
  }
}
</script>


<style scoped>
.content {
  max-width: 350px;
  margin: 0 auto;
  text-align: center;
  padding: 80px 0px;
}
input {
  outline: none;
  width: 100%;
  padding: 5px 20px;
  border: 2px solid #ddd;
  border-top-left-radius: 15px;
  border-bottom-right-radius: 15px;
  transition: linear 0.3s;
  
}
input:focus {
  border: 2px solid #aaa;
  border-radius: 0;
  border-top-right-radius: 15px;
  border-bottom-left-radius: 15px;
}

.todos {
  padding: 30px;
}
.todos li {
  cursor: pointer;
  word-wrap: break-word;
  user-select: none;
  padding: 10px 0;
  transition: ease-out 0.3s;
}
.completed {
  color: #aaa;
  text-decoration: line-through;
}


.footer div {
  display: inline-block;
}
</style>