<template>
  <!-- LİST AREA-->
  <div class="col-md-12 pl-md-4">
    <div class="row py-3 py-md-1">
      <div class="container px-0 text-center text-md-left">
        
        <P
          >Showing <b>{{ hotelArray.length }}</b> HOTEL for Antalya City</P
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
              v-for="(item, index) in hotelArray.slice(0, 5)"
              :key="index"
            >
              <div class="row border">
                <div class="col-md-3 px-0">
                  <img class="w-100 h-100" :src="item.Photo" />
                  <i class="fa fa-heart fa-6"></i>
                </div>
                <div class="col-md-6">
                  <div class="row p-1">
                    <div class="col-5 px-0">
                      <small>{{ item.City }}/{{ item.Country }}</small>
                    </div>
                    <div class="col-5 px-0">
                      <a href="" class="color-green"
                        ><small>Haritada Göster</small></a
                      >
                    </div>
                    <div
                      class="col-2 bg-green-soft color-blue px-0 text-center"
                    >
                      <small class="font-weight-bold">{{item.Stars}} Star</small>
                    </div>
                  </div>
                  <div class="row p-1">
                    <div class="col-md-12 pt-1 line-height-tiny" style="text-align: left;">
                        <h5 class="font-weight-bold">
                          {{ item.Name }}
                        </h5>
                        <p class="color-grey">.</p>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col-md-12 p-1 hide-mobile">
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
                      <h4 class="font-weight-bold">{{ item.Price }} TL</h4>
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
  </div>

</template>
<script>
    
    export default {
    
      methods:{
        example2(value){
            console.log(value);
            this.firstIndex = value
        },
        example3(value){
            console.log(value);
            this.lastIndex = value
        }
      },
      data() {
        return {
          hotelArray: [
    {
        Name: "The Peninsula",
        Amenities: "pool, jacuzzi",
        Stars: "4",
        City: "Paris",
        Country: "France",
        Photo: "https://assets.hotelaparis.com/uploads/pictures/000/028/007/rect690_room.jpg",
        Price: "400",
        WebSite: "https://www.peninsula.com/"
    },
    {
        Name: "Regent Berlin",
        Amenities: "wifi, pets",
        Stars: "5",
        City: "Berlin",
        Country: "Germany",
        Photo: "https://www.telegraph.co.uk/content/dam/Travel/hotels/europe/germany/berlin/hotel-de-rome-berlin-germany-2-p-xlarge.jpg",
        Price: "900",
        WebSite: "https://www.ihg.com/"
    },
    {
        Name: "Brown's Hotel",
        Amenities: "wifi",
        Stars: "5",
        City: "London",
        Country: "UK",
        Photo: "https://www.telegraph.co.uk/content/dam/Travel/hotels/europe/united-kingdom/Hotels%20-%20England/london/the-ritz-london-p-large.jpg",
        Price: "800"
    },
    {
        Name: "Grand Hotel Du Palais Royal",
        Amenities: "wifi",
        Stars: "5",
        City: "Paris",
        Country: "France",
        Photo: "https://media.timeout.com/images/103729245/1372/772/image.jpg",
        Price: "850",
        WebSite: "https://www.roccofortehotels.com/hotels-and-resorts/browns-hotel/"
    },
    {
        Name: "The Savoy",
        Amenities: "wifi",
        Stars: "5",
        City: "London",
        Country: "UK",
        Photo: "https://www.telegraph.co.uk/content/dam/Travel/hotels/europe/united-kingdom/Hotels%20-%20England/london/the-dorchester-p-large.jpg",
        Price: "1050",
        WebSite: "https://www.fairmont.com/savoy-london/"
    },
    {
        Name: "George V",
        Amenities: "pool, jacuzzi, wifi",
        Stars: "5",
        City: "Paris",
        Country: "France",
        Photo: "https://assets.hotelaparis.com/uploads/pictures/000/011/834/rect690_1_chambre_hotel_george_v-2.jpg",
        Price: "1000",
        WebSite: "https://www.fourseasons.com/paris/"
    },
    {
        Name: "The Ritz London",
        Amenities: "pool, wifi",
        Stars: "5",
        City: "London",
        Country: "UK",
        Photo: "https://www.telegraph.co.uk/content/dam/Travel/hotels/europe/united-kingdom/Hotels%20-%20England/london/the-langham-london-room-p-xlarge.jpg",
        Price: "850",
        WebSite: "https://www.theritzlondon.com/"
    },
    {
        Name: "Le Royal Monceau",
        Amenities: "wifi",
        Stars: "5",
        City: "Paris",
        Country: "France",
        Photo: "https://media.timeout.com/images/103698374/1372/772/image.jpg",
        Price: "900",
        WebSite: "https://www.raffles.com/paris/"
    },
    {
        Name: "Grand Hyatt",
        Amenities: "pets",
        Stars: "2",
        City: "Berlin",
        Country: "Germany",
        Photo: "https://www.telegraph.co.uk/content/dam/Travel/hotels/europe/germany/berlin/waldorf-astoria-berlin-p-large.jpg",
        Price: "156",
        WebSite: "https://www.hyatt.com/en-US/hotel/germany/grand-hyatt-berlin/bergh?src=corp_lclb_gmb_seo_eame_bergh"
    },
    {
        Name: "The Langham",
        Amenities: "jacuzzi, wifi",
        Stars: "2",
        City: "London",
        Country: "UK",
        Photo: "https://www.telegraph.co.uk/content/dam/Travel/hotels/europe/united-kingdom/Hotels%20-%20England/london/the-connaught-p-large.jpg",
        Price: "170",
        WebSite: "http://www.langhamhotels.com/en/the-langham/london"
    },
    {
        Name: "The Ritz-Carlton",
        Amenities: "pets",
        Stars: "5",
        City: "Berlin",
        Country: "Germany",
        Photo: "https://www.telegraph.co.uk/content/dam/Travel/hotels/europe/germany/berlin/ritz-carlton-berlin-p-large.jpg",
        Price: "900",
        WebSite: "http://www.ritzparis.com/en-GB/luxury-hotel-paris"
    },
    {
        Name: "Ritz Paris",
        Amenities: "pool, wifi",
        Stars: "4",
        City: "Paris",
        Country: "France",
        Photo: "https://assets.hotelaparis.com/uploads/pictures/000/037/294/rect690_ritz-paris-hotel-suite-coco-chanel.jpg",
        Price: "600",
        WebSite: "http://www.ritzparis.com/en-GB"
    },
    {
        Name: "Hotel de Rome",
        Amenities: "pool, jacuzzi",
        Stars: "5",
        City: "Berlin",
        Country: "Germany",
        Photo: "https://www.telegraph.co.uk/content/dam/Travel/hotels/europe/germany/berlin/hotel-zoo-berlin-p-large.jpg",
        Price: "800",
        WebSite: "https://www.roccofortehotels.com/hotels-and-resorts/hotel-de-rome/"
    }
],
          firstIndex : 0,
          lastIndex : 5,
        };
      },
    };
    </script>
<style>

</style>