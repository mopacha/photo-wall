<template>
  <div class="wall">
    <div class="container">
      <span v-for="(item, index) in imgList" :key="index" class="imgItem">
        <img :src="item.url">
      </span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      imgList: []
    }
  },

  created() {
    this.getImg()
  },

  methods: {
    getImg() {
      const reorderKeys = [
        'TB1KIkQKXXXXXaOXpXXXXXXXXXX-450-300.png',
        'TB1T7oPKXXXXXaUXpXXXXXXXXXX-450-300.png',
        'TB104ZSKXXXXXX2XpXXXXXXXXXX-450-300.png',
        'TB1DlArKXXXXXXiaXXXXXXXXXXX-450-300.jpg',
        'TB1mMZOKXXXXXbpXpXXXXXXXXXX-450-300.png',
        'TB16plLSFXXXXbBapXXXXXXXXXX-200-200.png',
        'TB1F3AxKXXXXXX2XVXXXXXXXXXX-450-300.png',
        'TB1WRIEKXXXXXaPXFXXXXXXXXXX-450-300.png',
        'TB1A0ZtKXXXXXccXVXXXXXXXXXX-450-300.png',
        'TB1RvE1KXXXXXaiXXXXXXXXXXXX-450-300.png',
        'TB15ysvKXXXXXayXVXXXXXXXXXX-450-300.png',
        'TB1aegRKXXXXXXZXpXXXXXXXXXX-450-300.png',
        'TB113QCKXXXXXb2XFXXXXXXXXXX-450-300.png',
        'TB1z2ovKXXXXXaVXVXXXXXXXXXX-450-300.jpg',
        'TB1b0sRKXXXXXaAXpXXXXXXXXXX-450-300.png',
        'TB1H4.ZKXXXXXa3XXXXXXXXXXXX-450-300.png',
        'TB1fE.FKXXXXXX7XFXXXXXXXXXX-450-300.png',
        'TB1_0ZDKXXXXXboXFXXXXXXXXXX-450-300.png',
        'TB1JXAZKXXXXXa2XXXXXXXXXXXX-450-300.png',
        'TB16.A1KXXXXXXuXXXXXXXXXXXX-450-300.png',
        'TB1oXcPKXXXXXbmXpXXXXXXXXXX-450-300.png',
        'TB1uc7KKXXXXXXbXFXXXXXXXXXX-450-300.png',
        'TB1IioWKXXXXXb_XXXXXXXXXXXX-450-300.png',
        'TB13FU0KXXXXXaLXXXXXXXXXXXX-450-300.png',
        'TB14kcOKXXXXXbtXpXXXXXXXXXX-450-300.png',
        'TB1gyw1KXXXXXXGXXXXXXXXXXXX-450-300.png',
        'TB1x6ctKXXXXXbLXVXXXXXXXXXX-450-300.png',
        'TB16eMPKXXXXXaYXpXXXXXXXXXX-450-300.png',
        'TB1857NKXXXXXbNXpXXXXXXXXXX-450-300.png',
        'TB1YisSKXXXXXcCXXXXXXXXXXXX-450-300.png',
        'TB1WL3qKXXXXXbBXVXXXXXXXXXX-450-300.png',
        'TB1M1QVKXXXXXcIXXXXXXXXXXXX-450-300.png',
        'TB1MrcxKXXXXXXCXVXXXXXXXXXX-450-300.png',
        'TB1v2ARKXXXXXX8XpXXXXXXXXXX-450-300.png',
        'TB1U.3oKXXXXXbRaXXXXXXXXXXX-450-300.png',
        'TB1WgIwKXXXXXagXVXXXXXXXXXX-450-300.jpg',
        'TB1I8MTKXXXXXXBXpXXXXXXXXXX-450-300.png',
        'TB1DZcrKXXXXXcVXVXXXXXXXXXX-450-300.png',
        'TB1blaBSFXXXXbqXXXXXXXXXXXX-200-200.png',
        'TB1EEUYKXXXXXaLXXXXXXXXXXXX-450-300.png',
        'TB1qaEtKXXXXXbMXVXXXXXXXXXX-450-300.png',
        'TB1t3oSKXXXXXX3XpXXXXXXXXXX-450-300.png',
        'TB1HZEQKXXXXXavXpXXXXXXXXXX-450-300.png',
        'TB18gwGKXXXXXawXFXXXXXXXXXX-450-300.png',
        'TB11KADKXXXXXaBXFXXXXXXXXXX-450-300.png',
        'TB1xusLKXXXXXcmXpXXXXXXXXXX-450-300.png',
        'TB1Y.ErKXXXXXcFXVXXXXXXXXXX-450-300.png',
        'TB1o3cwKXXXXXapXVXXXXXXXXXX-450-300.png',
        'TB1eFoLKXXXXXcAXpXXXXXXXXXX-450-300.png',
        'TB1VGMPKXXXXXa.XpXXXXXXXXXX-450-300.png',
        'TB17BINKXXXXXbEXpXXXXXXXXXX-450-300.png',
        'TB12uEFKXXXXXaPXFXXXXXXXXXX-450-300.png',
        'TB1C_svKXXXXXaJXVXXXXXXXXXX-450-300.png',
        'TB1zS3JKXXXXXcVXpXXXXXXXXXX-450-300.png',
        'TB1rIsuKXXXXXa5XVXXXXXXXXXX-450-300.png',
        'TB1XiEUKXXXXXcOXXXXXXXXXXXX-450-300.png',
        'TB19hkHKXXXXXXRXFXXXXXXXXXX-450-300.png',
        'TB1i97GKXXXXXavXFXXXXXXXXXX-450-300.png',
        'TB1OhsBKXXXXXcnXFXXXXXXXXXX-450-300.png',
        'TB1NO3OKXXXXXboXpXXXXXXXXXX-450-300.png',
        'TB1gPgQKXXXXXacXpXXXXXXXXXX-450-300.png',
        'TB1p1.2KXXXXXXJXXXXXXXXXXXX-450-300.png',
        'TB1iQ.IKXXXXXXoXFXXXXXXXXXX-450-300.png',
        'TB1YscMKXXXXXcdXpXXXXXXXXXX-450-300.png',
        'TB1WM.UKXXXXXbGXXXXXXXXXXXX-450-300.png',
        'TB1V_IUKXXXXXc8XXXXXXXXXXXX-450-300.png',
        'TB1GkkCKXXXXXb5XFXXXXXXXXXX-450-300.png',
        'TB1xWZOKXXXXXbtXpXXXXXXXXXX-450-300.png',
        'TB1zo7CKXXXXXbBXFXXXXXXXXXX-450-300.png',
        'TB1RrkYKXXXXXX3XXXXXXXXXXXX-450-300.png',
        'TB1.IMKKXXXXXcZXpXXXXXXXXXX-450-300.png',
        'TB16KgVKXXXXXcaXXXXXXXXXXXX-450-300.png',
        'TB103wwKXXXXXb1XFXXXXXXXXXX-450-300.png',
        'TB1WW.KKXXXXXcNXpXXXXXXXXXX-450-300.png',
        'TB1hLMtKXXXXXb1XVXXXXXXXXXX-450-300.png',
        'TB1JccxKXXXXXXRXVXXXXXXXXXX-450-300.png',
        'TB1dEwtKXXXXXbxXVXXXXXXXXXX-450-300.png',
        'TB1HLJVPXXXXXXhXVXXXXXXXXXX-864-864.jpg',
        'TB1l24QPXXXXXbTXVXXXXXXXXXX-750-750.jpg',
        'TB1fIlKPXXXXXalaXXXXXXXXXXX-4912-4912.jpg',
        'TB1V9X7PXXXXXcOXpXXXXXXXXXX-340-340.jpg',
        'TB15YdrPXXXXXaPaVXXXXXXXXXX-750-750.jpg',
        'TB1Y5xWPXXXXXXkXVXXXXXXXXXX-1536-1536.jpg',
        'TB1HNRwPXXXXXa7apXXXXXXXXXX-2048-2048.jpg',
        'TB1BplEPXXXXXc0aXXXXXXXXXXX-750-750.jpg',
        'TB17g4NPXXXXXXoaXXXXXXXXXXX-960-960.jpg',
        'TB10d4CPXXXXXX9apXXXXXXXXXX-180-179.jpg',
        'TB1tA8TPXXXXXabXVXXXXXXXXXX-600-600.jpg',
        'TB15nujPXXXXXXmXXXXXXXXXXXX-518-518.jpg'
      ]
      this.imgList = reorderKeys.map((item, index) => {
        return {
          index,
          url: 'http://img.alicdn.com/tps/' + item,
          content: '新年快乐'
        }
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.wall {
  .container {
    width: 960px;
    height: 450px;
    margin: 60px auto;
    position: relative;
    img {
      height: 120px;
      width: 120px;
    }
  }
  .container .imgItem {
    display: inline-block;
    height: 40px;
    width: 40px;
    position: absolute;
    padding: 10px 10px 15px;
    background: #fff;

    border: 1px solid #ddd;
    -webkit-transition: 1s;
    -moz-transition: 1s;
    transition: 1s;
    z-index: 1;
  }
  .container .imgItem:hover {
    -webkit-transform: rotate(0deg);
    -moz-transform: rotate(0deg);
    transform: rotate(0deg);
    -webkit-transform: scale(1.1);
    -moz-transform: scale(1.1);
    transform: scale(1.1);
    -webkit-box-shadow: 5px 5px 5px #ddd;
    -moz-box-shadow: 5px 5px 5px #ddd;
    box-shadow: 5px 5px 5px #ddd;
    z-index: 2;
    cursor: pointer;
  }
  .imgItem:nth-child(n) {
    top: 0px;
    left: 400px;
    -webkit-transform: rotate(-5deg);
    -moz-transform: rotate(-5deg);
    transform: rotate(-5deg);
  }
  .imgItem:nth-child(n + 1) {
    top: 0px;
    left: 600px;
    -webkit-transform: rotate(-20deg);
    -moz-transform: rotate(-20deg);
    transform: rotate(-20deg);
  }
  .imgItem:nth-child(n + 2) {
    bottom: 0;
    right: 0;
    -webkit-transform: rotate(5deg);
    -moz-transform: rotate(5deg);
    transform: rotate(5deg);
  }
  .imgItem:nth-child(n + 3) {
    bottom: 0;
    left: 300px;
    -webkit-transform: rotate(-10deg);
    -moz-transform: rotate(-10deg);
    transform: rotate(-10deg);
  }
  .imgItem:nth-child(n + 4) {
    bottom: 0;
    left: 0;
    -webkit-transform: rotate(-10deg);
    -moz-transform: rotate(-10deg);
    transform: rotate(-10deg);
  }
  .imgItem:nth-child(n + 5) {
    top: 0;
    left: 0;
    -webkit-transform: rotate(10deg);
    -moz-transform: rotate(10deg);
    transform: rotate(10deg);
  }
  .imgItem:nth-child(n + 6) {
    top: 0;
    left: 850px;
    -webkit-transform: rotate(20deg);
    -moz-transform: rotate(20deg);
    transform: rotate(20deg);
  }
  .imgItem:nth-child(n + 7) {
    bottom: -20px;
    right: 630px;
    -webkit-transform: rotate(5deg);
    -moz-transform: rotate(5deg);
    transform: rotate(5deg);
  }
  .imgItem:nth-child(n + 8) {
    top: 90px;
    left: 550px;
    -webkit-transform: rotate(15deg);
    -moz-transform: rotate(15deg);
    transform: rotate(15deg);
  }
  .imgItem:nth-child(n + 9) {
    left: 180px;
    top: 20px;
    -webkit-transform: rotate(-10deg);
    -moz-transform: rotate(-10deg);
    transform: rotate(-10deg);
  }
}
</style>
