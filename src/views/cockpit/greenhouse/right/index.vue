<template>
  <div class="box1">
    <img src="@/assets/cockpit/public/右侧导航背景.png" alt="" class="right" />
    <!-- 标题盒子1 -->
    <div class="header-box" style="margin-top: 7.5vh">
      <img
        src="@/assets/cockpit/public/具体内容标题背景.png"
        alt=""
        class="right-content1"
      />
      <!-- 圆点 -->
      <div class="status-point" />
      <!-- 标题 -->
      <span class="span1">
        <!-- 内容标题填写处 -->
        大棚用途分析
      </span>
    </div>
    <!-- 内容盒子1 -->
    <div class="content-box">
      <!-- 具体内容填写处 -->
      <!-- 饼状图 -->
      <div class="div1">
        <div ref="content1" id="content1"></div>
      </div>
    </div>

    <!-- 标题盒子2 -->
    <div class="header-box" style="margin-top: -3vh">
      <img
        src="@/assets/cockpit/public/具体内容标题背景.png"
        alt=""
        class="right-content2"
      />
      <div class="status-point" />
      <span>
        <!-- 内容标题填写处 -->
        大棚作物分析
      </span>
    </div>
    <!-- 内容盒子2 -->
    <div class="content-box">
      <!-- 具体内容填写处 -->
      <div class="div2">
        <img
          src="@/assets/cockpit/greenhouse/右二外框.png"
          alt=""
          class="content2-back"
        />
        <div id="content2" ref="content2"></div>
      </div>
    </div>

    <!-- 标题盒子3 -->
    <div class="header-box" style="margin-top: -1vh">
      <img
        src="@/assets/cockpit/public/具体内容标题背景.png"
        alt=""
        class="right-content3"
      />

      <div class="status-point" />
      <span  style="margin-left:2.5vw">
        <!-- 内容标题填写处 -->
        大棚产值排行榜
      </span>
    </div>
    <!-- 内容盒子3 -->
    <div class="content-box">
      <!-- 具体内容填写处 -->

      <div
        class="ranking"
        v-for="(item, index) in greenhouseList.slice(0, 5)"
        :key="index"
      >
        <div class="ranking-index-box">
          <img :src="item.indexBackImg" alt="" class="ranking-index-img" />
          <span class="ranking-index">
            {{ index + 1 }}
          </span>
        </div>
        <div class="ranking-data-box">
          <span class="ranking-name">
            {{ item.greenhouseName }}
          </span>
          <span class="ranking-data">
            {{ item.cropsValueTotal }}
          </span>
          <img :src="rankBackImg" alt="" class="ranking-box-img" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import * as echarts from "echarts";
