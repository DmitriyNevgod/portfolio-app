<template>
  <div class="contact full-screen">
    <div class="overlay">
      <el-row type="flex" justify="center" align="middle">
        <el-col :span="24" class="contact__title-wrap">
          <h1 class="contact__title">Дмитрий Невгод</h1>
          <span class="contact__subtitle">Web Developer</span>
        </el-col>
      </el-row>
      <el-row type="flex" justify="center" align="middle">
        <el-col :span="24" class="contact__body">
          <h2 class="contact__body-title">
            Мы должны узнать друг друга поближе!
          </h2>
          <a class="contact__body-email" href="mailto:nevgod.dm@gmail.com">
            nevgod.dm@gmail.com
          </a>
        </el-col>
      </el-row>
      <el-row type="flex" justify="center" align="middle">
        <el-col :span="24">
          <ul class="contact__social-list">
            <li class="contact__item">
              <a href="https://www.facebook.com/dmitriy.nevgod" target="_blank">
                <svg
                  aria-hidden="true"
                  focusable="false"
                  data-prefix="fab"
                  data-icon="facebook-f"
                  class="svg-inline--fa fa-facebook-f fa-w-10"
                  role="img"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 320 512"
                >
                  <path
                    fill="#fff"
                    d="M279.14 288l14.22-92.66h-88.91v-60.13c0-25.35 12.42-50.06 52.24-50.06h40.42V6.26S260.43 0 225.36 0c-73.22 0-121.08 44.38-121.08 124.72v70.62H22.89V288h81.39v224h100.17V288z"
                  ></path>
                </svg>
              </a>
            </li>
            <li class="contact__item">
              <a
                href="https://www.instagram.com/dmitriy.nevgod/"
                target="_blank"
              >
                <svg
                  aria-hidden="true"
                  focusable="false"
                  data-prefix="fab"
                  data-icon="instagram"
                  class="svg-inline--fa fa-instagram fa-w-14"
                  role="img"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 448 512"
                >
                  <path
                    fill="#fff"
                    d="M224.1 141c-63.6 0-114.9 51.3-114.9 114.9s51.3 114.9 114.9 114.9S339 319.5 339 255.9 287.7 141 224.1 141zm0 189.6c-41.1 0-74.7-33.5-74.7-74.7s33.5-74.7 74.7-74.7 74.7 33.5 74.7 74.7-33.6 74.7-74.7 74.7zm146.4-194.3c0 14.9-12 26.8-26.8 26.8-14.9 0-26.8-12-26.8-26.8s12-26.8 26.8-26.8 26.8 12 26.8 26.8zm76.1 27.2c-1.7-35.9-9.9-67.7-36.2-93.9-26.2-26.2-58-34.4-93.9-36.2-37-2.1-147.9-2.1-184.9 0-35.8 1.7-67.6 9.9-93.9 36.1s-34.4 58-36.2 93.9c-2.1 37-2.1 147.9 0 184.9 1.7 35.9 9.9 67.7 36.2 93.9s58 34.4 93.9 36.2c37 2.1 147.9 2.1 184.9 0 35.9-1.7 67.7-9.9 93.9-36.2 26.2-26.2 34.4-58 36.2-93.9 2.1-37 2.1-147.8 0-184.8zM398.8 388c-7.8 19.6-22.9 34.7-42.6 42.6-29.5 11.7-99.5 9-132.1 9s-102.7 2.6-132.1-9c-19.6-7.8-34.7-22.9-42.6-42.6-11.7-29.5-9-99.5-9-132.1s-2.6-102.7 9-132.1c7.8-19.6 22.9-34.7 42.6-42.6 29.5-11.7 99.5-9 132.1-9s102.7-2.6 132.1 9c19.6 7.8 34.7 22.9 42.6 42.6 11.7 29.5 9 99.5 9 132.1s2.7 102.7-9 132.1z"
                  ></path>
                </svg>
              </a>
            </li>
            <li class="contact__item">
              <a href="https://t.me/dmitriy_nevgod" target="_blank">
                <svg
                  aria-hidden="true"
                  focusable="false"
                  data-prefix="fab"
                  data-icon="telegram-plane"
                  class="svg-inline--fa fa-telegram-plane fa-w-14"
                  role="img"
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 448 512"
                >
                  <path
                    fill="#fff"
                    d="M446.7 98.6l-67.6 318.8c-5.1 22.5-18.4 28.1-37.3 17.5l-103-75.9-49.7 47.8c-5.5 5.5-10.1 10.1-20.7 10.1l7.4-104.9 190.9-172.5c8.3-7.4-1.8-11.5-12.9-4.1L117.8 284 16.2 252.2c-22.1-6.9-22.5-22.1 4.6-32.7L418.2 66.4c18.4-6.9 34.5 4.1 28.5 32.2z"
                  ></path>
                </svg>
              </a>
            </li>
          </ul>
        </el-col>
      </el-row>
    </div>

    <video
      loop
      muted
      autoplay
      poster="video/plane.jpg"
      class="contact-bg__video"
    >
      <source
        :src="require('../assets/video/contact-bg.mp4')"
        type="video/mp4"
      />
      <source
        :src="require('../assets/video/contact-bg.webm')"
        type="video/webm"
      />
    </video>
  </div>
