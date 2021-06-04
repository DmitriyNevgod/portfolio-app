<template>
  <div class="about">
    <el-row
      type="flex"
      justify="center"
      align="middle"
      class="about-me full-screen"
    >
      <el-col class="about-me-left" :sm="10">
        <h1 class="about-me-left__title">Обо мне</h1>
        <p class="about-me-left__text">
          Я занимаюсь разработкой веб приложений. Web Developer - профессия,
          которая проглотила меня. С каждым новым проектом я всё больше понимаю
          как много технологий ещё нужно изучить и сколько возможностей могут
          дать эти знания. Меня вдохновляет то, чем я занимаюсь.
        </p>
      </el-col>

      <el-col class="about-me__img" :sm="7" :span="14">
        <img
          :src="require('../assets/img/about-page/about-photo.jpg')"
          alt="Дмитрий Невгод"
        />
      </el-col>
      <div class="scroll-btn">
        <a href="#skills" class="scroll"><span></span></a>
      </div>
    </el-row>
    <div class="skills full-screen" id="skills">
      <el-row type="flex" justify="center" align="middle">
        <el-col :span="24">
          <h2 class="skills__title">Навыки</h2>
          <p class="skills__sub-title">"нет предела совершенству"</p>
        </el-col>
      </el-row>

      <ul class="skills-honeycomb__list">
        <li
          class="skills-honeycomb__item"
          v-for="skill in skills"
          :key="skill.title"
        >
          <img :src="skill.img" :alt="skill.title" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      skills: [
        { title: "html", img: require("../assets/img/about-page/html.png") },
        { title: "css", img: require("../assets/img/about-page/css.png") },
        { title: "js", img: require("../assets/img/about-page/js.png") },
        { title: "sass", img: require("../assets/img/about-page/sass.png") },
        {
          title: "jQuery",
          img: require("../assets/img/about-page/jQuery.png"),
        },
        {
          title: "bootstrap",
          img: require("../assets/img/about-page/bootstrap.png"),
        },
        { title: "npm", img: require("../assets/img/about-page/npm.png") },
        {
          title: "node-js",
          img: require("../assets/img/about-page/node-js.png"),
        },
        {
          title: "babel",
          img: require("../assets/img/about-page/babel.png"),
        },
        {
          title: "webpack",
          img: require("../assets/img/about-page/webpack.png"),
        },
        { title: "vue", img: require("../assets/img/about-page/vue.png") },
        { title: "react", img: require("../assets/img/about-page/react.png") },
        { title: "redux", img: require("../assets/img/about-page/redux.png") },
        { title: "figma", img: require("../assets/img/about-page/figma.png") },
        { title: "git", img: require("../assets/img/about-page/git.png") },
        { title: "pixel", img: require("../assets/img/about-page/pixel.png") },
        {
          title: "vs-code",
          img: require("../assets/img/about-page/vs-code.png"),
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.about-me {
  background: #eeeeee;
  &-left {
    margin-right: 10%;
    text-align: center;
    line-height: 1.55em;
  }
  &__img {
    height: 560px;
    img {
      width: 100%;
      height: 100%;
    }
  }
}

.scroll-btn {
  position: absolute;
  bottom: 80px;
}
.scroll {
  padding-top: 60px;
  & span {
    position: absolute;
    top: 0;
    left: 50%;
    width: 30px;
    height: 50px;
    margin-left: -15px;
    border: 2px solid #f84525;
    border-radius: 50px;
    box-sizing: border-box;
  }
  & span::before {
    position: absolute;
    top: 10px;
    left: 50%;
    content: "";
    width: 6px;
    height: 6px;
    margin-left: -3px;
    background-color: #f84525;
    border-radius: 100%;
    -webkit-animation: sdb10 2s infinite;
    animation: sdb10 2s infinite;
    box-sizing: border-box;
  }
}

@-webkit-keyframes sdb10 {
  0% {
    -webkit-transform: translate(0, 0);
    opacity: 0;
  }
  40% {
    opacity: 1;
  }
  80% {
    -webkit-transform: translate(0, 20px);
    opacity: 0;
  }
  100% {
    opacity: 0;
  }
}
@keyframes sdb10 {
  0% {
    transform: translate(0, 0);
    opacity: 0;
  }
  40% {
    opacity: 1;
  }
  80% {
    transform: translate(0, 20px);
    opacity: 0;
  }
  100% {
    opacity: 0;
  }
}

.skills {
  padding: 90px 0;
  &__title {
    text-align: center;
    font-size: 2em;
  }
  &__sub-title {
    text-align: center;
  }
  &-honeycomb__list {
    display: flex;
    flex-wrap: wrap;
    width: 1090px;
    margin: 100px auto 0;
  }
  &-honeycomb__item {
    background: url("../assets/img/about-page/hexagon.svg") no-repeat center;
    background-size: cover;
    height: 200px;
    width: 200px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 20px;
    margin-top: -20px;
    &:nth-child(5),
    &:nth-child(9),
    &:nth-child(14) {
      margin-right: 0;
    }
    &:nth-child(6),
    &:nth-child(15) {
      margin-left: 110px;
    }
    img {
      width: 60%;
      height: 70%;
    }
    &:hover {
      transition: 0.3s linear;
      background: url("../assets/img/about-page/hexagon-hover.svg") no-repeat
        center;
      background-size: cover;
    }
  }
}

@media (max-width: 1200px) {
  .about-me {
    &-left {
      line-height: 1.3em;
    }
    &__img {
      height: 350px;
    }
  }
  .skills {
    &-honeycomb__list {
      width: 900px;
      padding-bottom: 100px;
    }
    &-honeycomb__item {
      width: 180px;
      height: 180px;
      margin-top: -10px;

      &:nth-child(10) {
        margin-left: 20px;
      }
      &:nth-child(6) {
        margin-left: 20px;
      }
      &:nth-child(7),
      &:nth-child(14) {
        margin-right: 100px;
      }
      &:nth-child(5),
      &:nth-child(12) {
        margin-left: 100px;
      }
      &:nth-child(15) {
        margin-left: 0;
      }
      img {
        width: 60%;
        height: 70%;
      }
    }
  }
}
@media (max-width: 992px) {
  .about-me {
    &-left {
      margin-right: 10%;
      line-height: 1.1em;
      font-size: 0.94em;
    }
    &__img {
      height: 300px;
    }
  }
  .skills {
    &-honeycomb__list {
      margin-top: 50px;
      padding-bottom: 50px;
      width: 700px;
    }
    &-honeycomb__item {
      width: 150px;
      height: 150px;
      &:nth-child(5),
      &:nth-child(12) {
        margin-left: 80px;
      }
    }
  }
}
@media (max-width: 767px) {
  .about-me {
    &-left {
      margin-top: 5%;
      &__title {
        margin: 50px 0;
      }
      margin-right: 0;
      text-align: center;
      line-height: 1.1em;
    }
    &__img {
      height: 500px;
    }
  }
  .skills {
    &-honeycomb__list {
      margin-top: 50px;
      padding-bottom: 50px;
      width: 500px;
    }
    &-honeycomb__item {
      width: 100px;
      height: 100px;
      margin-top: 0px;
      &:nth-child(5),
      &:nth-child(12) {
        margin-left: 60px;
      }
    }
  }
}
@media (max-width: 576px) {
  .about-me {
    background: url("../assets/img/about-page/about-photo-m.jpg") no-repeat
      center;
    background-size: cover;
    color: #fff;
    -webkit-box-align: flex-start !important;
    -ms-flex-align: flex-start !important;
    align-items: flex-start !important;
    &-left {
      margin-top: 30%;
      line-height: 1.1em;
      &__title {
        margin: 20px 0;
      }
    }
    &__img {
      display: none;
    }
  }
  .skills {
    &-honeycomb__list {
      width: 300px;
    }
    &-honeycomb__item {
      width: 90px;
      height: 90px;
      margin-top: -5px;
      margin-right: 10px;

      &:nth-child(4),
      &:nth-child(9),
      &:nth-child(14) {
        margin-left: 50px;
      }
      &:nth-child(5),
      &:nth-child(6),
      &:nth-child(10),
      &:nth-child(12) {
        margin-left: 0;
      }
      &:nth-child(7),
      &:nth-child(9),
      &:nth-child(11),
      &:nth-child(12),
      &:nth-child(14) {
        margin-right: 10px;
      }
      img {
        width: 60%;
        height: 70%;
      }
    }
  }
}
</style>
