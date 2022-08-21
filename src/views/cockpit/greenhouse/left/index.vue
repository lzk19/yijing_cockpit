<template>
  <div class="box1">
    <img src="@/assets/cockpit/public/左侧导航背景.png" alt="" class="left" />
    <div class="title-box">
      <span>
        <!-- 大标题填写处 -->
        智慧大棚
      </span>
      <img
        src="@/assets/cockpit/public/椭圆1936.png"
        alt=""
        class="left-ellipse"
      />
    </div>

    <!-- 标题盒子1 -->
    <div class="header-box">
      <img
        src="@/assets/cockpit/public/具体内容标题背景.png"
        alt=""
        class="left-content1"
      />
      <!-- 圆点 -->
      <div class="status-point" />
      <!-- 标题 -->
      <span style="margin-left: -1.5vw">
        <!-- 内容标题填写处 -->
        大棚产值
      </span>
      <span
        class="view-all"
        @click="dialogVisible = true"
        style="margin-left: 4vw"
        >查看全部</span
      >
    </div>

    <Dialog v-if="dialogVisible == true"></Dialog>

    <!-- 内容盒子1 -->
    <div class="content-box1">
      <!-- 具体内容填写处 -->
      <el-carousel
        trigger="click"
        height="18.8vh"
        class="carousel"
        :interval="4000"
      >
        <el-carousel-item
          v-for="item in greenhouseList"
          :key="item.index"
          class="carousel-item"
        >
          <img :src="item.url" alt="" />
          <div class="content-title-box">
            <img :src="titleImg" alt="" class="content-title" />
            <span class="title">
              {{ item.greenhouseName }}
            </span>
          </div>
          <div class="page-footer">
            <img :src="footerImg" alt="" class="footer-img" />
            <span class="footer-text"> {{ item.index + 1 }} / {{greenhouseList.length}} </span>
          </div>
        </el-carousel-item>
      </el-carousel>
      
      <!-- <el-carousel
        trigger="click"
        class="carousel"
        :interval="4000"
        height="18.8vh"
      >
        <el-carousel-item
          v-for="item in greenhouseList"
          :key="item.index + 'only1'"
          class="carousel-item"
          v-loading="loading"
        >
          <img :src="item.url" alt="" />
          <div class="content-title-box">
            <img :src="titleImg" alt="" class="content-title" />
            <span class="title">
              {{ item.greenhouseName }}
            </span>
          </div>
          <div class="page-footer">
            <img :src="footerImg" alt="" class="footer-img" />
            <span class="footer-text"> {{ item.index + 1 }} / 4 </span>
          </div>
        </el-carousel-item>
      </el-carousel> -->
    </div>

    <!-- 标题盒子2 -->
    <div class="header-box" style="margin-top: 2vh">
      <img
        src="@/assets/cockpit/public/具体内容标题背景.png"
        alt=""
        class="left-content2"
      />
      <div class="status-point" />
      <span style="margin-left:-1vw">
        <!-- 内容标题填写处 -->
        大棚喷滴灌
      </span>
    </div>
    <!-- 内容盒子2 -->
    <div class="content-box2">
      <!-- 具体内容填写处 -->

      <div class="outer-data-box">
        <div
          class="inner-data-box"
          v-for="item in dripIrrigationList1"
          :key="item.index + 'only1'"
        >
          <img :src="dataBackImg" alt="" class="data-img" />
          <span class="data">{{ item.data }}</span>
          <span class="data-title">{{ item.title }}</span>
        </div>
      </div>

      <div class="outer-data-box">
        <div
          class="inner-data-box"
          v-for="item in dripIrrigationList2"
          :key="item.index + 'only2'"
        >
          <img :src="dataBackImg" alt="" class="data-img" />
          <span class="data">{{ item.data }}</span>
          <span class="data-title">{{ item.title }}</span>
        </div>
      </div>
    </div>

    <!-- 标题盒子3 -->
    <div class="header-box" style="margin-top: 1.5vh">
      <img
        src="@/assets/cockpit/public/具体内容标题背景.png"
        alt=""
        class="left-content3"
      />

      <div class="status-point" />
      <span style="margin-left:0.4vw">
        <!-- 内容标题填写处 -->
        大棚占地面积排名
      </span>
    </div>
    <!-- 内容盒子3 -->
    <div class="content-box3">
      <!-- 具体内容填写处 -->
      <!-- 排名 -->
      <div
        class="area-box"
        v-for="(item, index) in greenhouseList.slice(0, 5)"
        :key="index + 'only2'"
      >
        <span :class="indexStyle[index]">
          {{ index + 1 }}
        </span>
        <span class="type">
          {{ item.greenhouseName }}
        </span>
        <span class="area"> 占地面积：{{ item.greenhouseArea }} </span>
        <div class="percentage-box">
          <span class="percentage"> {{ item.greenhouseAreaPercentage }}% </span>
          <span class="percentage-text">
            {{ percentageText }}
          </span>
        </div>
        <el-progress
          :text-inside="true"
          :show-text="false"
          :stroke-width="6"
          :color="item.progressColor"
          :percentage="item.greenhouseAreaPercentage"
          class="progress"
        >
        </el-progress>
      </div>
    </div>
  </div>
