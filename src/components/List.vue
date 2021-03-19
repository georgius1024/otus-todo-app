<template>
    <ul>
      <li v-for="item in items" :key="item">
        <span class="float-right" @click="removeItem(item)">&times;</span>
        <span v-text="item"/>
      </li>
    </ul>
</template>
<script>
export default {
  name: 'List',
  props: {
    items: {
      type: Array,
      required: true
    }
  },
  methods: {
    removeItem(item) {
      this.$emit('remove', item)
    }
  }
}
</script>
<style scoped>
ul {
  list-style-type: none;
  text-align: left;
  margin: 0;
  padding: 0;
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
