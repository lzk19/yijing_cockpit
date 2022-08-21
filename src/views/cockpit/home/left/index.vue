<template>
  <div class="box1">
    <img src="@/assets/cockpit/public/左侧导航背景.png" alt="" class="left" />
    <div class="title-box">
      <span>
        <!-- 大标题填写处 -->
        概况
      </span>
      <img
        src="@/assets/cockpit/public/椭圆1936.png"
        alt=""
        class="left-ellipse"
      />
    </div>

    <!-- 标题盒子1 -->
    <div class="header-box" style="margin-top: -1vh">
      <img
        src="@/assets/cockpit/public/具体内容标题背景.png"
        alt=""
        class="left-content1"
      />
      <!-- 圆点 -->
      <div class="status-point" />
      <!-- 标题 -->
      <span class="span1">
        <!-- 内容标题填写处 -->
        基本概况
      </span>
    </div>
    <!-- 内容盒子1 -->
    <div class="content-box1">
      <!-- 具体内容填写处 -->
      <div class="data-box">
        <span
          v-for="item in dataTitleList1"
          :key="item.index+'only1'"
          class="data-title"
        >
          {{ item.title }}
        </span>
        <br>
        <span
          v-for="item in dataTitleList1"
          :key="item.index+'only2'"
          class="data"
        >
          {{ item.data }}
        </span>
      </div>

      <div class="underline-box">
        <img
          :src="item.url"
          alt=""
          v-for="item in underlineList"
          :key="item.index+'only1'"
          class="data-underline"
          style="margin-left: -1.5vw"
        />
      </div>
      <div class="data-box">
        <span
          v-for="item in dataTitleList2"
          :key="item.index+'only1'"
          class="data-title"
        >
          {{ item.title }}
        </span>
        <br>
        <span
          v-for="item in dataTitleList2"
          :key="item.index+'only2'"
          class="data"
        >
          {{ item.data }}
        </span>
      </div>

      <div class="underline-box">
        <img
          :src="item.url"
          alt=""
          class="data-underline"
          style="margin-left: -1.5vw"
          v-for="item in underlineList"
          :key="item.index+'only2'"
        />
      </div>
    </div>

    <!-- 标题盒子2 -->
    <div class="header-box" style="margin-top: -5vh">
      <img
        src="@/assets/cockpit/public/具体内容标题背景.png"
        alt=""
        class="left-content2"
      />
      <div class="status-point" />
      <span>
        <!-- 内容标题填写处 -->
        小镇介绍
      </span>
    </div>
    <!-- 内容盒子2 -->
    <div class="content-box2" v-for="(item, index) in townInfo" :key="index">
      <!-- 具体内容填写处 -->

      <div class="play-box">
        <img
          src="src\assets\cockpit\home\播放按钮.png"
          alt=""
          class="play-btn"
        />
      </div>
      <!-- controls="controls" 显示视频控件 -->
      <video
        src="http://www.w3school.com.cn/i/movie.ogg"
        id="video"
        ref="videoPlay"
      ></video>
      <div class="textArea">
        <span>&nbsp;&nbsp;{{ item.intro }}</span>
      </div>
    </div>
    <!-- 标题盒子3 -->
    <div class="header-box">
      <img
        src="@/assets/cockpit/public/具体内容标题背景.png"
        alt=""
        class="left-content3"
      />

      <div class="status-point" />
      <span>
        <!-- 内容标题填写处 -->
        小镇美景
      </span>
    </div>
    <!-- 内容盒子3 -->
    <div class="content-box3">
      <!-- 具体内容填写处 -->
      <el-carousel
        trigger="click"
        height="16vh"
        class="carousel"
        :interval="4000"
      >
        <el-carousel-item
          v-for="item in imgList"
          :key="item.index"
          class="carousel-item"
        >
          <img :src="item.url" alt="" />
          <div class="page-footer">
            <img :src="item.footerImg" alt="" class="footer-img" />
            <span class="footer-text">
              {{ item.footerText }}
            </span>
          </div>
        </el-carousel-item>
      </el-carousel>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dataTitleList1: [
        {
          index:0,
          title: "人口总数",
          data: "569人",
        },
        {
          index:1,
          title: "本地人口",
          data: "382人",
        },
        {
          index:2,
          title: "外来人口",
          data: "187人",
        },
        {
          index:3,
          title: "辖区面积",
          data: "439亩",
        },
      ],
      dataTitleList2: [
        {
          index:0,
          title: "耕地面积",
          data: "657亩",
        },
        {
          index:1,
          title: "农业产值",
          data: "214万元",
        },
        {
          index:2,
          title: "工业产值",
          data: "328万元",
        },
        {
          index:3,
          title: "商业产值",
          data: "526万元",
        },
      ],
      townInfo:[
        {
          intro:'“梦想小镇”坐落在余杭区仓前街道，占地面积约3平方公里，于2014年9月正式启动建设，17万方先导区块即将运营。“梦想小镇”涵盖了互联网创业小镇和天使小镇两大内容，其中，互联网创业小镇重点鼓领域产品研发、生产、经营和技术(工程)服务的企业;'
        }
      ],
      imgList: [
        {
          index:0,
          url: require('../../../../assets/cockpit/示例图片/1.jpg'),
          footerImg: require('../../../../assets/cockpit/home/页脚.png'),
          footerText: "1/4",
        },
        {
          index:1,
          url: require('../../../../assets/cockpit/示例图片/2.jpg'),
          footerImg: require('../../../../assets/cockpit/home/页脚.png'),
          footerText: "2/4",
        },
        {
          index:2,
          url: require('../../../../assets/cockpit/示例图片/3.jpg'),
          footerImg: require('../../../../assets/cockpit/home/页脚.png'),
          footerText: "3/4",
        },
        {
          index:3,
          url: require('../../../../assets/cockpit/示例图片/4.jpg'),
          footerImg: require('../../../../assets/cockpit/home/页脚.png'),
          footerText: "4/4",
        },
      ],
      underlineList:[
        {index:0,url:require('../../../../assets/cockpit/home/数据下划线.png')},
        {index:1,url:require('../../../../assets/cockpit/home/数据下划线.png')},
        {index:2,url:require('../../../../assets/cockpit/home/数据下划线.png')},
        {index:3,url:require('../../../../assets/cockpit/home/数据下划线.png')},
      ]
    };
  },
};
</script>

