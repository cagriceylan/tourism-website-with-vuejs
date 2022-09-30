<template>
  <div id="BaseTitle">
    <div class="container mt-4">
      <div class="row row-p-5">
        <div class="col-md-4">
          <div class="row" style="border-bottom: 2px solid #dee2e6">
            <h5 class="font-weight-bold">{{category_title}}</h5>
          </div>
          <div class="row reveal fade-left greenline"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name:"BaseTitle",
    props:{
        category_title : String
    }

};
</script>

<style>
    #BaseTitle{

    }

    .greenline{
        border-bottom: 2px solid var(--primary-color);
    }
</style>