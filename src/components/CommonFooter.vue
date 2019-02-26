<template>
  <footer>
    <div class="navImg colorBlack">
      <img mode="widthFix" src="../../static/images/index/more.jpg" alt="">
    </div>
    <div class="collapse" @click="showAddress">
      <div class="collapseHeader">
        <div class="collapseIconGroup">
          <img mode="widthFix" src="../../static/images/index/icon/icon1.png" alt="">
          <p>婚礼场地</p>
        </div>
        <span>+</span>
      </div>
      <div class="collapseContent" v-if="addressBool">
        <div class="collapseIconGroup" v-for="(item,index) in AddressList" :key="index">
          <i-icon type="enter" size="16" color="#a18c61" />
          <p>{{item.content}}</p>
        </div>
      </div>
    </div>
    <div class="collapse" @click="showService">
      <div class="collapseHeader">
        <div class="collapseIconGroup">
          <img mode="widthFix" src="../../static/images/index/icon/icon2.png" alt="">
          <p>婚礼服务</p>
        </div>
        <span>+</span>
      </div>
      <div class="collapseContent" v-if="serviceBool">
        <div class="collapseIconGroup" v-for="(item,index) in serviceList" :key="index">
          <i-icon type="enter" size="16" color="#a18c61" />
          <p>{{item.content}}</p>
        </div>
      </div>
    </div>
    <div class="collapse">
      <div class="collapseHeader">
        <div class="collapseIconGroup">
          <img mode="widthFix" src="../../static/images/index/icon/icon3.png" alt="">
          <p>婚宴料理</p>
        </div>
      </div>
    </div>
    <div class="collapse">
      <div class="collapseHeader">
        <div class="collapseIconGroup">
          <img mode="widthFix" src="../../static/images/index/icon/icon4.png" alt="">
          <p>策划布置</p>
        </div>
      </div>
    </div>
    <div class="collapse" @click="showRoom">
      <div class="collapseHeader">
        <div class="collapseIconGroup">
          <img mode="widthFix" src="../../static/images/index/icon/icon2.png" alt="">
          <p>门店场馆</p>
        </div>
        <span>+</span>
      </div>
      <div class="collapseContent" v-if="roomBool">
        <div class="collapseIconGroup" v-for="(item,index) in roomList" :key="index">
          <i-icon type="enter" size="16" color="#a18c61" />
          <p>{{item.content}}</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      more: {
        address: "婚礼场地"
      },
      AddressList: [
        { content: "场地特色" },
        { content: "豪华宴会厅" },
        { content: "证婚仪式堂" },
        { content: "婚纱礼服馆" }
      ],
      serviceList: [{ content: "专业团队" }, { content: "个性礼遇" }],
      roomList: [
        { content: "黄兴公园店" },
        { content: "滨江店" },
        { content: "五角场店" },
        { content: "吴中店" },
        { content: "世博江景店" },
        { content: "世博旗舰店" },
        { content: "繁兴店(即将开张,火热预售中)" },
        { content: "海岛婚礼店" },
      ],
      addressBool: false,
      serviceBool: false,
      roomBool: false
    };
  },
  methods: {
    showAddress() {
      this.addressBool = !this.addressBool;
    },
    showService() {
      this.serviceBool = !this.serviceBool;
    },
    showRoom() {
      this.roomBool = !this.roomBool;
    }
  }
};
</script>

<style lang="scss" scoped>
footer {
  width: 100%;
  background-color: black;
  padding-bottom: 200rpx;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .navImg {
    height: 80rpx;
    width: 100%;
    background-color: black;
    border-bottom: 8rpx solid #a18c61;
    image {
      width: 100%;
    }
  }
  .collapse {
    width: 100%;
    background-color: #000;
    border-bottom: 2rpx solid #a18c61;
    .collapseHeader {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 80rpx;
      width: 100%;
      background-color: #000;
      .collapseIconGroup {
        margin-left: 80rpx;
        display: flex;
        justify-content: center;
        align-items: center;
        img {
          width: 30rpx;
        }
        p {
          padding-left: 20rpx;
          width: 200rpx;
          color: #fff;
        }
      }
      span {
        color: #a18c61;
        margin-right: 40rpx;
        font-size: 60rpx;
      }
    }
    .collapseContent {
      display: flex;
      flex-direction: column;
      width: 100%;
      background-color: #000;
      .collapseIconGroup {
        height: 80rpx;
        margin-left: 80rpx;
        display: flex;
        align-items: center;
        img {
          width: 30rpx;
        }
        p {
          padding-left: 40rpx;
          width: 200rpx;
          color: #fff;
        }
      }
    }
  }
}
</style>
