<template>
  <div class="portfolio full-screen">
    <el-row type="flex" justify="center" align="middle">
      <el-col :span="24">
        <h1 class="portfolio__title">Портфолио</h1>
      </el-col>
    </el-row>

    <el-row type="flex" justify="center" align="middle" class="portfolio-bg">
      <el-col :sm="24" :md="20">
        <ul class="portfolio__list">
          <li
            class="portfolio__item"
            :class="{ 'item-margin': renderItems(idx) }"
            v-for="(item, idx) in portfolioList"
            :key="item.title"
          >
            <a
              :href="item.path"
              target="_blank"
              v-if="renderItems(idx)"
              class="portfolio__item-link"
            >
              <div class="portfolio__card">
                <img
                  :src="item.img"
                  :alt="item.title"
                  class="portfolio__card-img"
                />

                <hr />
                <div class="portfolio__card-body">
                  <h4 class="portfolio__card-title">{{ item.title }}</h4>
                  <span class="portfolio__card-date">{{ item.date }}</span>
                  <p class="portfolio__card-text" v-html="item.text"></p>
                  <a
                    v-if="item.gitLink !== null"
                    class="portfolio__card-btn"
                    :href="item.gitLink"
                    target="_blank"
                  >
                    Git
                  </a>
                </div>
              </div>
            </a>
          </li>
        </ul>
        <div class="portfolio__btn">
          <button @click="loadMore()" ref="loadMoreBtn">Загрузить ещё</button>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 3,
      portfolioList: [
        {
          title: "ZeBoard",
          img: require("../assets/img/portfolio-page/zeboard.png"),
          path: null,
          date: "23.04.2021",
          text: "Первое приложение на VueJS <br> В разработке*",
          gitLink: null,
        },
        {
          title: "ToDoList on ReactJS",
          img: require("../assets/img/portfolio-page/ToDoReact.png"),
          path: "https://react-todo-159f5.web.app/",
          date: "08.04.2021",
          text:
            "Простое приложение на ReactJS <br> Связано с Firebase <br> (все изменения будут видны всем пользователям)",
          gitLink: null,
        },
        {
          title: "Normalno",
          img: require("../assets/img/portfolio-page/normalno.png"),
          path: "http://normalno.in.ua/",
          date: "29.03.2021",
          text:
            "оптимизация кода для поисковой выдачи <br> ускорение скорости загрузки сайта на 42% <br> оптимизация сайта для мобильных устройств",
          gitLink: null,
        },
        {
          title: "Neftegaz",
          img: require("../assets/img/portfolio-page/neftegaz.png"),
          path: "https://neftegaz.by/",
          date: "10.11.2020",
          text:
            "оптимизация кода для поисковой выдачи <br> оптимизация сайта для мобильных устройств",
          gitLink: null,
        },
        {
          title: "NativeLab",
          img: require("../assets/img/portfolio-page/nativelab.png"),
          path: "http://moon7.beget.tech/nativelab/",
          date: "30.07.2020",
          text: "Вёрстка по макету PSD <br> *проект заморожен",
          gitLink: null,
        },
        {
          title: "Мой дворик(WP)",
          img: require("../assets/img/portfolio-page/dvorik-wp.png"),
          path: null,
          date: "11.03.2020",
          text: "работа с шаблоном WordPress <br> *проект заморожен",
          gitLink: null,
        },
        {
          title: "Сантехника",
          img: require("../assets/img/portfolio-page/plumbing.png"),
          path: "http://moon7.beget.tech/plumbing/",
          date: "09.01.2020",
          text: "вёрстка по макету PSD  <br> *проект заморожен",
          gitLink: null,
        },
        {
          title: "Мой дворик(MODx)",
          img: require("../assets/img/portfolio-page/dvorik.png"),
          path: "https://dvorik-31.ru/",
          date: "19.06.2019",
          text:
            "Вёрстка и настройка форм обратной связи <br> Удаление небезопасных скриптов <br> Работа с CMS MODX Evo <br> Разработка калькулятора на JS(JQuery) <br> Мелкие правки <br> *проект заморожен",
          gitLink: null,
        },
        {
          title: "Мой дворик(Форма для рассчётов)",
          img: require("../assets/img/portfolio-page/dvorik-calc.png"),
          path: "http://moon7.beget.tech/dvorik-calculator/",
          date: "03.08.2019",
          text: "Создание формы для рассчётов цены на изделия",
          gitLink: null,
        },
        {
          title: "Appo",
          img: require("../assets/img/portfolio-page/appo.png"),
          path: "http://moon7.beget.tech/appo/",
          date: "27.05.2019",
          text: "Вёрстка по макету PSD",
          gitLink: null,
        },
        {
          title: "Креатив Медиа",
          img: require("../assets/img/portfolio-page/creative.png"),
          path: "http://moon7.beget.tech/creative/",
          date: "11.04.2019",
          text: "Вёрстка по макету PSD",
          gitLink: null,
        },
        {
          title: "CreditAsia",
          img: require("../assets/img/portfolio-page/CreditAsia.png"),
          path: "http://moon7.beget.tech/creditasia/",
          date: "13.02.2019",
          text: "Вёрстка по макету PSD",
          gitLink: null,
        },
      ],
    };
  },
  methods: {
    renderItems(n) {
      if (this.count <= this.portfolioList.length) {
        return n < this.count ? true : false;
      } else {
        this.$refs.loadMoreBtn.style.display = "none";
        return true;
      }
    },
    loadMore(str) {
      let width = document.body.clientWidth;
      const setCount = (n) => {
        console.log("1", this.count);
        this.count += n;
        console.log("2", this.count);
      };
      if (str === "init") {
        width > 1200
          ? (this.count = 3)
          : width <= 1200 && width >= 767
          ? (this.count = 2)
          : width < 767
          ? (this.count = 1)
          : null;
      } else {
        width > 1200
          ? setCount(3)
          : width <= 1200 && width >= 767
          ? setCount(2)
          : width < 767
          ? setCount(1)
          : null;
      }
    },
  },
  created() {
    this.loadMore("init");
  },
};
</script>