export default {
  data() {
    return {
      rankBackImg:require('../../../../assets/cockpit/greenhouse/右三行数据外框.png'),
      greenhouseList: [
        {
          index: 0,
          greenhouseName: "蔬菜大棚",
          greenhouseArea: 460,
          greenhouseAreaPercentage: 47.5,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
          indexBackImg:require('../../../../assets/cockpit/greenhouse/右三橙色序号外框.png')
        },
        {
          index: 1,
          greenhouseName: "玉米基地",
          greenhouseArea: 306,
          greenhouseAreaPercentage: 31.2,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
          indexBackImg:require('../../../../assets/cockpit/greenhouse/右三橙色序号外框.png')
        },
        {
          index: 2,
          greenhouseName: "水稻基地",
          greenhouseArea: 148,
          greenhouseAreaPercentage: 10.5,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
          indexBackImg:require('../../../../assets/cockpit/greenhouse/右三橙色序号外框.png')
        },
        {
          index: 3,
          greenhouseName: "茭白基地",
          greenhouseArea: 63,
          greenhouseAreaPercentage: 7.5,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
          indexBackImg:require('../../../../assets/cockpit/greenhouse/右三蓝色序号外框.png')
        },
        {
          index: 4,
          greenhouseName: "西瓜基地",
          greenhouseArea: 42,
          greenhouseAreaPercentage: 4.5,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
          indexBackImg:require('../../../../assets/cockpit/greenhouse/右三蓝色序号外框.png')
        },
        {
          index: 5,
          greenhouseName: "芒果基地",
          greenhouseArea: 41,
          greenhouseAreaPercentage: 4.5,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
        },
        {
          index: 6,
          greenhouseName: "榴莲基地",
          greenhouseArea: 40,
          greenhouseAreaPercentage: 4.5,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
        },
        {
          index: 7,
          greenhouseName: "草莓基地",
          greenhouseArea: 39,
          greenhouseAreaPercentage: 4.5,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
        },
        {
          index: 8,
          greenhouseName: "猕猴桃基地",
          greenhouseArea: 38,
          greenhouseAreaPercentage: 4.5,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
        },
        {
          index: 9,
          greenhouseName: "哈密瓜基地",
          greenhouseArea: 33,
          greenhouseAreaPercentage: 4.5,
          percentageText: "总占比率",
          cropsValueTotal: 32190,
        },
      ],
    };
  },
  methods: {
    init1() {
      var chartDom = document.getElementById("content1");
      var myChart1 = echarts.init(chartDom);
      var option1 = {
        title: {
          height: "100",
          text: "总亩数",
          subtext: "9000亩",
          textStyle: {
            borderWidth: 4,
            borderColor: "#fff",
            color: "#88B1D0",
            fontSize: "16",
            fontWeight: "nomal",
            fontFamily: "Microsoft YaHei",
          },
          subtextStyle: {
            color: "#ffffff",
            fontSize: "16",
            fontWeight: "nomal",
            fontFamily: "DINPro",
          },

          left: "center",
          top: "38%",
          z: 30,
        },
        // tooltip：鼠标移到饼图部分上时显示的对话框
        tooltip: {
          formatter: "{b}：{c}亩",
        },
        series: [
          // 内圆
          {
            type: "pie",
            radius: "33",
            label: {
              show: false,
            },
            labelLine: {
              show: false,
            },
            itemStyle: {
              opacity: 0.8,
              color: {
                type: "radial",
                x: 0.5,
                y: 0.5,
                r: 0.5,
                colorStops: [
                  {
                    offset: 1,
                    color: "#27C9FE", // 0% 处的颜色
                  },
                  {
                    offset: 0.35,
                    color: "#0c1330", // 100% 处的颜色
                  },
                ],
                global: false, // 缺省为 false
              },
              borderColor: "#34ECFF ",
              borderWidth: 3.5,
            },
            data: [{ name: "总亩数", value: 9000 }],
          },
          // 外环
          {
            hoverAnimation: false,
            type: "pie",
            radius: ["45", "58"],
            itemStyle: {
              borderRadius: 4,
              borderColor: "#505a7a",
              borderWidth: 3,
            },
            labelLine: {
              length: 10,
              length2: 10,
            },

            label: {
              formatter: "{cValue|{c}亩}\n{bValue|{b}} ",
              borderColor: "#8C8D8E",
              rich: {
                cValue: {
                  color: "#FFFFFF",
                  fontWeight: "bold",
                  fontFamily: "DINPro",
                  fontSize: 16,
                  align: "center",
                },
                bValue: {
                  color: "#88B1D0",
                  fontWeight: "bold",
                  fontFamily: "Microsoft YaHei",
                  fontSize: 14,
                  align: "center",
                },
              },
            },
            data: [
              {value:3000,name:'蔬菜类'},
              {value:1000,name:'水果类'},
              {value:5000,name:'粮食类'}
            ]
          },
        ],
      };

      myChart1.setOption(option1);
      // 默认高亮
      myChart1.dispatchAction({
        type: "highlight",
      });
      window.addEventListener("resize", function () {
        myChart1.resize();
      });
    },
    init2() {
      // 右二折柱混合
      var chartDom = document.getElementById("content2");
      var myChart2 = echarts.init(chartDom);
      var option2 = {
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "cross",
            label: {
              backgroundColor: "#6a7985",
            },
          },
        },
        legend: {
          data: ["接入面积", "开通面积", "使用面积"],
          itemWidth: 15, //矩形宽度
          itemHeight: 5, //矩形高度
          // symbol: 'none',
          textStyle: {
            color: "#88B1D0",
            fontWeight: "bold",
            fontFamily: "Microsoft YaHei",
          },
        },
        grid: {
          top: "20%",
          left: "3%",
          bottom: "1%",
          right: "7%",
          containLabel: true,
        },
        xAxis: [
          {
            type: "category",
            data: ["2019", "2020", "2021", "2022", "2023", "2024"],
            axisTick: {
              alignWithLabel: true,
            },
            nameTextStyle: {
              color: "#82b0ec",
            },
            axisLine: {
              show: false,
              lineStyle: {
                color: "#82b0ec",
              },
            },
            axisLabel: {
              textStyle: {
                color: "#BFF7FF",
                fontWeight: 300,
                fontFamily: "DINPro",
              },
              margin: 10,
            },
          },
        ],
        yAxis: [
          {
            max: 300,
            min: 0,
            splitNumber: 4,
            show: true,
            type: "value",
            // interval: 2,
            axisLabel: {
              interval: 2,
              opacity: 0.8,
              textStyle: {
                color: "#C3F4FE",
                fontWeight: 300,
                fontFamily: "DINPro",
              },
            },
            splitLine: {
              interval: 2,
              lineStyle: {
                interval: 2,
                type: "dotted",
                color: "#fff",
                opacity: 0.1,
              },
            },
          },
        ],
        series: [
          // 上部椭圆
          {
            // name: '无效数据',
            type: "pictorialBar",
            symbolSize: [15, 7],
            symbolOffset: [0, -5], // 上部椭圆
            symbolPosition: "end",
            z: 12,
            color: "#21F3FF",
            data: [300, 250, 200, 100, 200, 300],
            itemStyle: {
              opacity: 0.8,
            },
            tooltip: {
              trigger: "item",
              show: false,
            },
          },
          // 下部椭圆
          {
            // name: '无效数据',
            type: "pictorialBar",
            symbolSize: [15, 6],
            symbolOffset: [0, 5], // 下部椭圆
            // "barWidth": "20",
            z: 12,
            color: "#1F61EA",
            data: [300, 250, 200, 100, 200, 300],
            itemStyle: {
              opacity: 0.8,
            },
            tooltip: {
              trigger: "item",
              show: false,
            },
          },
          // 开通面积
          {
            name: "开通面积",
            data: [150, 230, 224, 218, 135, 147],
            type: "line",
            symbol: "none",
            lineStyle: {
              color: "#dea908", //改变折线颜色
            },
          },
          // 使用面积
          {
            name: "使用面积",
            data: [250, 130, 124, 118, 235, 247],
            type: "line",
            symbol: "none",
            lineStyle: {
              color: "#00BFFF ", //改变折线颜色
            },
          },
          // 接入面积
          {
            name: "接入面积",
            type: "bar",
            barWidth: "15",
            itemStyle: {
              normal: {
                color: new echarts.graphic.LinearGradient(0, 0, 0, 0.7, [
                  {
                    offset: 0.4,
                    color: "#00B7FF",
                  },
                  {
                    offset: 1,
                    color: "#2244AC",
                  },
                ]),
                opacity: 0.8,
              },
            },
            data: [300, 250, 200, 100, 200, 300],
          },
        ],
      };
      myChart2.setOption(option2);
      window.addEventListener("resize", function () {
        myChart2.resize();
      });
    },
  },
  mounted() {
    this.init1();
    this.init2();
  },
};
</script>

