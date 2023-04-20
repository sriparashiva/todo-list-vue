<template>
  <div id="app">
    <img class="logo" src="./assets/logo.svg" />
    <div class="container">
      <input
        class="todoForm"
        v-model="todoInput"
        type="text"
        placeholder="What do you want to do?"
        v-on:keyup.enter="addTodo"
      />
      <div class="todoList">
        <div
          v-for="(todo, index) in filteredTodos"
          :key="todo.id"
          class="todoItem"
        >
          <div class="todoItem-left">
            <input
              type="checkbox"
              v-model="todo.completed"
              class="todoCheckbox"
            />
            <div
              v-if="!todo.editing"
              class="todoLabel"
              :class="{ completed: todo.completed }"
              v-on:dblclick="editTodo(todo)"
            >
              {{ todo.title }}
            </div>
            <input
              v-else
              type="text"
              v-model="todo.title"
              v-on:blur="doneEdit(todo)"
              v-on:keyup.enter="doneEdit(todo)"
              v-on:keyup.esc="cancelEdit(todo)"
              class="editTodo"
              v-focus
            />
          </div>
          <div class="todoItem-right" v-on:click="removeTodo(index)">
            &times;
          </div>
        </div>
        <div v-if="filteredTodos.length === 0" class="noTasks">
          No tasks to show
        </div>
        <div v-if="filteredTodos.length > 0" class="editTip">
          Double click on a task to edit it
        </div>
        <div class="bottom">
          <div class="bottom-left">
            <input
              type="checkbox"
              name="completeAll"
              id="completeAll"
              :checked="allComplete"
              v-on:change="toggleAllComplete"
            />
            <label for="completeAll"> Complete All</label>
            <div class="pendingCount">{{ incompleteCount }} tasks pending</div>
          </div>
          <div class="bottom-right">
            <div class="todosFilters">
              <button
                :class="{ active: filterMode === 'all' }"
                v-on:click="filterMode = 'all'"
              >
                All
              </button>
              <button
                :class="{ active: filterMode === 'incomplete' }"
                v-on:click="filterMode = 'incomplete'"
              >
                Pending
              </button>
              <button
                :class="{ active: filterMode === 'completed' }"
                v-on:click="filterMode = 'completed'"
              >
                Completed
              </button>
            </div>
            <button
              class="clearCompleted"
              v-on:click="clearCompleted"
              v-if="showClearBtn"
            >
              Clear Completed Tasks
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'TodoList',
    data() {
      return {
        todoInput: '',
        idCounter: 2,
        editCache: '',
        filterMode: 'all',
        todos: [
          {
            id: 0,
            title: 'Make a todo app',
            completed: false,
            editing: false,
          },
          {
            id: 1,
            title: 'Deploy app',
            completed: false,
            editing: false,
          },
        ],
      }
    },
    computed: {
      incompleteCount() {
        return this.todos.filter((todo) => !todo.completed).length
      },
      allComplete() {
        return this.incompleteCount === 0
      },
      filteredTodos() {
        if (this.filterMode === 'all') return this.todos
        else if (this.filterMode === 'incomplete')
          return this.todos.filter((todo) => todo.completed === false)
        else if (this.filterMode === 'completed')
          return this.todos.filter((todo) => todo.completed === true)
        else return this.todos
      },
      showClearBtn() {
        return this.todos.filter((todo) => todo.completed).length > 0
      },
    },
    directives: {
      focus: {
        inserted: function (el) {
          el.focus()
        },
      },
    },
    methods: {
      addTodo() {
        if (this.todoInput.trim() != '') {
          this.todos.push({
            id: this.idCounter,
            title: this.todoInput,
            completed: false,
            editing: false,
          })
          this.idCounter++
          this.todoInput = ''
        }
      },
      removeTodo(index) {
        this.todos.splice(index, 1)
      },
      editTodo(todo) {
        this.editCache = todo.title
        todo.editing = true
      },
      cancelEdit(todo) {
        todo.title = this.editCache
        todo.editing = false
      },
      doneEdit(todo) {
        todo.editing = false
        if (todo.title.trim() === '') todo.title = this.editCache
      },
      toggleAllComplete() {
        if (this.allComplete)
          this.todos.forEach((todo) => (todo.completed = false))
        else this.todos.forEach((todo) => (todo.completed = true))
      },
      clearCompleted() {
        this.todos = this.todos.filter((todo) => todo.completed === false)
      },
    },
  }
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
    width: 80%;
    max-width: 768px;
    margin-left: auto;
    margin-right: auto;
  }
  .logo {
    max-width: 64px;
  }
  .todoForm {
    width: 100%;
    padding: 0.5rem;
    border: 2px solid #ccc;
    margin: 1rem 0;
  }
  .todoItem {
    display: flex;
    justify-content: space-between;
    flex-flow: row nowrap;
    padding: 0.5rem;
    border: 1px solid #ccc;
    margin: 1rem 0;
  }
  .todoItem-left {
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
  }
  .todoLabel {
    cursor: pointer;
  }
  .todoCheckbox {
    margin-right: 0.5rem;
  }
  .todoItem-right {
    cursor: pointer;
  }
  .completed {
    text-decoration: line-through;
    opacity: 0.5;
  }
  .bottom {
    width: 100%;
    padding: 0.5rem;
    border-top: 1px solid #ccc;
    margin: 1.5rem 0;
    display: flex;
    justify-content: space-between;
  }
  .bottom-left {
    text-align: left;
  }
  .todosFilters button {
    border-radius: 0px;
    background: #ccc;
    border: none;
    padding: 0.25rem;
  }
  .todosFilters button.active {
    background-color: green;
    color: white;
  }
  button.clearCompleted {
    width: 100%;
    border: none;
    padding: 0.25rem;
    margin: 0.5rem 0;
    background: #ccc;
  }
  .pendingCount {
    font-style: italic;
    margin: 0.5rem 0;
  }
  .editTip {
    font-size: 0.75rem;
  }
  .editTodo {
    border: none;
    font-size: 1rem;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
</style>
