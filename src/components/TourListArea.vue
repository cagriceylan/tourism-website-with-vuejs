<template>
  <!-- LİST AREA-->
  <div class="col-md-12 pl-md-4">
    <div class="row py-3 py-md-1">
      <div class="container px-0 text-center text-md-left">
        <BaseTitle category_title="Antalya City Hotel" />
        <P
          >Showing <b>{{ tourArray.length }}</b> Hotel for Antalya City</P
        >
      </div>
    </div>

    <div class="col-md-12">
      <div>
        <ul
          class="
            container
            nav nav-tabs
            flex-column flex-sm-row
            greyline
            nav-justified
          "
          id="myTab"
          role="tablist"
        >
          <li class="nav-item mr-1">
            <a
              class="
                nav-link nav-link2
                active
                font-weight-bold
                color-blue
                text-left text-md-cente
              "
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
              class="
                nav-link nav-link2
                font-weight-bold
                color-blue
                text-left text-md-center
              "
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
              class="
                nav-link nav-link2
                font-weight-bold
                color-blue
                text-left text-md-center
              "
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
              class="
                nav-link nav-link2
                font-weight-bold
                color-blue
                text-left text-md-center
              "
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
              v-for="(item, index) in tourArray.slice(firstIndex, lastIndex)"
              :key="index"
            >
              <div class="row border">
                <div class="col-md-3 px-0">
                  <img class="w-100 h-100" :src="item.tourImg" />
                  <i class="fa fa-heart fa-6"></i>
                </div>
                <div class="col-md-6">
                  <div class="row p-1">
                    <div class="col-5 px-0">
                      <small>{{ item.tourCity }}/{{ item.tourCountry }}</small>
                    </div>
                    <div class="col-5 px-0">
                      <a href="" class="color-green"
                        ><small>Haritada Göster</small></a
                      >
                    </div>
                    <div
                      class="col-2 bg-green-soft color-blue px-0 text-center"
                    >
                      <small class="font-weight-bold">6.8 / 10</small>
                    </div>
                  </div>
                  <div class="row p-1">
                    <div class="col-md-12 pt-1 line-height-tiny" style="text-align: left;">
                        <h5 class="font-weight-bold">
                          {{ item.tourName }}
                        </h5>
                        <p class="color-grey">{{ item.tourDay }}</p>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col-md-12 p-1 hide-mobile">
                      <div class="col-md-4 color-green line-height-tiny">
                        <small class="font-size-10"
                          >Vade Farksız 12 Taksit</small
                        ><br />
                      </div>
                      <div class="col-md-4 color-green line-height-tiny">
                        <small class="font-size-10"
                          >Vade Farksız 12 Taksit</small
                        ><br />
                      </div>
                      <div class="col-md-4 color-green line-height-tiny">
                        <small class="font-size-10"
                          >Vade Farksız 12 Taksit</small
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
                        style="background: orange; color: white"
                        >{{ item.tourDate }}</small
                      >
                      <h6 class="color-grey mt-1"><del>3,513 TL</del></h6>
                      <h4 class="font-weight-bold">{{ item.tourPrice }} TL</h4>
                      <p class="font-size-12 text-muted">
                        2 Gece /2 Kişi <br />
                        Toplam Fiyat
                      </p>
                    </div>
                  </div>
                  <div class="row">
                    <a
                      type="button"
                      href="hotel-detail.html"
                      class="
                        btn btn-primary btn-block
                        bg-green-gradient
                        border-0
                        rounded-0
                        py-3
                      "
                      style="padding-left: 28px"
                      >Rezervasyon Yap</a
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
      <BasePagination :itemCount="tourArray.length" />
    </div>
  </div>
</template>

<script>
import BaseTitle from "./BaseTitle.vue";
import BasePagination from "./BasePagination.vue";

