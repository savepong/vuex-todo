<template>
  <div>
    <form @submit.prevent="save()">
      <input type="text" v-model="inputText" />
      <button type="submit">Save</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'InputForm',
  data () {
    return {
      inputText: ''
    }
  },
  methods: {
    save () {
      this.$emit('onSave', this.inputText)
    }
  }
}
</script>