</template>

<script>
export default {
  mounted() {},
};
</script>

<style lang="scss">
.contact {
  background: #1f1e1d;
  color: #fff;
  overflow: hidden;
  z-index: -100;
  position: absolute;
  width: 100%;
  .overlay {
    background: #000000a2;
    position: relative;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 200;
  }
  &-bg__video {
    object-fit: cover;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -100;
  }
  &__title-wrap {
    margin-top: 120px;
    margin-bottom: 70px;
    text-align: center;
  }
  &__title {
    margin-bottom: 20px;
    font-size: 2.3em;
    letter-spacing: 0.08em;
  }
  &__subtitle {
    color: #f84525;
    letter-spacing: 0.25em;
  }
  &__body {
    text-align: center;
    &-title {
      font-weight: 300;
      margin: 40px 0;
      letter-spacing: 0.05em;
    }
    &-email {
      font-size: 3em;
      letter-spacing: 0.2em;
      font-weight: 600;
      color: #fff;
      &:hover {
        color: #f84525cc;
        text-decoration: underline;
      }
    }
  }
  &__social-list {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 5%;
  }
  &__item {
    height: 100px;
    width: 100px;
    border: 1px solid #fff;
    border-radius: 50%;
    margin-right: 30px;
    a {
      display: flex;
      border-radius: 50%;
      justify-content: center;
      align-items: center;
      height: 100%;
      width: 100%;
    }
    svg {
      height: 50%;
      width: 50%;
    }
    &:hover {
      background: #fff;
      svg path {
        fill: #000;
      }
    }
  }
}
@media (max-width: 1200px) {
  .contact {
    &__body-title {
      font-size: 1.3em;
    }
    &__body-email {
      font-size: 2.7em;
    }
  }
}
@media (max-width: 992px) {
  .contact {
    &__body-title {
      font-size: 1.2em;
    }
    &__body-email {
      font-size: 2em;
    }
  }
}
@media (max-width: 767px) {
  .contact {
    &__body-title {
      font-size: 0.9em;
      margin: 20px 0;
    }
    &__body-email {
      font-size: 1.5em;
    }
  }
}
@media (max-width: 576px) {
  .contact {
    &__title {
      font-size: 1.7em;
    }
    &__subtitle {
      font-size: 0.8em;
    }
    &__body-title {
      font-size: 0.8em;
      margin: 10px 0;
    }
    &__body-email {
      font-size: 1.1em;
    }
    &__item {
      width: 80px;
      height: 80px;
      margin-top: 20vh;
    }
  }
}
</style>