<style lang="scss">
.portfolio {
  background: #eeeeee;
  &-bg {
    background: #eeeeee;
  }
  &__title {
    margin-top: 120px;
    margin-bottom: 100px;
    text-align: center;
  }
  &__list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  &__item {
    background: #fff;
    width: 30%;

    &-link {
      height: 100%;
    }
    img {
      width: 100%;
      height: 100%;
    }
  }
  .item-margin {
    margin-bottom: 30px;
    margin-right: 30px;
  }
  &__card-body {
    padding: 15px;
    color: #000;
  }
  &__card {
    hr {
      margin-top: 20px;
      margin-bottom: 0;
      border: 1px solid #888;
      opacity: 0.5;
    }
    &-title {
      margin-bottom: 15px;
      font-size: 1.2em;
    }
    &-date {
      font-size: 0.7em;
      color: #888;
    }
    &-text {
      margin: 15px 0;
    }
    &-btn {
      color: #f84525;
      font-size: 1em;
      padding: 4px 10px;
      border-radius: 15px;
      font-weight: 700;
      &:hover {
        background: #f84525;
        color: #fff;
      }
    }
  }
  &__btn {
    text-align: center;
    margin: 20px 0;
    button {
      background: #f84525;
      border-radius: 28px;
      color: #fff;
      font-size: 0.8em;
      line-height: 1em;
      font-weight: 600;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      padding: 18px 22px;
      &:hover {
        background: #ee664e;
      }
    }
  }
}
@media (max-width: 1200px) {
  .portfolio {
    &__title {
      margin-top: 100px;
      margin-bottom: 60px;
    }
    &__card-text {
      font-size: 0.8em;
    }
    & .item-margin {
      margin-bottom: 15px;
      margin-right: 15px;
    }
  }
}
@media (max-width: 992px) {
  .portfolio {
    &__item {
      width: 47%;
      &:nth-child(even).item-margin {
        margin-right: 0px;
      }
    }
    &__card-btn {
      background: #f84525;
      color: #fff;
      padding: 5px 25px;
    }
  }
}
@media (max-width: 767px) {
  .portfolio {
    &__title {
      margin-bottom: 25px;
    }
    &__item {
      width: 100%;
    }
    .item-margin {
      margin-right: 0px;
    }
    &__card-btn {
      padding: 5px 25px;
      display: block;
      text-align: center;
    }
  }
}
</style>
