<template>
  <div>
    <h1>{{title}}</h1>
    <p>{{content}}</p>
    <button @click="btnAttion">{{count}}</button>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    },
    content: {
      type: String
    }
  },

  data: () => ({
    // Title: '',
    // Content: ''
    count: 1
  }),
  methods: {
    btnAttion () {
      this.count++
      // eslint-disable-next-line eqeqeq
      if (this.count % 7 == 0) {
        this.$emit('sevenActive', { title: this.title, content: this.content })
      }
    }
  }
}
</script>
