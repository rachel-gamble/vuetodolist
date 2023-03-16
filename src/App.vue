<template>
  <div id="app">
    <div class="container">
      <h1>Vue ToDo</h1>
      <input class="input" v-model="newToDo" />
      <button v-on:click="add()" class="add-button bold">+</button>
      <ul class="list" style="list-style-type: none">
        <li v-for="(todo, i) in exisitingToDo">
          <span>
            {{ i + 1 }}: {{ todo.text }}
          </span>
          <button @click="deleteToDo" class="delete-button">
            X
          </button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      newToDo: '',
      exisitingToDo: [
        { text: 'New Coding Project', id: 0 },
        { text: 'Go to ballet', id: 1 },
        { text: 'Date Night', id: 2 },
      ]
    }
  },
  methods: {
    add() {
      this.exisitingToDo.push({
        text: this.newToDo,
        id: new Date().valueOf()
      }),
        this.newToDo = ''
    },
    deleteToDo(i) {
      this.exisitingToDo.splice(i, 1)
    }
  }
}
</script>

<style></style>
