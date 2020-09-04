<template>
  <div class="about">
    <van-uploader v-model="fileList" :after-read="afterRead" :max-count="1" />
    <van-cell-group>
      <van-field v-model="title" label="文章标题" placeholder="请输入文章标题" />
      <van-field v-model="summary" label="文章简介" placeholder="请输入文章简介" />
      <van-field v-model="content" label="文章内容" placeholder="请输入文章内容" type="textarea" autosize/>
    </van-cell-group>
    <van-button block type="primary" @click="handleAdd">提交</van-button>
  </div>
</template>

<script>
import { Uploader, CellGroup, Field, Button } from 'vant'
export default {
  components: {
    [Uploader.name]: Uploader,
    [CellGroup.name]: CellGroup,
    [Field.name]: Field,
    [Button.name]: Button
  },
  data () {
    return {
      fileList: [],
      title: '',
      summary: '',
      content: '',
      img: ''
    }
  },
  methods: {
    afterRead (file) {
      console.log(file)
      this.img = file.content
    },
    handleAdd () {
      const param = {
        title: this.title,
        summary: this.summary,
        content: this.content,
        img: this.img
      }
      console.log(param)
    }
  }
}
</script>

<style scoped>
  .about {
    margin-top: 60px;
  }
  .van-button {
    position: absolute;
    bottom: 50px;
  }
</style>
