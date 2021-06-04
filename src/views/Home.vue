<template>
  <el-row class="home full-screen overflow">
    <el-col :span="24">
      <div class="home__title-wrap">
        <span class="home__overhead">Web Developer</span>
        <h1 class="home__title">
          Здравствуй! Моё имя Дмитрий Невгод. Я занимаюсь разработкой
          веб-приложений
        </h1>

        <div class="home__btn">
          <router-link to="/about" class="home__btn-link">
            <span>Узнать лучше</span>
            <svg width="13px" height="10px" viewBox="0 0 13 10">
              <path d="M1,5 L11,5"></path>
              <polyline points="8 1 12 5 8 9"></polyline>
            </svg>
          </router-link>
        </div>
      </div>
    </el-col>
    <div class="svg-bg">
      <img :src="require('../assets/img/home-bg.svg')" alt="svg" />
    </div>
  </el-row>
</template>

<script>
export default {};
</script>

<style lang="scss">
.home {
  background: #1f1e1d;
  color: #fff;
  display: flex;
  align-items: center;
  &__title-wrap {
    margin-left: 10%;
    width: 50%;
  }
  &__overhead {
    font-size: 1.4em;
    color: #f84525;
    letter-spacing: 0.25em;
  }
  &__title {
    line-height: 1.15em;
    margin-left: 30px;
    font-size: 2em;
    letter-spacing: 0.02em;
  }
  &__btn {
    position: relative;
    z-index: 1;
    margin-top: 70px;
  }
  .svg-bg {
    position: absolute;
    top: 40px;
    bottom: 0;
    right: 0;
    opacity: 0.3;
    img {
      height: 95vh;
    }
  }
  .home__btn-link::before {
    width: 100%;
    background: #f84525;
  }
}
@media (max-width: 1200px) {
  .home {
    &__overhead {
      font-size: 1em;
    }
    &__title-wrap {
      width: 60%;
    }
    &__title {
      font-size: 2em;
    }
    .svg-bg {
      right: -20%;
      img {
        height: 85vh;
      }
    }
  }
}
@media (max-width: 992px) {
  .home {
    &__title-wrap {
      width: 70%;
    }
    &__title {
      font-size: 1.8em;
    }
    .svg-bg {
      img {
        height: 70vh;
      }
    }
  }
}
@media (max-width: 768px) {
  .home {
    &__overhead {
      font-size: 0.85em;
    }
    &__title {
      font-size: 1.4em;
    }
    .svg-bg {
      margin-top: 20%;
      right: -30%;
      img {
        height: 50vh;
      }
    }
  }
}
@media (max-width: 576px) {
  .home {
    &__title-wrap {
      width: 100%;
      margin-left: 0;
    }
    &__title {
      font-size: 1.2em;
    }
    .svg-bg {
      img {
        height: 40vh;
      }
    }
  }
}
</style>

<style lang="sass">
$color: #fff
$primary: #f84525bd

a
  text-decoration: none
  color: inherit

.home__btn-link
  position: relative
  margin: auto
  padding: 15px 22px
  transition: all .2s ease
  &:before
    content: ""
    position: absolute
    top: 0
    left: 0
    display: block
    border-radius: 28px
    background: rgba($primary,.5)
    width: 56px
    height: 56px
    transition: all .3s ease
  span
    position: relative
    font-size: 16px
    line-height: 18px
    font-weight: 900
    letter-spacing: .2em
    text-transform: uppercase
    vertical-align: middle
  svg
    position: relative
    top: 0
    margin-left: 10px
    fill: none
    stroke-linecap: round
    stroke-linejoin: round
    stroke: $color
    stroke-width: 2
    transform: translateX(-5px)
    transition: all .3s ease
  &:hover
    &:before
      width: 100%
      background: rgba($primary,1)
    svg
      transform: translateX(0)
  &:active
    transform: scale(.96)
</style>
