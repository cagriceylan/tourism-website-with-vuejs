<template>
  <div id="app">
    <BaseHeader/>
    <MainBanner/>
    <BaseBlogArea/>
    <CampaignArea :howMuchItem="3" />
    <ThemesArea/>
    <TourListArea/>
    <HotelListArea/>
    <BaseFooter/>
  </div>
</template>

<script>
import BaseHeader from './components/BaseHeader.vue'
import MainBanner from './components/MainBanner.vue'
import BaseBlogArea from './components/BaseBlogArea.vue'
import CampaignArea from './components/CampaignArea.vue'
import ThemesArea from './components/ThemesArea.vue'
import BaseFooter from './components/BaseFooter.vue'
import TourListArea from './components/TourListArea.vue'
import HotelListArea from './components/HotelListArea.vue'


export default {
  name: 'App',
  components: {
    BaseHeader,
    MainBanner,
    CampaignArea,
    ThemesArea,
    BaseFooter,
    TourListArea,
    HotelListArea,
    BaseBlogArea
  },
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Montserrat&display=swap');
  :root{--primary-color: rgb(11 55 149);}
#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--primary-color);
}

.color-blue{
  color: var(--primary-color) !important;
}

.card-shadow{
        box-shadow: 0 0.3rem 2rem rgb(0 0 0 / 10%);
    }

.button-link {
  color: var(--primary-color);
  font-size: 10px;
  background: transparent;
}
.scale{
  overflow: hidden;
  
}
.scale img{

  transition: all 0.1s ease-in-out;
}
.scale:hover img {


transform: scale(1.2);
}
</style>
