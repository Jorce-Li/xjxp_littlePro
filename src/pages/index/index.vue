<template>
  <div class="index">
    <CommonHeader></CommonHeader>
    <div class="canClickImg">
      <img mode="widthFix" src="../../../static/images/index/index.jpg" alt="">
    </div>
    <div class="noClickImg">
      <img mode="widthFix" src="../../../static/images/index/index2.jpg" alt="">
    </div>
    <div class="navImg">
      <img mode="widthFix" src="../../../static/images/index/nav1.png" alt="">
      <ImgSwiper :imgUrls="activityUrls"></ImgSwiper>
    </div>
    <div class="navImg colorGray">
      <img mode="widthFix" src="../../../static/images/index/nav2.png" alt="">
    </div>
    <div class="canClickImg colorGray">
      <img mode="widthFix" :src="item.src" @click="imgGo(item.url)" v-for="(item,index) in ImgList" alt="" :key="index">
    </div>
    <div class="navImg colorGray">
      <img mode="widthFix" src="../../../static/images/index/nav3.png" alt="">
      <ImgSwiper :imgUrls="lateNewsImgUrls"></ImgSwiper>
    </div>
    <div class="navImg colorGray">
      <img mode="widthFix" src="../../../static/images/index/index3.png" alt="">
    </div>
    <div class="inputGroup">
      <div class="inputCommon" @click="InputDateShow">
        <p>{{order.date}}</p>
        <i-icon class="inputIcon" size="18" type="unfold" />
      </div>
      <div class="inputCommon">
        <p>{{order.size}}</p>
        <i-icon class="inputIcon" size="18" type="unfold" />
      </div>
      <div class="inputCommon">
        <p>{{order.price}}</p>
        <i-icon class="inputIcon" size="18" type="unfold" />
      </div>
      <div class="inputCommon">
        <input type="text" placeholder="您的手机号码">
      </div>
      <div class="inputCommon">
        <img mode="widthFix" src="../../../static/images/index/button.png" alt="">
      </div>
    </div>
    <CommonFooter></CommonFooter>
    <FixedFooter></FixedFooter>

    <i-action-sheet :visible="InputDateBool" :actions="InputDateActions" show-cancel @cancel="InputDateCancel" @click="InputDateSelect" />
  </div>
</template>

<script>
import CommonHeader from "@/components/CommonHeader";
import CommonFooter from "@/components/CommonFooter";
import FixedFooter from "@/components/FixedFooter";
import ImgSwiper from "@/components/ImgSwiper";

export default {
  data() {
    return {
      motto: "Hello miniprograme",
      userInfo: {
        nickName: "mpvue",
        avatarUrl: "http://mpvue.com/assets/logo.png"
      },
      order: {
        date: "半年内",
        size: "10桌以下",
        price: "10万以下",
        phone: null
      },
      current: "",
      InputDateBool: false,
      InputDateActions: [
        { value: 1, name: "半年内" },
        { value: 2, name: "半年到一年" },
        { value: 3, name: "一年以后" }
      ],
      inputList: [{ value: 1, name: "测试" }],
      activityUrls: [
        require("../../../static/images/index/activity/aty1.png"),
        require("../../../static/images/index/activity/aty2.png")
      ],
      lateNewsImgUrls: [
        require("../../../static/images/index/news/news1.png"),
        require("../../../static/images/index/news/news2.png")
      ],
      ImgList: [
        {
          src: require("../../../static/images/index/img1.png"),
          url: ""
        },
        {
          src: require("../../../static/images/index/img2.png"),
          url: ""
        },
        {
          src: require("../../../static/images/index/img3.png"),
          url: ""
        },
        {
          src: require("../../../static/images/index/img4.png"),
          url: ""
        },
        {
          src: require("../../../static/images/index/img5.png"),
          url: ""
        },
        {
          src: require("../../../static/images/index/img6.png"),
          url: ""
        },
        {
          src: require("../../../static/images/index/img7.png"),
          url: ""
        }
      ]
    };
  },

  components: {
    CommonHeader,
    CommonFooter,
    FixedFooter,
    ImgSwiper: ImgSwiper
  },

  methods: {
    inputChange() {},
    InputDateShow() {
      this.InputDateBool = true;
    },
    InputDateCancel() {
      this.InputDateBool = false;
    },
    InputDateSelect(e) {
      // console.log(e.mp._relatedInfo.anchorTargetText);
      this.order.date = e.mp._relatedInfo.anchorTargetText
      this.InputDateBool = false;
    }
  },

  created() {
    // let app = getApp()
  }
};
</script>

<style lang="scss" scoped>
.index {
  .canClickImg {
    width: 100%;
    img {
      width: 100%;
    }
  }
  .noClickImg {
    width: 100%;
    height: 1000rpx;
    img {
      width: 100%;
    }
  }
  .navImg {
    width: 100%;
    image {
      width: 100%;
    }
  }
  .colorGray {
    background-color: rgb(226, 226, 223);
  }
  .queryPrice {
    width: 100%;
  }
  .inputGroup {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: rgb(226, 226, 223);
    padding-bottom: 80rpx;
    .inputCommon {
      width: 65%;
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 40rpx;
      p {
        width: 100%;
        color: #7b7b7b;
        height: 80rpx;
        line-height: 80rpx;
        padding: 10rpx 20rpx;
        font-size: 32rpx;
        border-radius: 10rpx;
        background-color: #eee;
      }
      input {
        width: 100%;
        height: 80rpx;
        line-height: 80rpx;
        padding: 10rpx 20rpx;
        font-size: 32rpx;
        border-radius: 10rpx;
        background-color: #eee;
        color: #c4c4c4;
      }
      .inputIcon {
        position: absolute;
        right: 10rpx;
      }
    }
  }
}
</style>
