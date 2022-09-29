<template>
  <div id="ThemesArea">
    <BaseTitle category_title="TEMALAR"/>
    <div class="container-fluid mt-3">
      <div class="row row-p-5">
        <div class="col-4 col-md p-0 scale" v-for="(item,i) in themes" :key="i">
          <div class="card h-100 border-0 card-special text-white">
            <a href="hotel-list.html" class="card-text">  
              <img class="card-img" :src ="require(`@/assets/img/${item.img}`)"> 
              <div class="card-img-overlay bg-dark-gradient -">
                <h5 class="card-title on-image">{{item.name}}</h5>
              </div>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import BaseTitle from "./BaseTitle.vue";
export default {
    name:"ThemesArea",
    components:{
        BaseTitle
    },
    data(){
        return{
            themes: [
                {img:"theme-1.png", name:"ERKEN REZERVASYON"},
                {img:"theme-2.png", name:"YURTİÇİ TUR"},
                {img:"theme-3.png", name:"YURTDIŞI TUR"},
                {img:"theme-4.png", name:"KIBRIS"},
                {img:"theme-5.png", name:"BALAYI OTELLERİ"},
                {img:"theme-6.png", name:"KAYAK OTELLERİ"}
            ]
        }
    },
    props:{}
}
</script>

<style>
  .on-image{
    position: absolute;
    left: 27px;
    bottom: 50px;
    font-size: 20px;
    color: #fff;
    z-index: 1;
  }

  .card-img-overlay {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    padding: 1.25rem;
}

.card-img-overlay {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    padding: 1.25rem;
}

.bg-dark-gradient {
    background: linear-gradient(0deg, rgba(0,0,0,0.925754060324826) 0%, rgba(255,255,255,0) 58%);
}
</style>