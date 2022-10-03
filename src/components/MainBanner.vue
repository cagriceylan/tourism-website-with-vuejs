<template id="">
  <div class="MainBanner">
    <!-- Main Banner Area-->
    <div class="container-fluid">
      <div
        class="
          row
          position-relative
          overflow-hidden
          text-center
          main-search-area-banner
        "
        id="searchbar"
      >
        <div class="container">
          <div class="row row-p-5">
            <ul class="nav nav-tabs w-100" id="myTab" role="tablist">
              <li class="nav-item mr-2 bg-green-transparent">
                <a
                  class="nav-link active rounded-0"
                  id="home-tab"
                  data-toggle="tab"
                  href="#home"
                  role="tab"
                  aria-controls="home"
                  aria-selected="true"
                  >OTEL</a
                >
              </li>
              <li class="nav-item mr-2 bg-green-transparent">
                <a
                  class="nav-link text-white rounded-0"
                  id="profile-tab"
                  data-toggle="tab"
                  href="#home"
                  role="tab"
                  aria-controls="profile"
                  aria-selected="false"
                  >OTEL+UÇAK+TRANSFER</a
                >
              </li>
              <li class="nav-item mr-2 bg-green-transparent">
                <a
                  class="nav-link text-white rounded-0"
                  id="profile-tab"
                  data-toggle="tab"
                  href="#profile"
                  role="tab"
                  aria-controls="profile"
                  aria-selected="false"
                  >TUR</a
                >
              </li>
            </ul>
            <div
              class="tab-content bg-white card-shadow w-100 main-search-content"
              id="myTabContent"
            >
              <div
                class="tab-pane fade show active pb-0 p-md-4"
                id="home"
                role="tabpanel"
                aria-labelledby="home-tab"
              >
                <form class="needs-validation" novalidate>
                  <div class="form-row">
                    <div class="col-md-3 mb-0 mb-md-3">
                      <input v-model="sehir"
                        type="text"
                        class="form-control border-0 py-md-4"
                        placeholder="City"
                        aria-label="Bölge ara"
                        style="border-bottom: 2px solid #dee2e6 !important"
                      />
                      <p>{{ sonuc }}</p>
                    </div>
                    <div class="col-md-3 mb-0 mb-md-3">
                      <input
                        type="text"
                        class="form-control border-0 py-md-4"
                        placeholder="Giriş / Çıkış Tarihi"
                        aria-label="Giriş / Çıkış Tarihi"
                        style="border-bottom: 2px solid #dee2e6 !important"
                      />
                      <div class="valid-feedback">Looks good!</div>
                      <div class="valid-feedback">Looks good!</div>
                    </div>
                    <div class="col-md-4 mb-0 mb-md-3">
                      <div class="input-group">
                        <input
                          type="text"
                          class="form-control border-0 py-md-4"
                          placeholder="2 Yetişkin"
                          aria-label="2 Yetişkin"
                          style="border-bottom: 2px solid #dee2e6 !important"
                        />
                        <div class="invalid-feedback">
                          Please choose a username.
                        </div>
                      </div>
                    </div>
                    <div class="col-md-2 mb-0 mb-md-3">
                      <a
                        class="
                          btn btn-primary
                          w-100
                          bg-green-gradient
                          border-0
                          py-md-3
                        "
                        @click="search(sehir)"
                        >ARAMA YAP</a
                      >
                    </div>
                  </div>
                </form>
              </div>
              <div
                class="tab-pane fade pb-0 p-md-4"
                id="profile"
                role="tabpanel"
                aria-labelledby="profile-tab"
              >
                <form class="needs-validation2" novalidate>
                  <div class="form-row">
                    <div class="col-md-3 mb-3">
                      <input
                        type="text"
                        class="form-control border-0 py-md-4"
                        placeholder="Örn: Balkanlar, İsviçre, Paris"
                        aria-label="Örn: Balkanlar, İsviçre, Paris"
                        style="border-bottom: 2px solid #dee2e6 !important"
                      />
                      <div class="valid-feedback">Looks good!</div>
                    </div>
                    <div class="col-md-3 mb-3">
                      <input
                        type="text"
                        class="form-control border-0 py-md-4"
                        placeholder="Dönem"
                        aria-label="Dönem"
                        style="border-bottom: 2px solid #dee2e6 !important"
                      />
                      <div class="valid-feedback">Looks good!</div>
                      <div class="valid-feedback">Looks good!</div>
                    </div>
                    <div class="col-md-4 mb-3">
                      <div class="input-group">
                        <input
                          type="text"
                          class="form-control border-0 py-md-4"
                          placeholder="2 Yetişkin"
                          aria-label="2 Yetişkin"
                          style="border-bottom: 2px solid #dee2e6 !important"
                        />
                        <div class="invalid-feedback">
                          Please choose a username.
                        </div>
                      </div>
                    </div>
                    <div class="col-md-2 mb-3">
                      <a
                        class="
                          btn btn-primary
                          w-100
                          bg-green-gradient
                          border-0
                          py-md-3
                        "
                        href="tour-list.html"
                        type="submit"
                        >ARAMA YAP</a
                      >
                    </div>
                  </div>
                </form>
              </div>
              <div
                class="tab-pane fade pb-0 p-md-4"
                id="contact"
                role="tabpanel"
                aria-labelledby="contact-tab"
              >
                ...
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MainBanner",
  props: {},
  methods:{
    search(a){
      if(this.city.includes(a)){
        this.sonuc = "basarili";
      }
      else{
        this.sonuc = "basarisiz";
      }
    }
  },
  data(){
    return{
      sonuc: "",
      sehir: "City",
       city : ["Adana","Adiyaman","Afyon","Agri","Aksaray","Amasya","Ankara","Antalya","Ardahan","Artvin","Aydin","Balikesir","Bartin","Batman","Bayburt","Bilecik","Bingol","Bitlis","Bolu","Burdur","Bursa","Canakkale","Cankiri","Corum","Denizli","Diyarbakir","Duzce","Edirne","Elazig","Erzincan","Erzurum","Eskisehir","Gaziantep","Giresun","Gumushane","Hakkari","Hatay","Igdir","Isparta","Istanbul","Izmir","Kahramanmaras","Karabuk","Karaman","Kars","Kastamonu","Kayseri","Kilis","Kirikkale","Kirklareli","Kirsehir","Kocaeli","Konya","Kutahya","Malatya","Manisa","Mardin","Mersin","Mugla","Mus","Nevsehir","Nigde","Ordu","Osmaniye","Rize","Sakarya","Samsun","Sanliurfa","Siirt","Sinop","Sirnak","Sivas","Tekirdag","Tokat","Trabzon","Tunceli","Usak","Van","Yalova","Yozgat","Zonguldak"]

    }
  }
};
</script>

<style>
.MainBanner {
  background: url('@/assets/img/banner.png');
  background-size: 100% !important;
  background-repeat: no-repeat !important;
}

#searchbar{
  padding-top: 100px;
  padding-bottom: 100px;
}

.bg-green-transparent {
    background-color: var(--primary-color);
    color: white;
}

.active{
color: var(--primary-color);
}

.btn-primary{
  
  background-color: var(--primary-color) !important;
}
</style>