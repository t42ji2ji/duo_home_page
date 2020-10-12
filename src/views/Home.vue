<template lang="pug">
.pageBase.home
  .logoWithDesc
    .logo
      .logoCircle
      .sizeBox
      .logoText
        .logoTitle DUODUO
        .logoSubTitle DESIGN
    .desc
      .descItem Provide:
      .descItem Character Design
      .descItem Front-end Developer
      .descItem App Developer
  .others
    .mail Email:duoduo.design.company@gmail.com
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';

export default {
  name: 'Home',
  components: {
    HelloWorld,
  },
};
</script>

<style lang="scss" scoped>
.pageBase {
  font-family: 'IBM Plex Mono', monospace;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  // background-color: blue;
}

.others{
position: absolute;
bottom: 20px;
}

.logoWithDesc{
  display: flex;
  flex-direction: column;
  .desc{
    margin-top: 32px;
    display: flex;
    flex-direction: column;
    text-align: start;
    font-size: 14px;
  }
}

.logo {
  display: flex;
  .logoCircle {
    width: 66px;
    height: 66px;
    position: relative;
    background-color: #ff7a7a;
    border-radius: 50%;
    &:hover{
      &::after{
    transform: translate(-33px, 0px);

      }
    }
  }
  .logoCircle:after {
    content: '';
    mix-blend-mode: multiply;
    position: absolute;
    width: 66px;
    height: 66px;
    border-radius: 50%;
    background-color: #7bc8ff;
    transition: 0.5s;
    transform: translate(0px, 0px);
    animation: logoAnimation 3s;

  }
}

.logoText {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  .logoTitle {
    font-size: 30px;
    font-weight: 500;
    line-height: 25px;
    position: relative;
    overflow: hidden;

  }

  .logoTitle:after {
    content: '';
    left: 0;
    width: 100%;
    height: 100%;
    position: absolute;
    background-color: rgb(36, 33, 44);
    animation: logoText 1.6s ease-in-out;
    transform: scaleX(0) ;
    transform-origin: left center;
   
  }

  .logoSubTitle {
    font-size: 10px;
    font-weight: medium;
    font-weight: 800;
    position: relative;
    overflow: hidden;
  }
  .logoSubTitle::after{
    content: '';
    left: 0;
    width: 100%;
    height: 100%;
    position: absolute;
    background-color: rgb(36, 33, 44);
    animation: logoText 1.5s ease-in-out;
    transform: scaleX(0) ;
    transform-origin: left center;
  }
}

.sizeBox {
  width: 46px;
}

@keyframes logoAnimation {
  from {
    transform: translate(-33px, 0px);
  }
  to {
    transform: translate(0px, 0px);
  }
}
@keyframes logoText {
  0% {
    transform-origin: left center;

    transform: scaleX(0) translateX(0px);;
  }
  50%{
        transform-origin: left center;
      transform: scaleX(1) ;
  }

  100% {
    transform: translateX(100px);
  }
}
</style>
