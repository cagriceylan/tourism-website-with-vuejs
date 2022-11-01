<template>
  <div class="carousel swiper-container card-shadow" ref="carousel">
    <div class="swiper-wrapper">
      <div v-for="(item, index) in sliderimg" class="swiper-slide" :key="item">
        <img
          :src="require(`@/assets/img/${item.img}`)"
          style="width: 100%; height: 100%; filter: blur(1px)"
        />
        <p class="swiper-title">{{ item.title }}</p>
        <h6 style="position: absolute; bottom: 0px; right: 0px">
          Campaign Number: {{ index }}
        </h6>
      </div>
    </div>

    <div class="swiper-pagination"></div>

    <div class="swiper-button-prev">
      <i class="fas fa-angle-left" />
    </div>
    <div class="swiper-button-next">
      <i class="fas fa-angle-right" />
    </div>
  </div>
</template>

<script>
import Swiper, { Autoplay, Navigation, Pagination } from "swiper";
import "swiper/swiper-bundle.min.css";
Swiper.use([Autoplay, Navigation, Pagination]);

export default {
  name: "BaseCarousel",

  props: {
    sliderimg: Array,
    //content: {  required: Boolean,  type: Array,},
  },

  mounted() {
    this.mountCarousel();
  },

  methods: {
    mountCarousel() {
      const carouselContainer = this.$refs.carousel;
      const swiper = new Swiper(carouselContainer, {
        autoplay: {
          disableOnInteraction: true,
        },
        centeredSlides: true,
        direction: "horizontal",
        loop: true,
        slidesPerView: 1,

        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev",
        },

        pagination: {
          clickable: true,
          el: ".swiper-pagination",
        },
      });

      carouselContainer.addEventListener("mouseenter", () => {
        swiper.autoplay.stop();
      });

      carouselContainer.addEventListener("mouseleave", () => {
        swiper.autoplay.start();
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.swiper {
  &-container {
    border: 1px solid transparent;
  }

  &-item {
    &:hover {
    }
  }

  &-slide {
    align-items: center;
    display: flex;
    font-family: sans-serif;
    font-weight: bold;
    height: 450px;
    justify-content: center;
  }
}

.swiper-button-next:after {
  color: white !important;
}

.swiper-button-prev:after {
  color: white !important;
}
.swiper-title {
  padding: 20px;
  position: absolute;
  top: 20px;
  right: 20px;
  background-color: rgba(255, 0, 0, 0.493);
  color: white;
  word-wrap: break-word;
  width: 200px;
}
</style>
