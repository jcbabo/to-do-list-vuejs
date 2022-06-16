<template>
  <div class="app-container">
    <component :is="layout" class="dynamic-layout">
      <router-view />
    </component>
  </div>
  <div class="page">
    <div class="principal-content">
      <div class="title-page">
        <h1>To-do List</h1>
        <h5>Agora em VueJs!</h5>
      </div>
      <div class="todo-input">
        <input type="text" name="todo-input" v-model="todo" @keyup.enter="addTask(todo)" />
        <button class="btn-input" @click="addTask(todo)">Inserir
        </button>
      </div>
      <div class="task-grid">
        <input type="checkbox" />
        <ul>
          <li>As tarefas aparecerão aqui</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Todo-List',

  created() {

    document.title = 'Application To-do List'

  },

  data() {
    return {
      id: 0, //id das tarefas listadas
      todo: '', // nome da tarefa que será vinculada ao input
      todos: [], // array vazio que armazenará as tarefas
    }
  },

  methods: {
    //gera uma id novo para cada tarefa
    genId() {
      return (this.id += 1); //incrementa o data property "id", iniciando no '1'
    },

    //adiciona uma nova tarefa ao array 'todos'
    addTask(todo) {
      this.todos.push({
        id: this.genId(), //gera um novo id
        name: todo, //o nome da tarefa
        done: false, //para que a tarefa apareça como 'não completada' na lista
      });
      this.todo = ""; //limpa os dados do input
    },

    //pega o índice da tarefa corrente para facilita uma explusão posterior
    getIndex(todo) {
      //a variável recebe a tarefa como parâmetro, procura seu índice e retorna ele
      let index = this.todos.findIndex(item => item.id === todo.id);
      return index;
    },

    //exclui uma tarefa a partir de seu índice atraveś de um splice no array
    removeTask(todo) {
      let index = this.getIndex(todo); //a variável recebe o índice da tarefa em questão
      this.todos.splice(index, 1); //faz um splice no array e remove o índice da variável "index"
    },

    //recebe uma tarefa como parâmetro de entrada e muda seu status
    taskComplete(todo) {
      todo.done = !todo.done
    },
  }
}

</script>

<style lang="scss">
// .page {
//   display: grid;
//   justify-content: center;
//   background-color: $bg-page;
//   margin: auto;
//   border: $borders 2px solid;
//   border-radius: 10px;
//   max-width: 750px;
// }

// .principal-content {
//   padding: 20px 10px;
// }

// .title-page {
//   color: $text;
//   text-align: center;
// }

// h1, h5 {
//   margin: 0px;
//   padding-bottom: 14px;
// }

// .todo-input {
//   display: grid;
//   grid-template-columns: 1fr 1fr;
//   width: fit-content;
//   column-gap: 10px;
//   padding: 30px 0px;
// }

// input, button {
//   color: $text;
//   background-color: $bg-input;
//   border: $borders  1px solid;
//   border-radius: 3px;
//   box-shadow: none;
//   padding: 5px 10px;
// }

// .btn-input {
//   width: 60px;
// }

// .task-grid {
//   display: grid;
//   grid-template-columns: auto 1fr;
//   column-gap: 5px;
// }

// ul {
//   margin: 0px;
//   list-style-type: none;
//   padding: 0px;
// }

// li {
//   color: $text;
// }

:root {
  font-size: 62.5%;
  font-family: 'Prompt', Sans-Serif;

  body {
    font-size: 1.7rem;
  }

  #app,
  .app-container {
    height: 100vh;
  }
}
</style>
