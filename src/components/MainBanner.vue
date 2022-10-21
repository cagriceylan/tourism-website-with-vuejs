<template id="MainBanner">
  <div class="MainBanner">
    <!-- Main Banner Area-->
    <div class="container-fluid">
      <div
        class="row position-relative overflow-hidden text-center main-search-area-banner"
        id="searchbar"
      >
        <div class="container">
          <div class="row">
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
                    <div class="col-md-4 mb-0 mb-md-3">
                      <input
                        v-model="sehir"
                        @keyup="getData"
                        type="text"
                        class="form-control border-0 py-md-4"
                        placeholder="City / Hotel / Location"
                        aria-label="Bölge ara"
                        style="border-bottom: 2px solid #dee2e6 !important"
                      />

                      <div
                        class="col-md-12 mb-0 mb-md-3 text-left p-3"
                        v-if="isActive"
                        style="
                          font-size: 12px !important;
                          position: absolute;
                          left: 0px;
                          background-color: white;
                        "
                      >
                        <div
                          class="font-weight-bold"
                          style="
                            border-top: 1px solid #ced4da;
                            background-color: powderblue;
                          "
                        >
                          Hotels
                        </div>
                        <option
                          @click="writeText(i.name)"
                          v-for="(i, index) in myData.hotel"
                          :key="index"
                        >
                          {{ i.name }}
                        </option>
                        <div
                          class="font-weight-bold"
                          style="
                            border-top: 1px solid #ced4da;
                            background-color: powderblue;
                          "
                        >
                          Destinations
                        </div>
                        <option
                          @click="writeText(i.name)"
                          v-for="(i, index) in myData.destination"
                          :key="index"
                        >
                          {{ i.name }}
                        </option>
                        <div
                          class="font-weight-bold"
                          style="
                            border-top: 1px solid #ced4da;
                            background-color: powderblue;
                          "
                        >
                          Category
                        </div>
                        <option
                          @click="writeText(i.name)"
                          v-for="(i, index) in myData.category"
                          :key="index"
                        >
                          {{ i.name }}
                        </option>
                      </div>
                    </div>
                    <div class="col-md-3 mb-0 mb-md-3">
                      <div class="input-group">
                        <input
                          type="text"
                          class="form-control border-0 py-md-4"
                          placeholder="Giriş / Çıkış Tarihleri"
                          style="border-bottom: 2px solid #dee2e6 !important"
                        />
                      </div>
                    </div>
                    <div class="col-md-3 mb-0 mb-md-3">
                      <div class="input-group">
                        <input
                          @click="counterShow"
                          v-model="passengers"
                          type="text"
                          class="form-control border-0 py-md-4"
                          placeholder="2 Yetiskin"
                          aria-label="2 Yetişkin"
                          style="
                            border-bottom: 2px solid #dee2e6 !important;
                            background-color: #ffffff !important;
                          "
                          readonly
                        />
                        <div
                          class="col-md-12 mb-0 mb-md-3 text-left p-3"
                          v-if="isActiveCounter"
                          style="
                            font-size: 12px !important;
                            position: absolute;
                            left: 0px;
                            top: 100%;
                            background-color: white;
                          "
                        >
                          <div
                            class="font-weight-bold my-2"
                            style="
                              border-top: 1px solid #ced4da;
                              background-color: powderblue;
                            "
                          >
                            Yetişkin Sayısı
                          </div>
                          <div class="d-flex text-center">
                            <a
                              class="btn col-md-2 bg-blue text-white"
                              @click="adultCounterFunc('remove')"
                              ><h4>-</h4></a
                            >
                            <div class="col-md-8">
                              <h5>{{ adultCounter }}</h5>
                            </div>
                            <a
                              class="btn col-md-2 bg-blue text-white"
                              @click="adultCounterFunc('add')"
                              ><h4>+</h4></a
                            >
                          </div>
                          <div
                            class="font-weight-bold my-2"
                            style="
                              border-top: 1px solid #ced4da;
                              background-color: powderblue;
                            "
                          >
                            Çocuk Sayısı
                          </div>
                          <div class="d-flex text-center">
                            <a
                              class="btn col-md-2 bg-blue text-white"
                              @click="childCounterFunc('remove')"
                              ><h4>-</h4></a
                            >
                            <div class="col-md-8">
                              <h5>{{ childCounter }}</h5>
                            </div>
                            <a
                              class="btn col-md-2 bg-blue text-white"
                              @click="childCounterFunc('add')"
                              ><h4>+</h4></a
                            >
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="col-md-2 mb-0 mb-md-3">
                      <a
                        class="btn btn-primary w-100 bg-green-gradient border-0 py-md-3"
                        >Arama Yap</a
                      >
                    </div>
                  </div>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "MainBanner",
  props: {},
  data() {
    return {
      sehir: "",
      passengers: "",
      myData: {},
      isActive: false,
      isActiveCounter: false,
      adultCounter: 2,
      childCounter: 0,
    };
  },
  methods: {
    search(a) {
      if (this.city.includes(a)) {
        this.sonuc = "basarili";
      } else {
        this.sonuc = "basarisiz";
      }
    },
    getData(e) {
      if (this.sehir.length >= 3) {
        this.isActive = true;
      } else {
        this.isActive = false;
      }
      e.preventDefault();
      console.log("start");
      axios
        .post(
          "http://10.0.8.40:2080/api/autocomplate/hotel",
          { term: this.sehir, limit: 5 },
          { headers: { "X-AUTH-TOKEN": "0dea3d3ca70e2e7c895c4d2edf0bad71" } }
        )
        .then((response) => {
          console.log(response);
          this.myData = response.data.data;
        }).catch;
      console.log("end");
    },
    writeText(text) {
      this.sehir = text;
      this.isActive = false;
    },
    counterShow() {
      if (this.isActiveCounter == true) {
        this.isActiveCounter = false;
      } else {
        this.isActiveCounter = true;
      }
      if (this.childCounter == 0) {
        this.passengers = this.adultCounter + " Yetişkin";
      } else {
        this.passengers =
          this.adultCounter + " Yetişkin, " + this.childCounter + " Çocuk ";
      }
    },
    adultCounterFunc(param) {
      if (param == "add") {
        if (this.adultCounter != 6) {
          this.adultCounter++;
        } else {
          this.adultCounter = 6;
        }
      } else {
        if (this.adultCounter != 1) {
          this.adultCounter--;
        } else {
          this.adultCounter = 1;
        }
      }
      this.passengers =
        this.adultCounter + " Yetişkin, " + this.childCounter + " Çocuk ";
    },
    childCounterFunc(param) {
      if (param == "add") {
        if (this.childCounter != 2) {
          this.childCounter++;
        } else {
          this.childCounter = 2;
        }
      } else {
        if (this.childCounter != 0) {
          this.childCounter--;
        } else {
          this.childCounter = 0;
        }
      }
      this.passengers =
        this.adultCounter + " Yetişkin, " + this.childCounter + " Çocuk ";
    },
  },
};
</script>

<style>
.MainBanner {
  background: url("@/assets/img/banner.png");
  background-size: 100% !important;
  background-repeat: no-repeat !important;
}

#searchbar {
  padding-top: 150px;
  padding-bottom: 180px;
}

.bg-green-transparent {
  background-color: var(--primary-color);
  color: white;
}

.active {
  color: var(--primary-color);
}

.btn-primary {
  background-color: var(--primary-color) !important;
}
.isactive {
  display: v-bind("showstatus");
}

.isactivecounter {
  display: v-bind("showstatus");
}
</style>
