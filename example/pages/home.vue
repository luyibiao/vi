<template>
  <div class="home-page">
    <div class="home-page__body">
      <div class="banner clear">
        <div class="desc">
          <h3 class="heading-super">中后台快速开发的组件库</h3>
          <p class="paragraph">vi 是一套基于 Vue 开发的组件库，集成大量常用的UI组件，帮助开发者快速完成PC端的中后台产品开发</p>
          <vi-button type="primary" size="large" @click="$router.push({path: 'component/快速上手'})">
            快速开始
            <vi-icon name="arrow-right"></vi-icon>
          </vi-button>
        </div>
        <img class="fr" src="../assets/svg/home-banner1.svg" alt="">
      </div>
      <div class="banner clear">
        <ul class="feature-list fr">
          <li class="feature-item">
            <vi-icon name="radio-checked"></vi-icon>
            <div class="content">
              <p class="heading-middle">Free</p>
              <p class="heading-middle">免费开源</p>
            </div>
          </li>
          <li class="feature-item">
            <vi-icon name="radio-checked"></vi-icon>
            <div class="content">
              <p class="heading-middle">Easy</p>
              <p class="heading-middle">简单易用</p>
            </div>
          </li>
          <li class="feature-item">
            <vi-icon name="radio-checked"></vi-icon>
            <div class="content">
              <p class="heading-middle">Standard</p>
              <p class="heading-middle">标准规范</p>
            </div>
          </li>
          <li class="feature-item">
            <vi-icon name="radio-checked"></vi-icon>
            <div class="content">
              <p class="heading-middle">Scalability</p>
              <p class="heading-middle">拓展性强</p>
            </div>
          </li>
          <li class="feature-item">
            <vi-icon name="radio-checked"></vi-icon>
            <div class="content">
              <p class="heading-middle">......</p>
            </div>
          </li>
        </ul>
        <img class="fl" src="../assets/svg/home-banner2.svg" alt="">
      </div>
      <div class="banner clear">
        <div class="contributor">
          <h2 class="desc heading-large" style="line-height: 1.5;">
            使用组件 Demo 快速体验交互细节；使用前端框架封装的代码帮助工程师快速开发。
          </h2>
        </div>
        <img class="fr" src="../assets/svg/home-banner3.svg" alt="">
      </div>
    </div>
    <div class="home-page__footer">
      &copy;2019 - vi (Vue Components)
    </div>
  </div>
</template>
<script>
export default {
  name: 'home-page'
}
</script>

<style lang="scss" scoped>
.home-page {
  width: 100%;
  overflow: auto;
  color: #909399;
  .home-page__body {
    width: 90%;
    max-width: 1360px;
    margin: 0 auto;
    padding: 100px 0;
    color: #000;
  }

  .banner {
    position: relative;
    &:not(:first-child) {
      margin-top: 250px;
    }

    &:nth-child(1) {
      
      img {
        width: 60%;
      }
    }

    &:nth-child(2) {
      img {
        width: 50%;
      }
    }

    &:nth-child(3) {
      img {
        width: 60%;
      }
    }

    .desc {
      width: 36%;
      right: 0;
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      .heading-super {
        font-size: 30px;
        font-weight: bold;
        color: #303133;
      }
      &.heading-large {
        line-height: 1.5;
        font-size: 30px;
      }
      p {
        margin-top: 30px;
        margin-bottom: 50px;
        line-height: 1.5;
        font-size: 18px;
      }
    }
  }

  .feature-list {
    width: 40%;
    height: 100%;
    margin: 0;

    position: absolute;
    right: 0;
    top: 0;

    font-size: 0;

    .feature-item {
    }
  }

  .feature-item {

    & > * {
      display: inline-block;
      vertical-align: middle;
      margin-left: 20%;
      font-size: 30px;
    }

    &:not(:last-child) {
      margin-bottom: 10%;
    }

    .content {
      p {
        margin-top: 10px;
      }
    }
  }

  .home-page__footer {
    width: 100%;
    height: 60px;
    margin-top: 100px;

    background-color: darken(#5575c8, 10%);

    color: #ffffff;
    font-size: 13px;
    text-align: center;
    line-height: 60px;
  }
}
</style>
