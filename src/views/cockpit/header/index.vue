<template>
  <div>
    <div class="outsideBox">
      <img
        src="@/assets/cockpit/public/标题框架.png"
        alt=""
        class="header-box"
      />
      <div class="insideBox">
        <img
          src="@/assets/cockpit/public/驾驶舱标题.png"
          alt=""
          class="header-text"
        />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
img {
  // 解决图片失真
  image-rendering: -moz-crisp-edges; /* Firefox */
  image-rendering: -o-crisp-edges; /* Opera */
  image-rendering: -webkit-optimize-contrast; /*Webkit (non-standard naming) */
  image-rendering: crisp-edges;
  -ms-interpolation-mode: nearest-neighbor; /* IE (non-standard property) */
}
.outsideBox {
  position: relative;

  .header-box {
    position: absolute;
    width: 58vw;
    height: 16vh;
    left: 50%;
    top: 0.2vh;
    transform: translate(-51%);
  }
  .header-text {
    position: absolute;
    width: 25vw;
    height: 4vh;
    top: 5vh;
    left: 50%;
    transform: translateX(-54%);
  }
}
</style>

