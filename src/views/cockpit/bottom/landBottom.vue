<template>
  <img src="@/assets/cockpit/public/底部框架.png"
       class="bottom-box"
       alt="">

  <div class="btn1-box">
    <img src="@/assets/cockpit/public/底部左1按钮未点.png"
         alt=""
         class="bottom-left1">
    <span class="title">概况</span>
  </div>

  <div class="btn2-box">
    <img src="@/assets/cockpit/public/底部中1按钮未点.png"
         alt=""
         class="bottom-middle1">
    <span class="title">智慧大棚</span>
  </div>

  <div class="btn3-box">
    <img src="@/assets/cockpit/public/底部中2按钮未点.png"
         alt=""
         class="bottom-middle2C">
    <span class="title">农业产业</span>
  </div>

  <div class="btn4-box">
    <img src="@/assets/cockpit/public/底部右1按钮已点.png"
         alt=""
         class="bottom-right1">
    <span class="title">土地管理</span>
  </div>

</template>

<script setup>


</script>

<style lang="scss" scoped>
img {
  // 解决图片失真
  image-rendering: -moz-crisp-edges; /* Firefox */
  image-rendering: -o-crisp-edges; /* Opera */
  image-rendering: -webkit-optimize-contrast; /*Webkit (non-standard naming) */
  image-rendering: crisp-edges;
  -ms-interpolation-mode: nearest-neighbor; /* IE (non-standard property) */
}
.bottom-box {
  // position: absolute;
  height: 7.5vh;
  width: 33vw;
  margin-top: 2vh;
  margin-left: -3.8vw;
}

.btn1-box {
  height: 4.1vh;
  width: 8.2vw;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: -31vw;
  margin-top: 2vh;
  .bottom-left1 {
    height: 3vh;
    width: 6.2vw;
  }
  .title {
    line-height: 4.1vh;
    text-align: center;
    height: 4.1vh;
    width: 4.8vw;
    margin-left: -5vw;
    font-size: 1.1vw;
    font-family: Alibaba PuHuiTi;
    font-weight: 400;
    color: #ffffff;
  }
}

.btn2-box {
  height: 3vh;
  width: 5.4vw;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 2vh;
  .bottom-middle1 {
    height: 3vh;
    width: 5.4vw;
  }
  .title {
    line-height: 3vh;
    text-align: center;
    height: 3vh;
    width: 5.4vw;
    margin-left: -5.3vw;
    font-size: 1.1vw;
    font-family: Alibaba PuHuiTi;
    font-weight: 400;
    color: #ffffff;
  }
}
.btn3-box {
  height: 3vh;
  width: 5.4vw;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 0.9vw;
  margin-top: 2vh;
  .bottom-middle2C {
    height: 3vh;
    width: 5.4vw;
  }
  .title {
    line-height: 3vh;
    margin-top: -0.5vh;
    text-align: center;
    width: 5.4vw;
    margin-left: -5.3vw;
    font-size: 1.1vw;
    font-family: Alibaba PuHuiTi;
    font-weight: 400;
    color: #ffffff;
  }
}

.btn4-box {
  height: 4.2vh;
  width: 8.2vw;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: -0.8vw;
  margin-top: 2.2vh;
  .bottom-right1 {
    height: 4.2vh;
    width: 8.2vw;
  }
  .title {
    margin-left: -7vw;
    margin-top: -0.5vh;
    text-align: center;
    line-height: 4.1vh;
    height: 4.1vh;
    width: 6vw;
    font-size: 1.1vw;
    font-family: Alibaba PuHuiTi;
    font-weight: 400;
    color: #ffffff;
  }
}
</style>