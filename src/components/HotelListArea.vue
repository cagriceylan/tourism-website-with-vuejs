<template>
  <!-- LİST AREA-->

  <div class="col-md-12 pl-md-4">
    <div class="row py-3 py-md-1">
      <div class="container px-0 text-center text-md-left">
        <BaseTitle :category_title="city.name + ' Hotels'" />
        <P
          >Showing <b>{{ hotelArray.length }}</b> Hotel for
          {{ city.name }} City</P
        >
      </div>
    </div>

    <div class="col-md-12">
      <div>
        <ul
          class="container nav nav-tabs flex-column flex-sm-row greyline nav-justified"
          id="myTab"
          role="tablist"
        >
          <li class="nav-item mr-1">
            <a
              class="nav-link nav-link2 active font-weight-bold color-blue text-left text-md-cente"
              id="home-tab"
              data-toggle="tab"
              href="#home2"
              role="tab"
              aria-controls="home"
              aria-selected="true"
              >All Tours</a
            >
          </li>
          <li class="nav-item">
            <a
              class="nav-link nav-link2 font-weight-bold color-blue text-left text-md-center"
              id="home-tab"
              data-toggle="tab"
              href="#home2"
              role="tab"
              aria-controls="home"
              aria-selected="false"
              >Ship Tours</a
            >
          </li>
          <li class="nav-item">
            <a
              class="nav-link nav-link2 font-weight-bold color-blue text-left text-md-center"
              id="home-tab"
              data-toggle="tab"
              href="#home2"
              role="tab"
              aria-controls="home"
              aria-selected="false"
              >Boutique Tours</a
            >
          </li>
          <li class="nav-item">
            <a
              class="nav-link nav-link2 font-weight-bold color-blue text-left text-md-center"
              id="home-tab"
              data-toggle="tab"
              href="#home2"
              role="tab"
              aria-controls="home"
              aria-selected="false"
              >En Çok Tercih Edilen</a
            >
          </li>
        </ul>
        <div class="tab-content pb-2" id="myTabContent">
          <div
            class="tab-pane fade show active"
            id="home2"
            role="tabpanel"
            aria-labelledby="home-tab"
          >
            <div
              class="container card-shadow mt-5 mt-md-4"
              v-for="(item, index) in hotelArray.slice(firstIndex, lastIndex)"
              :key="index"
            >
              <div class="row border">
                <div class="col-md-3 px-0">
                  <img
                    class="w-100 h-100"
                    src="https://www.eliteal-tur.com/images/upload/1__1628246790_2.jpg"
                  />
                  <i class="fa fa-heart fa-6"></i>
                </div>
                <div class="col-md-6 border-left">
                  <div class="row p-1 px-3 text-left">
                    <div class="col-5 px-0">
                      <small
                        v-for="i in item.destination"
                        :key="i"
                        :src="i.fullPath"
                        >{{ i.name }}
                      </small>
                    </div>
                    <div class="col-5 px-0">
                      <a href="" class="color-green"
                        ><small>haritada göster</small></a
                      >
                    </div>
                    <div
                      class="col-2 bg-green-soft color-blue px-0 text-center"
                    >
                      <small class="font-weight-bold">6.8 / 10</small>
                    </div>
                  </div>
                  <div class="row p-1">
                    <div
                      class="col-md-12 pt-1 line-height-tiny"
                      style="text-align: left"
                    >
                      <h5 class="font-weight-bold">
                        {{ item.name }}
                      </h5>
                      <p class="color-grey">{{ item.tourDay }}</p>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col-md-12 p-1 hide-mobile">
                      <div
                        class="col-md-6 color-green line-height-tiny text-left"
                        v-for="i in item.category"
                        :key="i"
                      >
                        <small class="font-size-10 bg-soft-blue px-2 rounded">{{
                          i.name
                        }}</small
                        ><br />
                      </div>
                    </div>
                  </div>
                </div>
                <div class="col-md-3 border-left text-right">
                  <div class="row">
                    <!--bu alan mobil tasarımda gizlencek-->
                    <div class="col-md-12 py-2 hide-mobile">
                      <small
                        class="font-size-12 p-1 font-weight-bold"
                        style="background: #ffd700; color: white"
                        >{{ item.star }} Yıldızlı</small
                      >
                      <h6 class="color-grey mt-1"><del></del>.</h6>
                      <h4 class="font-weight-bold">.</h4>
                      <p class="font-size-12 text-muted">
                        2 Gece /2 Kişi <br />
                        Toplam Fiyat
                      </p>
                    </div>
                  </div>
                  <div class="row">
                    <a
                      type="button"
                      :href="'#searchbar'"
                      class="btn btn-primary btn-block bg-green-gradient border-0 rounded-0 py-3"
                      style="padding-left: 28px; font-size: 14px"
                      >Fiyat bilgisi için tarih aralığı seçin!</a
                    >
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div
            class="tab-pane fade"
            id="profile2"
            role="tabpanel"
            aria-labelledby="profile-tab"
          >
            ...
          </div>
          <div
            class="tab-pane fade"
            id="contact2"
            role="tabpanel"
            aria-labelledby="contact-tab"
          >
            ...
          </div>
        </div>
      </div>
    </div>
    <div class="col-md-3 mx-auto mt-5">
      <BasePagination
        :itemCount="staticlenght"
        @firstIndex="example2"
        @lastIndex="example3"
      />
    </div>
  </div>
</template>

<script>
import BaseTitle from "./BaseTitle.vue";
import BasePagination from "./BasePagination.vue";
import axios from "axios";

export default {
  name: "HotelListArea",
  components: {
    BaseTitle,
    BasePagination,
  },
  data() {
    return {
      hotelArray: [],
      firstIndex: 0,
      lastIndex: 5,
      staticlenght: 50,
      city: "",
    };
  },
  methods: {
    example2(value) {
      console.log(value);
      this.firstIndex = value;
    },
    example3(value) {
      console.log(value);
      this.lastIndex = value;
    },
    async getData() {
      try {
        const response = await axios.post(
          "http://LOCALADRESS/api/seo_page/slug",
          {
            slug: "girne-otelleri",
            origin: "",
            checkIn: "",
            checkOut: "",
          },
          { headers: { "X-AUTH-TOKEN": "" } }
        );
        this.hotelArray = response.data.data.result;
        this.city = response.data.data.hotelDestination;
      } catch (e) {
        console.log(e);
      }
      //   .then((response) => {
      //     console.log(response);
      //     this.hotelArray = response.data.result;
      //   })
      //   .catch((error) => {
      //     console.error(error);
      //   });
    },
  },
  async created() {
    await this.getData();
  },
};
</script>

<style>
small {
  font-size: 14px !important;
}

.font-size-12 {
  font-size: 12px !important;
}

.line-height-tiny {
  line-height: 1.2;
}
.bg-soft-blue {
  background: powderblue;
}
</style>
