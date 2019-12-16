<template>
  <div class="wall">
    <div class="top">
      <div class="left">
        <div class="row1">
          <img class="qinImg" :src="qinImg" alt="">
        </div>
        <div class="row2">
          <img class="happyImg" :src="happyImg" alt="">
        </div>
      </div>

      <div class="right">
        <img class="duilianImg" :src="duilianImg" alt="">
      </div>
    </div>
    <div class="swiper">
      <vue-baberrage
        :is-show="barrageIsShow"
        :barrage-list="barrageList"
        :loop="barrageLoop"
      />
    </div>
  </div>
</template>

<script>
import { MESSAGE_TYPE } from 'vue-baberrage'
export default {
  data() {
    return {
      happyImg: require('./imgs/happy.png'),
      duilianImg: require('./imgs/duilian.png'),
      qinImg: require('./imgs/qin.png'),
      img: require('./imgs/1.jpg'),
      msg: 'Hello vue-baberrage',
      barrageIsShow: true,
      currentId: 0,
      barrageLoop: false,
      barrageList: []
    }
  },

  created() {
    this.getData()
    // this.getList()
  },

  mounted() {},

  methods: {
    getData() {
      setInterval(() => {
        this.addToList()
      }, 100)
    },

    getList() {
      for (var i = 0; i < 300; i++) {
        this.addToList()
      }
    },

    addToList() {
      this.barrageList.push({
        id: ++this.currentId,
        avatar: this.img,
        msg: this.msg,
        time: 10,
        type: MESSAGE_TYPE.NORMAL
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.wall {
  height: 100%;
  background: #fb5232 url("./imgs/bg.png") no-repeat;
  background-size: 100% 100%;
  padding-top: 110px;

  .top {
    padding-left: 47px;
    .left {
      .row1,
      .row2 {
        text-align: right;
        margin-right: 127px;
      }
      img {
        display: inline-block;
      }
      .happyImg {
        width: 363px;
        height: 54px;
      }
      .qinImg {
        width: 137px;
        height: 24px;
      }
    }
    .right {
      text-align: right;
      .duilianImg {
        display: inline-block;
        width: 79px;
        height: 347px;
        margin-top: 0;
        margin-right: 12px;
      }
    }
  }

  .swiper {
    position: absolute;
    left: 0;
    right: 0;
    top: 200px;
    bottom: 150px;
  }
}
</style>
