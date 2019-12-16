<template>
  <div class="wall">
    <vue-baberrage
      :is-show="barrageIsShow"
      :barrage-list="barrageList"
      :loop="barrageLoop"
    />
  </div>
</template>

<script>
import { MESSAGE_TYPE } from 'vue-baberrage'
export default {
  data() {
    return {
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
  },

  methods: {
    getData() {
      setInterval(() => {
        this.addToList()
      }, 100)
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

<style lang="scss" scoped></style>
