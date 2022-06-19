<template>
  <div class="base-layout">
    <div class="principal-content">
      <div class="title-page">
        <h1>To-do List</h1>
        <h4>Agora em VueJs!</h4>
      </div>
      <div class="todo-input">
        <InputField></InputField>
        <InsertButton></InsertButton>
      </div>
      <div class="task-grid">
        <!-- <TaskArea></TaskArea> -->
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import InputField from '../components/InputField.vue'
import InsertButton from '../components/InsertButton.vue'
import TaskArea from '../components/TaskArea.vue'

// export default {
//   name: 'Todo-List',

//   created() {

//     document.title = 'Application To-do List'

//   },

//   data() {
//     return {
//       id: 0, //id das tarefas listadas
//       todo: '', // nome da tarefa que será vinculada ao input
//       todos: [], // array vazio que armazenará as tarefas
//     }
//   },

//   methods: {
//     //gera uma id novo para cada tarefa
//     genId() {
//       return (this.id += 1); //incrementa o data property "id", iniciando no '1'
//     },

//     //adiciona uma nova tarefa ao array 'todos'
//     addTask(todo) {
//       this.todos.push({
//         id: this.genId(), //gera um novo id
//         name: todo, //o nome da tarefa
//         done: false, //para que a tarefa apareça como 'não completada' na lista
//       });
//       this.todo = ""; //limpa os dados do input
//     },

//     //pega o índice da tarefa corrente para facilita uma explusão posterior
//     getIndex(todo) {
//       //a variável recebe a tarefa como parâmetro, procura seu índice e retorna ele
//       let index = this.todos.findIndex(item => item.id === todo.id);
//       return index;
//     },

//     //exclui uma tarefa a partir de seu índice atraveś de um splice no array
//     removeTask(todo) {
//       let index = this.getIndex(todo); //a variável recebe o índice da tarefa em questão
//       this.todos.splice(index, 1); //faz um splice no array e remove o índice da variável "index"
//     },

//     //recebe uma tarefa como parâmetro de entrada e muda seu status
//     taskComplete(todo) {
//       todo.done = !todo.done
//     },
//   }
// }

</script>

<style lang="scss">
.base-layout {
  display: grid;
  justify-content: center;
  background-color: $bg-page;
  margin: auto;
  border: $borders 2px solid;
  border-radius: 10px;
  max-width: 750px;

  .principal-content {
    padding: 20px 10px;
  }

  .title-page {
    color: $text;
    text-align: center;

    h1 {
      margin: 0px;
      font-size: 4rem;
      padding-bottom: 14px;
    }

    h4 {
      margin: 0px;
      font-size: 1.5rem;
      padding-bottom: 44px;
    }
  }

  .todo-input {
    display: grid;
    grid-template-rows: 1fr 1fr;
    row-gap: 10px;
    text-align: center;

    @include min-width($tablet) {
      display: flex;
      column-gap: 10px;
    }
  }
}
</style>
