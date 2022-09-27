<template>
  <div id="app">
    <BaseHeader/>
    <MainBanner/>
    <CampaignArea/>
    <ThemesArea/>
    <BaseFooter/>
  </div>
</template>

<script>
import BaseHeader from './components/BaseHeader.vue'
import MainBanner from './components/MainBanner.vue'
import CampaignArea from './components/CampaignArea.vue'
import ThemesArea from './components/ThemesArea.vue'
import BaseFooter from './components/BaseFooter.vue'



export default {
  name: 'App',
  components: {
    BaseHeader,
    MainBanner,
    CampaignArea,
    ThemesArea,
    BaseFooter
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Montserrat&display=swap');
  :root{--primary-color: rgb(51, 51, 53);}
#app {
  font-family: Montserrat, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--primary-color);
}

.color-blue{
  color: #0b3795 !important;
}

.card-shadow{
        box-shadow: 0 0.3rem 2rem rgb(0 0 0 / 10%);
    }
</style>