export default {
  name: "HotelListArea",
  components: {
    BaseTitle,
    BasePagination,
  },
  data() {
    return {
      tourArray: [
        {
          tourName: "Akdeniz Gemi Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/12/22",
          tourCategory: "Akdeniz Gemi Turları",
          tourPrice: "100",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Alpler Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/13/22",
          tourCategory: "Alpler Turları",
          tourPrice: "200",
          tourImg:
            "https://www.dalogluturizm.com/image/cache/Turlar/Yurt-Disi-Turlari/Buyuk-Balkan-Turu/balkan-turu-buyuk%20(7)-1000x600.jpg",
        },
        {
          tourName: "Amerika Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/14/22",
          tourCategory: "Amerika Turları",
          tourPrice: "300",
          tourImg: "https://www.fibartur.com/images/tour/137_b.jpg",
        },
        {
          tourName: "Amsterdam Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/15/22",
          tourCategory: "Amsterdam Turları",
          tourPrice: "400",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Azerbaycan Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/16/22",
          tourCategory: "Azerbaycan Turları",
          tourPrice: "500",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Balkan Turları (Otobüslü)",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/17/22",
          tourCategory: "Balkan Turları (Otobüslü)",
          tourPrice: "600",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Balkan Turları (Uçaklı)",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/18/22",
          tourCategory: "Balkan Turları (Uçaklı)",
          tourPrice: "700",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Baltık Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/19/22",
          tourCategory: "Baltık Turları",
          tourPrice: "800",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Baltıklar Gemi Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/20/22",
          tourCategory: "Baltıklar Gemi Turları",
          tourPrice: "900",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Belgrad Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/21/22",
          tourCategory: "Belgrad Turları",
          tourPrice: "1000",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Benelüks Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/22/22",
          tourCategory: "Benelüks Turları",
          tourPrice: "1100",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Beyrut Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/23/22",
          tourCategory: "Beyrut Turları",
          tourPrice: "1200",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Britanya Adaları Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/24/22",
          tourCategory: "Britanya Adaları Turları",
          tourPrice: "1300",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Britanya Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/25/22",
          tourCategory: "Britanya Turları",
          tourPrice: "1400",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Butik Kültür Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/26/22",
          tourCategory: "Butik Kültür Turları",
          tourPrice: "1500",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Dubai Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/27/22",
          tourCategory: "Dubai Turları",
          tourPrice: "1600",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Ege-Akdeniz Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/28/22",
          tourCategory: "Ege-Akdeniz Turları",
          tourPrice: "1700",
          tourImg:
            "https://www.kapadokyadayim.com/wp-content/uploads/2017/08/kapadokya-nerede-2.jpg",
        },
        {
          tourName: "Endülüs Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/29/22",
          tourCategory: "Endülüs Turları",
          tourPrice: "1800",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
        {
          tourName: "Fas Gemi Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/30/22",
          tourCategory: "Fas Gemi Turları",
          tourPrice: "1900",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
        {
          tourName: "Fas Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "12/31/22",
          tourCategory: "Fas Turları",
          tourPrice: "2000",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
        {
          tourName: "Festival Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "1/1/23",
          tourCategory: "Festival Turları",
          tourPrice: "2100",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
        {
          tourName: "Fransa Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "1/2/23",
          tourCategory: "Fransa Turları",
          tourPrice: "2200",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
        {
          tourName: "Gap Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "1/3/23",
          tourCategory: "Gap Turları",
          tourPrice: "2300",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
        {
          tourName: "Gemi Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "1/4/23",
          tourCategory: "Gemi Turları",
          tourPrice: "2400",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
        {
          tourName: "Helikopter Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "1/5/23",
          tourCategory: "Helikopter Turları",
          tourPrice: "2500",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
        {
          tourName: "Hindistan Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "1/6/23",
          tourCategory: "Hindistan Turları",
          tourPrice: "2600",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
        {
          tourName: "İskandinavya ve Fiyordlar Turları",
          tourCity: "İstanbul",
          tourCountry: "Türkiye",
          tourDay: "3 gece 4 gün",
          tourDate: "1/7/23",
          tourCategory: "İskandinavya ve Fiyordlar Turları",
          tourPrice: "2700",
          tourImg:
            "https://c.gruppal.com/tmp/symphony-seas-akdeniz-gemi-turu-resimi.jpg",
        },
      ],
      firstIndex : 0,
      lastIndex : 5,
    };
  },
};
</script>

<style>
small {
  font-size: 7px;
}

.line-height-tiny {
  line-height: 0.9;
}
</style>