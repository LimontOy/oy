<template>
  <div class="pages-index posr">
    <img src="@img/index/swiper-2.png">
    <div class="pages-index-title" >
      <h3 class="pages-index-move">已有的事，后必再有。已行的事，后必再行</h3>
    </div>
    <client-only>
      <div class="article">
        <template v-for="(i, k) of articList">
          <nuxt-link to="/vuea/meet"><el-link type="success">{{ i }}</el-link></nuxt-link>
          <el-divider>
            <el-icon><star-filled /></el-icon>
          </el-divider>
        </template>
      </div>
    </client-only>
    <div class="container posa">

      <div class="bird-container bird-container--one">
        <div class="bird bird--one"></div>
      </div>

      <div class="bird-container bird-container--two">
        <div class="bird bird--two"></div>
      </div>

      <div class="bird-container bird-container--three">
        <div class="bird bird--three"></div>
      </div>

      <div class="bird-container bird-container--four">
        <div class="bird bird--four"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'pagesIndex'
}
</script>

<script setup>
import { StarFilled } from '@element-plus/icons-vue'

const articList = [
    '多希望话题不断园游会永不打烊：2022年面试经历 2022-08-29',
    '冷空气跟琉璃在清晨很有透明感：2022年面试经历 2022-08-29',
    '鸡蛋糕跟你嘴角果酱我都想要尝：2022年面试经历 2022-08-29'
]
</script>

<style lang="scss">
*,
*::before,
*::after {
  box-sizing: border-box;
}

.container {
  width: 100%;
  //z-index: 521;
  top: 0;
  left: 0;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  // min-height: 100vh;
  min-height: 35rem;
  background-blend-mode: soft-light;
  background-size: cover;
  background-position: center center;
  padding: 2rem;
}

.bird {
  background-image: url(assets/image/index/bird-cells-new.svg);
  background-size: auto 100%;
  width: 88px;
  height: 125px;
  will-change: background-position;

  animation-name: fly-cycle;
  animation-timing-function: steps(10);
  animation-iteration-count: infinite;

  &--one {
    animation-duration: 1s;
    animation-delay: -0.5s;
  }

  &--two {
    animation-duration: 0.9s;
    animation-delay: -0.75s;
  }

  &--three {
    animation-duration: 1.25s;
    animation-delay: -0.25s;
  }

  &--four {
    animation-duration: 1.1s;
    animation-delay: -0.5s;
  }

}

.bird-container {
  position: absolute;
  top: 20%;
  left: -10%;
  transform: scale(0) translateX(-10vw);
  will-change: transform;

  animation-name: fly-right-one;
  animation-timing-function: linear;
  animation-iteration-count: infinite;

  &--one {
    animation-duration: 15s;
    animation-delay: 0;
  }

  &--two {
    animation-duration: 16s;
    animation-delay: 1s;
  }

  &--three {
    animation-duration: 14.6s;
    animation-delay: 9.5s;
  }

  &--four {
    animation-duration: 16s;
    animation-delay: 10.25s;
  }

}

@keyframes fly-cycle {

  100% {
    background-position: -900px 0;
  }

}

@keyframes fly-right-one {

  0% {
    transform: scale(0.3) translateX(-10vw);
  }

  10% {
    transform: translateY(2vh) translateX(10vw) scale(0.4);
  }

  20% {
    transform: translateY(0vh) translateX(30vw) scale(0.5);
  }

  30% {
    transform: translateY(4vh) translateX(50vw) scale(0.6);
  }

  40% {
    transform: translateY(2vh) translateX(70vw) scale(0.6);
  }

  50% {
    transform: translateY(0vh) translateX(90vw) scale(0.6);
  }

  60% {
    transform: translateY(0vh) translateX(110vw) scale(0.6);
  }

  100% {
    transform: translateY(0vh) translateX(110vw) scale(0.6);
  }

}

@keyframes fly-right-two {

  0% {
    transform: translateY(-2vh) translateX(-10vw) scale(0.5);
  }

  10% {
    transform: translateY(0vh) translateX(10vw) scale(0.4);
  }

  20% {
    transform: translateY(-4vh) translateX(30vw) scale(0.6);
  }

  30% {
    transform: translateY(1vh) translateX(50vw) scale(0.45);
  }

  40% {
    transform: translateY(-2.5vh) translateX(70vw) scale(0.5);
  }

  50% {
    transform: translateY(0vh) translateX(90vw) scale(0.45);
  }

  51% {
    transform: translateY(0vh) translateX(110vw) scale(0.45);
  }

  100% {
    transform: translateY(0vh) translateX(110vw) scale(0.45);
  }

}
.pages-index {
  width: 100%;
  @include cImg();
  &-title {
    margin: 40px auto;
    text-align: center;
    //font-size: 24px;
  }
  &-move {
    animation: moveTo linear .5s forwards;
  }
  @keyframes moveTo {
    from {
      transform: translateY(70px);
      opacity: 0;
    }
    to {
      transform: translateY(-10px);
      opacity: .9;
    }
  }

  .article {
    margin-left: 160px;
    width: 420px;
  }
  .el-icon svg {
    color: #00BD6FFF;
  }
  .el-link.el-link--success {
    color: #00BD6FFF;
  }
}
</style>