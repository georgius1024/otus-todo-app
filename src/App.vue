<template>
  <div id="app">
    <TodoHeader>ToDo App</TodoHeader>
    <hr>
    <TodoInput @add="addItem($event)" />
    <hr>
    <TodoList :items="items" @remove="removeItem($event)" />
  </div>
</template>

<script>
import TodoInput from './components/Input.vue'
import TodoList from './components/List.vue'
import TodoHeader from './components/Header.vue'

export default {
  name: "App",
  components: {
    TodoInput,
    TodoList,
    TodoHeader
  },
  data() {
    return {
      items: [
        "Создать поле ввода в itemName",
        "Добавить кнопку вызывающую метод addItem",
        "Вывести список items",
        "** Добавить возможность удаления, использовать метод removeItem"
      ]
    };
  },
  methods: {
    addItem(itemName) {
      if (itemName && this.items.indexOf(itemName) === -1) {
        this.items.push(itemName);
      }
    },
    removeItem(item) {
      this.items = this.items.filter(e => e !== item);
    }
  }
};
</script>

<style scoped>
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 500px;
  margin: 32px auto;
  box-shadow: 5px 5px 5px 0px rgba(0, 0, 0, 0.75);
  border: 1px solid #aaa;
  padding: 32px;
}
hr {
  margin: 12px 0;
  border: none;
  border-top: 1px solid #aaa;
}
</style>