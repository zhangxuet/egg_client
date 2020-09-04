<template>
  <div class="detail">
    <div class="title">{{}}</div>
    <div class="summary">{{}}</div>
    <div class="content">{{}}</div>
    <div class="create-time">{{}}</div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      detail: {}
    }
  },
  methods: {}
}
</script>

<style scoped>
.detail {
  padding: 20px;
  text-align: left;
}
.detail .title {
  font-size: 25px;
  padding-bottom: 20px;
}
.detail .summary {
  padding: 20px;
  background: #eeeeee;
}
.detail .content {
  padding: 20px;
  text-indent: 2em;
  line-height: 200%;
}
.detai .create-time {
  color: #999;
  text-align: right;
}
</style>
