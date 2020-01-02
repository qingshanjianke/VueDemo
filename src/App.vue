<template>
  <div>
    <input type="text" v-model="title" />
    <br />
    <input type="text" v-model="content" />
    <br />
    <button @click="changgeData">发布</button>
    <div>
      <demo1
        v-for="(item,index) in list"
        :key="index"
        :title="item.title"
        :content="item.content"
        @sevenActive="sevenActiveHandler"
      ></demo1>
    </div>
    <div>
      <Demo2>
        <div slot="title">xixixixixix</div>
      </Demo2>
    </div>
  </div>
</template>

<script>
import Demo1 from '@/components/Demo1.vue'
import Demo2 from '@/components/Demo2.vue'
export default {
  components: {
    Demo1,
    // eslint-disable-next-line vue/no-unused-components
    Demo2
  },
  data: () => ({
    title: '',
    content: '',
    list: []
  }),
  methods: {
    changgeData () {
      this.list.push({
        title: this.title,
        content: this.content
      })
    },
    sevenActiveHandler (data) {
      console.log(data)
    }
  }
}
</script>
