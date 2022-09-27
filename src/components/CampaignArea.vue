<template>


  <div id="CampaignArea">
    <BaseTitle category_title="KAMPANYALAR"/>

    <div class="container mt-3">
      <div class="row row-p-5">
        <div class="col-md-4 order-2 order-md-1 mt-md-0 mt-3">
          <CampaignItem v-for="(item,i) in CampaignData" :key="i" :item="item"/>

        </div>

        <div class="col-md-8 order-1 order-md-2">
          <div class="row pl-md-3">
            <div
              id="carouselExampleIndicators"
              class="carousel slide w-100"
              data-ride="carousel"
            >
              <ol class="carousel-indicators">
                <li
                  data-target="#carouselExampleIndicators"
                  data-slide-to="0"
                  class="active"
                ></li>
                <li
                  data-target="#carouselExampleIndicators"
                  data-slide-to="1"
                ></li>
                <li
                  data-target="#carouselExampleIndicators"
                  data-slide-to="2"
                ></li>
              </ol>
              <div class="carousel-inner">
                <div class="carousel-item active">
                  <img
                    class="d-block w-100 campaign-img"
                    src="@/assets/img/campaign-banner.png"
                    alt="First slide"
                  />
                </div>
                <div class="carousel-item">
                  <img
                    class="d-block w-100 campaign-img"
                    src="@/assets/img/campaign-banner.png"
                    alt="Second slide"
                  />
                </div>
                <div class="carousel-item">
                  <img
                    class="d-block w-100 campaign-img"
                    src="@/assets/img/campaign-banner.png"
                    alt="Third slide"
                  />
                </div>
              </div>
              <a
                class="carousel-control-prev"
                href="#carouselExampleIndicators"
                role="button"
                data-slide="prev"
              >
                <span
                  class="carousel-control-prev-icon"
                  aria-hidden="true"
                ></span>
                <span class="sr-only">Previous</span>
              </a>
              <a
                class="carousel-control-next"
                href="#carouselExampleIndicators"
                role="button"
                data-slide="next"
              >
                <span
                  class="carousel-control-next-icon"
                  aria-hidden="true"
                ></span>
                <span class="sr-only">Next</span>
              </a>
            </div>
          </div>
          <div class="row float-right">
            <a type="button" class="float-right color-green small"></a>
            <a class="color-green small float-right" href="hotel-list.html"
              >Tüm Kampanyaları Görüntüle</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
  
  <script>
import BaseTitle from "./BaseTitle.vue";
import CampaignItem from "./CampaignItem.vue";

export default {
  name: "CampaignArea",
  props: {},
  components: {
    CampaignItem,
    BaseTitle
},
data(){
    return{
        CampaignData: [
            {title: "TITLE1", discount: 33},
            {title: "TITLE2", discount: 14},
            {title: "TITLE3", discount: 13},
            {title: "TITLE4", discount: 23}
    ]}
    }
};
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
#CampaignArea {
  border-bottom: 2px solid rgb(235, 211, 211);
  box-shadow: 0 0.3rem 2rem rgb(0 0 0 / 10%);
}
</style>
  