</template>

<script>
import Dialog from "../dialog/index.vue";
export default {
  components: {
    Dialog,
  },
  data() {
    return {
      dialogVisible: false,
      percentageText: "总占比率",
      loading: true,
      progressColor:['progressColor1','progressColor2','progressColor3','progressColor4','progressColor5',],
      titleImg: require("../../../../assets/cockpit/greenhouse/左一内容标题.png"),
      dataBackImg: require("../../../../assets/cockpit/greenhouse/左二数据外框.png"),
      footerImg: require("../../../../assets/cockpit/greenhouse/页脚.png"),
      indexStyle: [
        "indexStyle1",
        "indexStyle2",
        "indexStyle3",
        "indexStyle4",
        "indexStyle5",
      ],
      dripIrrigationList1: [
        { index: 0, data: "34.9℃", title: "温度_1" },
        { index: 1, data: "21.9%RH", title: "湿度_1" },
        { index: 2, data: "6768.0lux", title: "光照" },
      ],
      dripIrrigationList2: [
        { index: 0, data: "22.7℃", title: "土壤温度_1" },
        { index: 1, data: "44.2%RH", title: "土壤湿度_1" },
        { index: 2, data: "0.0℃", title: "土壤温度_2" },
      ],
      greenhouseList: [
        {
          index: 0,
          greenhouseName: "蔬菜大棚",
          greenhouseArea: 460,
          greenhouseAreaPercentage: 47.7,
          url: require("../../../../assets/cockpit/示例图片/1.jpg"),
          progressColor:'#00ff00'
        },
        {
          index: 1,
          greenhouseName: "玉米基地",
          greenhouseArea: 306,
          greenhouseAreaPercentage: 31.2,
          url: require("../../../../assets/cockpit/示例图片/2.jpg"),
          progressColor:'#00BFFF'
        },
        {
          index: 2,
          greenhouseName: "水稻基地",
          greenhouseArea: 148,
          greenhouseAreaPercentage: 10.5,
          url: require("../../../../assets/cockpit/示例图片/3.jpg"),
          progressColor:'#BA55D3'
        },
        {
          index: 3,
          greenhouseName: "茭白基地",
          greenhouseArea: 63,
          greenhouseAreaPercentage: 7.5,
          url: require("../../../../assets/cockpit/示例图片/4.jpg"),
          progressColor:'lightgray'
        },
        {
          index: 4,
          greenhouseName: "水果基地",
          greenhouseArea: 42,
          greenhouseAreaPercentage: 4.5,
          url: require("../../../../assets/cockpit/示例图片/5.jpg"),
          progressColor:'lightgray'
        },
      ],
    };
  },
  mounted(){
    this.$bus.$on('dialogState',this.dialogUpdate)
  },
  methods:{
    dialogUpdate(data){
      this.dialogVisible = data
    }
  }
};
</script>


