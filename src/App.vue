<template>
  <div id="app">
    <h1>ToDo App</h1>
    <hr>
    <section>
      <input v-model="itemName" placeholder="Введите задачу">
      <button @click="addItem">Добавить</button>
    </section>
    <hr>
    <ul>
      <li v-for="item in items" :key="item">
        <span class="float-right" @click="removeItem(item)">&times;</span>
        <span v-text="item"/>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      itemName: "",
      items: [
        "Создать поле ввода в itemName",
        "Добавить кнопку вызывающую метод addItem",
        "Вывести список items",
        "** Добавить возможность удаления, использовать метод removeItem"
      ]
    };
  },
  methods: {
    addItem() {
      if (this.itemName && this.items.indexOf(this.itemName) === -1) {
        this.items.push(this.itemName);
        this.itemName = "";
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
input {
  padding: 12px;
}
button {
  padding: 12px;
}
ul {
  list-style-type: none;
  text-align: left;
}
ul > li {
  border-top: 1px solid #333;
  padding: 12px;
}
ul > li:last-child {
  border-bottom: 1px solid #333;
}

.float-right {
  float: right;
  cursor: pointer;
}
</style>