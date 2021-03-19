<template>
  <section>
    <input v-model="itemName" placeholder="Введите задачу">
    <button @click="addItem">Добавить</button>
  </section>
</template>

<script>
export default {
  name: "Input",
  data() {
    return {
      itemName: ""
    };
  },
  methods: {
    addItem() {
      this.$emit('add', this.itemName)
      this.itemName = ""
    }
  }
};
</script>
<style scoped>
input {
  padding: 12px;
}
button {
  padding: 12px;
}
</style>
