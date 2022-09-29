<template>
  <div id="CampaignArea">
    <BaseTitle category_title="KAMPANYALAR" />

    <div class="container mt-3">
      <div class="row row-p-5">
        <div class="col-md-4 order-2 order-md-1 mt-md-0 mt-3">
          <CampaignItem
            v-for="(item, i) in campaignData.slice(0, count)"
            :key="i"
            :item="item"
          />
          <a class="button-link float-right p-3" @click="itemshower">{{buttonText}}</a
          >
        </div>

        <div class="col-md-8 order-1 order-md-2">
          <div class="row pl-md-3">
            <BaseCarousel :sliderimg="campaign2Data"/>
          </div>
          <div class="row float-right">
            <a type="button" class="float-right color-green small"></a>
            <a class="button-link float-right" href="hotel-list.html"
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
import BaseCarousel from "./BaseCarousel.vue";


export default {
  name: "CampaignArea",
  components: {
    CampaignItem,
    BaseTitle,
    BaseCarousel,
  },
  data() {
    return {
      buttonText: "Tümünü Göster",
      campaignData: [
        { title: "TITLE1", discount: 33 },
        { title: "TITLE2", discount: 14 },
        { title: "TITLE3", discount: 13 },
        { title: "TITLE4", discount: 23 },
        { title: "TITLE5", discount: 13 },
        { title: "TITLE6", discount: 23 },
      ],
      campaign2Data: [
        { img: "c1.jpg", title: "Best Travel Acency Just For You With %20 Discout!"},
        { img: "c2.jpg", title: "Best Travel Acency Just For You With %20 Discout!"},
        { img: "c3.jpg", title: "Best Travel Acency Just For You With %20 Discout!"},
        { img: "c4.jpg", title: "Best Travel Acency Just For You With %20 Discout!"},
        { img: "c5.jpg", title: "Best Travel Acency Just For You With %20 Discout!"},
        { img: "c6.jpg", title: "Best Travel Acency Just For You With %20 Discout!"},
        { img: "c7.jpg", title: "Best Travel Acency Just For You With %20 Discout!"},
      ],
      count: this.howMuchItem
    };
  },
  props:{
    howMuchItem: {
      default:3
    }
  },
  methods: {
    itemshower: function(){
      if(this.count == this.howMuchItem){
        this.count = this.campaignData.lenght;
        this.buttonText = "Gizle";
      }
      else{
        this.count = this.howMuchItem;
        this.buttonText = "Tümünü Göster";
      }

    }

  }
};
</script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
#CampaignArea {
  box-shadow: 0 0.3rem 2rem rgb(0 0 0 / 11%);
  padding-top: 30px;
  padding-bottom: 30px;
}

</style>
  