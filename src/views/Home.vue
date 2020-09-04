<template>
  <div class="home">
    <van-list
      v-model="loading"
      :finished="finished"
      finished-text="没有更多了"
      @load="onLoad"
    >
      <van-cell v-for="item in list" :key="item" @click="handleToDetail(item.id)">
        <div class="list">
          <div class="left">
            <img :src="item.src" alt="">
          </div>
          <div class="rigth">
            <div class="title">{{item.title}}</div>
            <div class="create-time">{{item.createTime}}</div>
          </div>
        </div>
      </van-cell>
    </van-list>
  </div>
</template>

<script>
import { List, Cell } from 'vant'
export default {
  name: 'Home',
  components: {
    [List.name]: List,
    [Cell.name]: Cell
  },
  data () {
    return {
      list: [],
      loading: false,
      finished: false
    }
  },
  methods: {
    onLoad () {
      fetch('/article/lists')
        // .then(res => res.json())
        .then(res => {
          if (res.status === 200) {}
        })
      setTimeout(() => {
        for (let i = 0; i < 10; i++) {
          this.list.push(this.list.length + 1)
        }
        this.loading = false
        if (this.list.length >= 40) {
          this.finished = true
        }
      }, 1000)
    },
    handleToDetail (id) {
      this.$router.push({
        path: '/detail',
        query: {
          id: id
        }
      })
    }
  }
}
</script>

<style scoped>
  .list {
    display: flex;
    flex-direction: row;
  }
  .list .left, img {
    width: 150px;
    height: 100px;
    border-radius: 10px;
  }
  .list .rigth {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    margin-left: 15px;
  }
  .list .rigth .title {
    font-size: 18px;
  }
  .list .rigth .create-time {
    font-size: 12px;
    color: #666;
  }
</style>