<style lang="scss" scoped>
*::-webkit-scrollbar {
  width: 4px;
}

*::-webkit-scrollbar-thumb {
  background: #0bb3ef;
}

*::-webkit-scrollbar-track {
  margin-bottom: 27vh;
  margin-top: 2vh;
  background: #03374a;
}
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
    .left-ellipse{
      width: 100%;
      position: absolute;
      left: 50%;
      top: 90%;
      transform: translate(-50%);
    }
  }
  .header-box {
    margin-left: 0.5vw;
    display: flex;
    height: 4vh;
    align-items: center; //垂直
    width: 21.9vw;
    img {
      position: absolute;
      width: 19vw;
      height: 4vh;
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
      margin-left: -1.5vw;
      height: 4vh;
      width: 10vw;
      font-size: 0.83vw;
      font-family: Alibaba PuHuiTi;
      font-weight: bold;
      color: #ffffff;
    }
  }
  .content-box1 {
    width: 21vw;
    height: 18.8vh;
    overflow: hidden;
    position: relative;
    margin-top: 1vh;
    margin-bottom: 1.5vh;
    border-radius: 15px;
    .data-box {
      height: 4.5vh;
      width: 22.4vw;
      margin-left: -1.5vw;
      .data-title {
        margin-left: 0.3vw;
        // margin-right: -0.4vw;
        display: inline-block;
        width: 4.7vw;
        height: 1.5vh;
        font-size: 0.83vw;
        font-family: Microsoft YaHei;
        font-weight: 400;
        color: #88c4f3;
      }
      .data {
        // margin-left: 0.2vw;
        margin-right: 0.3vw;
        height: 3.6vh;
        display: inline-block;
        width: 4.5vw;
        font-size: 1.15vw;
        font-family: DINPro;
        font-weight: bold;
        color: #ffffff;
        background: linear-gradient(0deg, #00a8ff 0%, #8fdffe 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
      }
      
    }
    .underline-box {
      display: flex;
      justify-content: space-between;
      margin-left: 1.5vw;
      margin-right: 1.5vw;
      // margin-top: -0.5vh;
      .data-underline {
        // margin-top: -2vh;
        width: 4.5vw;
        height: 3.5vh;
      }
    }
  }

  .content-box2 {
    height: 35vh;
    width: 19.5vw;
    #video {
      margin-top: 1.5vh;
      width: 18.2vw;
      height: 18vh;
      border-radius: 15px;
      border: #68a6e0 2px solid;
    }
    .play-box {
      width: 2vw;
      height: 3.4vh;
      position: absolute;
      margin-left: 8vw;
      margin-top: 8.5vh;
      z-index: 3;
      cursor: pointer;
    }
    .textArea {
      width: 18.2vw;
      margin-top: 1vh;
      margin-left: 0.3vw;
      height: 10vh;
      overflow: auto;
      text-align: justify;
    }

    // 具体内容里的其他文字(非数据)
    span {
      font-size: 0.83vw;
      font-family: Microsoft YaHei;
      font-weight: 400;
      color: #88c4f3;
    }
    img {
      width: 95%;
      margin-top: 1vh;
    }
  }

  .content-box3 {
    width: 18.2vw;
    height: 16vh;
    margin-top: 1.5vh;
    margin-bottom: 1.5vh;
    .page-footer {
      margin-top: -3.3vh;
      margin-left: 15.1vw;
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 3vw;
      height: 3vh;
      .footer-img {
        border: #27c9fe 1px solid;
        width: 3vw;
        height: 3vh;
      }
      .footer-text {
        text-align: center;
        margin-left: -3vw;
        width: 3vw;
        height: 3vh;
        font-size: 0.75vw;
        font-family: Alibaba PuHuiTi;
        font-weight: bold;
        color: #ebf6ff;
        line-height: 3vh;
      }
    }
    .carousel {
      border-radius: 15px;
      border: #27c9fe 2px solid;
    }
    img {
      width: 100%;
      height: 100%;
      border-radius: 15px;
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
}
</style>
