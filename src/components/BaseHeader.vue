<template>
  <div class="BaseHeader">
    <!-- Header -->
    <div class="container-fluid">
      <nav
        class="navbar navbar-expand-lg navbar-light bg-light"
        style="background-color: white !important"
      >
        <a class="navbar-brand" href="index.html">
          <img
            src="@/assets/img/travel.png"
            class="logo-w td-logo"
            width="200px"
          />
        </a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav mr-auto">
            <li class="nav-item active dropdown mx-2">
              <a
                class="nav-link"
                href="hotel-list.html"
                id="navbarDropdownOtel"
                role="button"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false"
              >
                <h6 class="font-weight-bold">OTEL</h6>
              </a>
            </li>
            <li class="nav-item mx-2">
              <a class="nav-link" href="tour.html">
                <h6 class="font-weight-bold">TUR</h6>
                <span class="sr-only">(current)</span>
              </a>
            </li>
            <li class="nav-item dropdown mx-2">
              <a class="nav-link" href="hotel-list.html">
                <h6 class="font-weight-bold">KIBRIS</h6>
              </a>
            </li>
            <li class="nav-item dropdown mx-2">
              <a class="nav-link" href="hotel-list.html">
                <h6 class="font-weight-bold">FIRSATLAR</h6>
              </a>
            </li>
          </ul>
          <span class="navbar-text">
            <h6 class="float-left pt-2">
              Rezervasyon ve Detayl?? Bilgi ????in | <b> 444 44 44</b>
            </h6>
          </span>
          <div class="text-right">
            <form class="form-inline my-2 my-lg-0">
              <a
                class="btn btn-primary my-2 my-sm-0 rounded-0 mx-2"
                href="sign-up.html"
                type="submit"
                >??YE OL</a
              >
              <a
                class="btn btn-outline-primary my-2 my-sm-0 rounded-0"
                href="login.html"
                type="submit"
                >G??R???? YAP</a
              >
            </form>
          </div>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: "BaseHeader",
  props: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  border-bottom: 2px solid rgb(235, 211, 211);
  box-shadow: 0 0.3rem 2rem rgb(0 0 0 / 10%);
}
</style>
