<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.time">
        <button @click="itemDone(item.time)">Done</button>
        {{ item.text | capitalize}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  props: {
    items: {
      type: Array
    }
  },
  methods: {
    itemDone (id) {
      this.$emit('onItemDone', id)
    }
  },
  filters: {
    capitalize (value) {
      return value.toUpperCase()
    }
  }
}
</script>