<style lang="scss" scoped>
.left {
  position: absolute;
  z-index: -1;
  width: 21.5vw;
  height: 90vh;
  margin-left: -0.5vw;
}
img {
  // 解决图片失真
  image-rendering: -moz-crisp-edges; /* Firefox */
  image-rendering: -o-crisp-edges; /* Opera */
  image-rendering: -webkit-optimize-contrast; /*Webkit (non-standard naming) */
  image-rendering: crisp-edges;
  -ms-interpolation-mode: nearest-neighbor; /* IE (non-standard property) */
}
.box1 {
  pointer-events: auto;
  width: 21.5vw;
  height: 90vh;
  margin-left: 3.5vw;
  margin-top: 5vh;
  display: flex;
  flex-direction: column;
  .title-box {
    margin-left: 0.5vw;
    margin-top: 4vh;
    width: 4.8vw;
    height: 3vh;
    margin-bottom: 1.5vh;
    position: relative;
    span {
      font-size: 0.83vw;
      font-family: SourceHanSansCN;
      font-weight: bold;
      color: #0199e8;
    }
    .left-ellipse {
      width: 100%;
      position: absolute;
      left: 50%;
      top: 90%;
      transform: translate(-50%);
    }
  }
  .header-box {
    margin-top: -1vh;
    margin-left: 0.5vw;
    height: 4vh;
    display: flex;
    align-items: center; //垂直
    width: 21.9vw;
    img {
      position: absolute;
      width: 19vw;
      height: 4vh;
      z-index: -1;
    }
    .status-point {
      position: absolute;
      width: 5px;
      height: 5px;
      background: #d5f9ff;
      border-radius: 50%;
      margin-left: 0.75vw;
    }
    span {
      line-height: 4vh;
      height: 4vh;
      width: 10vw;
      font-size: 0.83vw;
      font-family: Alibaba PuHuiTi;
      font-weight: bold;
      color: #ffffff;
    }
    .view-all {
      text-align: center;
      line-height: 2.5vh;
      // padding-top: -0.5vh;
      width: 4.5vw;
      height: 2.7vh;
      border: #0bb3ef 2px solid;
      border-radius: 2px;
      font-size: 0.83vw;
      font-family: Alibaba PuHuiTi;
      font-weight: bold;
      color: #27caff;
      cursor: pointer;
    }
  }
  .content-box1 {
    width: 18.2vw;
    height: 18.8vh;
    margin-top: 1.5vh;
    .content-title-box {
      position: relative;
      margin-top: -20vh;
      margin-left: -0.3vw;
      width: 5vw;
      height: 4vh;
      display: flex;
      justify-content: center;
      align-items: center;
      .content-title {
        width: 100%;
        height: 100%;
        border: none;
      }
      .title {
        position: absolute;
        text-align: center;
        width: 5vw;
        height: 2.8vh;
        line-height: 2.8vh;
        font-size: 0.75vw;
        font-family: Alibaba PuHuiTi;
        font-weight: bold;
        color: #ebf6ff;
      }
    }

    .page-footer {
      margin-top: 12.9vh;
      margin-left: 14.6vw;
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 2.7vw;
      height: 3vh;
      .footer-img {
        border: #27c9fe 1px solid;
        width: 2.7vw;
        height: 3vh;
      }
      .footer-text {
        text-align: center;
        margin-left: -2.7vw;
        width: 2.7vw;
        height: 3vh;
        font-size: 0.75vw;
        font-family: Alibaba PuHuiTi;
        font-weight: bold;
        color: #ebf6ff;
        line-height: 3vh;
      }
    }

    .carousel {
      border-radius: 10px;
      margin-left: 0.8vw;
      // z-index: 2;
      border: #27c9fe 2px solid;
    }
    img {
      width: 100%;
      height: 100%;
      border-radius: 10px;
      cursor: pointer;
    }

    // 改变指示器为圆点
    :deep(.el-carousel__indicator--horizontal .el-carousel__button) {
      width: 10px;
      height: 10px;
      background: transparent;
      border: 1px solid #ffffff;
      border-radius: 50%;
      opacity: 0.5;
    }
    :deep(.el-carousel__indicator--horizontal.is-active .el-carousel__button) {
      width: 10px;
      height: 10px;
      background: #ffffff;
      border-radius: 50%;
      opacity: 1;
    }
  }

  .content-box2 {
    // background: black;
    width: 21vw;
    height: 16.5vh;
    margin-top: 0.5vh;
    .outer-data-box {
      // margin-left: 1vw;
      margin-top: 0.5vh;
      width: 18.2vw;
      display: flex;
      .inner-data-box {
        margin-left: 0.7vw;
        height: 7vh;
        width: 5.6vw;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        .data-img {
          width: 5.6vw;
          height: 7vh;
        }
        .data {
          // margin-left: -4vw;
          text-align: center;
          margin-top: -6vh;
          width: 4.3vw;
          height: 1.5vh;
          font-size: 1vw;
          font-family: DINPro;
          font-weight: bold;
          color: #ffffff;
        }
        .data-title {
          text-align: center;
          margin-top: 2vh;
          width: 5vw;
          height: 1.5vh;
          font-size: 0.9vw;
          font-family: Microsoft YaHei;
          font-weight: 400;
          color: #c3f4fe;
          line-height: 1.5vh;
        }
      }
    }

    // 具体内容里的其他文字(非数据)
    span {
      font-size: 0.83vw;
      font-family: Microsoft YaHei;
      font-weight: 400;
      color: #88c4f3;
    }
  }

  .content-box3 {
    width: 20vw;
    height: 26vh;
    margin-top: 1vh;
    .area-box {
      width: 20vw;
      height: 5.2vh;
      margin-top: 0.2vh;
      .indexStyle1 {
        color: red;
        font-style: italic;
        font-size: 1.1vw;
        margin-left: -5vw;
      }
      .indexStyle2 {
        color: #00ff00;
        font-style: italic;
        font-size: 1.1vw;
        margin-left: -5vw;
      }
      .indexStyle3 {
        color: #00bfff;
        font-style: italic;
        font-size: 1.1vw;
        margin-left: -5vw;
      }
      .indexStyle4 {
        color: lightgray;
        font-style: italic;
        font-size: 1.1vw;
        opacity: 0.2;
        margin-left: -5vw;
      }
      .indexStyle5 {
        color: lightgray;
        font-style: italic;
        font-size: 1.1vw;
        opacity: 0.2;
        margin-left: -5vw;
      }
      .type {
        margin-left: 0.5vw;
        height: 2vh;
        font-size: 1.1vw;
        font-family: SourceHanSansCN;
        font-weight: bold;
        color: #aad4ff;
        line-height: 2.5vh;
      }
      .area {
        margin-left: 1vw;
        height: 1.5vh;
        font-size: 0.73vw;
        font-family: SourceHanSansCN;
        font-weight: bold;
        color: #95afd2;
        line-height: 2.5vh;
      }
      .percentage-box {
        display: flex;
        flex-direction: column;
        margin-left: 15vw;
        margin-top: -3vh;
        .percentage {
          width: 3.4vw;
          font-size: 1.2vw;
          font-family: SourceHanSansCN;
          font-weight: bold;
          color: #0fbdff;
          line-height: 2.5vh;
        }
        .percentage-text {
          margin-top: -0.5vh;
          width: 4vw;
          font-size: 0.6vw;
          font-family: SourceHanSansCN;
          font-weight: bold;
          color: #95afd2;
          line-height: 2.5vh;
        }
      }
      .progress {
        margin-left: 0.5vw;
        width: 14vw;
        margin-top: -1.5vh;
        border: 1px solid #9999ff;
        border-radius: 10px;
      }

      .progressStyle4,
      .progressStyle5 {
        opacity: 0.2;
      }
      :deep(.el-progress-bar__outer) {
        background-color: transparent;
      }
    }
  }
}
</style>
