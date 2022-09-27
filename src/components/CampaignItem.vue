<template>
  <div id="CampaignItem">
    <div class="row card-shadow mt-3">
      <div class="col-4 col-md-4 p-0">
        <img class="d-block w-100" src="@/assets/img/campaign.png">
      </div>
      <div class="col-8 col-md-8 px-1">
        <div class="card border-0">
          <div class="card-body">
            <h6 class="card-title text-left">{{item.title}} WITH DISCOUNT %{{item.discount}}</h6>
          </div>
          <div class="card-body-space"></div>
          <div class="card-body">
            <a class="color-green small float-right" href="index.html">Detaylar</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "CampaignItem",
    props:{
      index: Number,
      item: Object
    } 
};
</script>

<style>
  h6{
    font-size: 12px !important;
    font-weight: bold !important;
  }

</style>