<template>
  <div id="body1">
    <Home v-if="menuActive === '概况'"></Home>
    <Greenhouse v-if="menuActive === '智慧大棚'"></Greenhouse>
    <Agriculture v-if="menuActive === '农业产业'"></Agriculture>
    <Land v-if="menuActive === '土地管理'"></Land>
    <el-footer>
      <img
        src="@/assets/cockpit/public/底部框架.png"
        class="bottom-img"
        alt=""
      />
      <div class="btn-box-box">
        <div
          class="btn-box"
          v-for="(item, index) in menuList"
          @click="menuActive = item.title"
          :key="index"
        >
          <img
            :src="menuActive == item.title ? item.url2 : item.url"
            class="bottom-left"
          />
          <span class="title">{{ item.title }}</span>
        </div>
      </div>
    </el-footer>
  </div>
</template>

<script>
import Home from "./home/Home.vue";
import Greenhouse from "./greenhouse/Greenhouse.vue";
import Agriculture from "./agriculture/Agriculture.vue";
import Land from "./land/Land.vue";
// import BigScreenMap from "@/Gis/BigScreenMap";

// let bigScreenMap = ref(null);
// provide('bigScreenMap', bigScreenMap);

// onMounted(() => {
//   bigScreenMap.value = new BigScreenMap("cesiumContainer");
// });

export default {
  components: {
    Home,
    Greenhouse,
    Agriculture,
    Land,
  },
  data() {
    return {
      menuActive: "概况",
      menuList: [
        {
          title: "概况",
          url: require("../../assets/cockpit/public/底部左1按钮未点.png"),
          url2: require("../../assets/cockpit/public/底部左1按钮已点.png"),
        },
        {
          title: "智慧大棚",
          url: require("../../assets/cockpit/public/底部中1按钮未点.png"),
          url2: require("../../assets/cockpit/public/底部中1按钮已点.png"),
        },
        {
          title: "农业产业",
          url: require("../../assets/cockpit/public/底部中2按钮未点.png"),
          url2: require("../../assets/cockpit/public/底部中2按钮已点.png"),
        },
        {
          title: "土地管理",
          url: require("../../assets/cockpit/public/底部右1按钮未点.png"),
          url2: require("../../assets/cockpit/public/底部右1按钮已点.png"),
        },
      ],
    };
  },
  methods: {
    menuClick(item) {
      this.menuActive = item.title;
    },
  },
};
</script>

<style lang="scss" scoped>
#body1 {
  position: absolute;
  z-index: 1;
  width: 100%;
  height: 100%;
  top: 0;
  left: 0;
  pointer-events: none;
}
#cesiumContainer {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
.el-footer {
  height: 7.5vh;
  display: flex;
  justify-content: center;
  align-items: center;
  pointer-events: auto;
  bottom: 5vh;
  position: relative;
  .bottom-img {
    position: absolute;
    height: 7.5vh;
    width: 33vw;
    top: -1.5vh;
    z-index: -1;
  }
  .btn-box-box {
    position: absolute;
    top: -2.8vh;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    .btn-box {
      height: 4.1vh;
      width: 6.2vw;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 3vh;
      margin-left: 0.5vw;
      cursor: pointer;
      .bottom-left {
        width: 6.2vw;
        height: 3.8vh;
      }
      .title {
        line-height: 3vh;
        text-align: center;
        height: 3vh;
        width: 7vw;
        margin-left: -6.2vw;
        font-size: 1vw;
        font-family: Alibaba PuHuiTi;
        font-weight: 400;
        color: #ffffff;
      }
    }
  }
}
</style>