<style lang="scss" scoped>
.right {
  // background: black;
  position: absolute;
  width: 21.5vw;
  height: 90vh;
  z-index: -1;
  // margin-right: ;
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
  // background: black;
  width: 21.5vw;
  height: 90vh;
  margin-top: 5vh;
  margin-right: 3vw;
  display: flex;
  flex-direction: column;
  .header-box {
    display: flex;
    align-items: center; //垂直
    width: 15.9vw;
    height: 4vh;
    img {
      margin-left: 2.5vw;
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
      margin-left: 3.25vw;
    }
    span {
      line-height: 4vh;
      height: 4vh;
      margin-left: 2vw;
      width: 10vw;
      font-size: 0.83vw;
      font-family: Alibaba PuHuiTi;
      font-weight: bold;
      color: #ffffff;
    }
  }
  .content-box {
    width: 21vw;
    position: relative;
    margin: 0 0 2.5vh 2.5vw;
    .div1 {
      height: 18vh;
      width: 21vw;
      #content1 {
        text-align: center;
        margin-left: -1vw;
        width: 100%;
        height: 100%;
      }
    }
    .div2 {
      height: 18vh;
      width: 21vw;
      .content2-back {
        height: 18vh;
        width: 20.5vw;
        margin-left: -11vw;
        position: absolute;
        z-index: -1;
      }
      #content2 {
        // text-align: center;
        width: 19vw;
        height: 18vh;
        margin-top: 1.5vh;
      }
    }
    .ranking {
      height: 7vh;
      width: 19vw;
      margin-top: -1vh;
      margin-left: 0.5vw;
      .ranking-index-box {
        width: 2.4vw;
        height: 4.1vh;
        position: relative;
        .ranking-index-img {
          width: 100%;
          height: 100%;
          margin-top: 2vh;
        }
        .ranking-index {
          position: absolute;
          transform: translate(-50%, -20%);
          font-size: 1vw;
          color: #ffffff;
          font-family: Agency FB;
          font-weight: bold;
          top: 80%;
          left: 50%;
        }
      }
      .ranking-data-box {
        display: flex;
        height: 3.6vh;
        width: 19vw;
        margin-top: -0.5vh;
        .ranking-box-img {
          height: 3.6vh;
          width: 19vw;
          margin-left: -16vw;
        }
        .ranking-name {
          color: #c3f4fe;
          font-family: Microsoft YaHei;
          font-weight: 400;
          margin-left: 4vw;
          font-size: 1vw;
          line-height: 3.6vh;
          width: 6vw;
          margin-top: 0.4vh;
        }
        .ranking-data {
          color: #ffffff;
          font-family: DINPro;
          font-weight: 400;
          margin-left: 2.5vw;
          font-size: 1vw;
          line-height: 3.6vh;
          margin-top: 0.4vh;
        }
      }
    }
  }
}
</style>