<template>
  <div class="container">
    <div class="d-flex py-5">
      <div
        class="card"
        v-for="(i, index) in post"
        :key="index"
      >
        <ul class="list-group list-group-flush text-left">
          <li class="list-group-item">user:{{ i.emailAdress }}</li>
          <li class="list-group-item">pass:{{ i.emailPassword }}</li>
        </ul>
      </div>
    </div>
    <div class="d-flex py-5">
      <form>
        <div class="form-group">
          <label for="exampleInputEmail1">Email address</label>
          <input v-model="mail"
            type="text"
            class="form-control"
            id="exampleInputEmail1"
            aria-describedby="emailHelp"
            placeholder="Enter email"
          />
          <small id="emailHelp" class="form-text text-muted"
            >We'll never share your email with anyone else.</small
          >
        </div>
        <div class="form-group">
          <label for="exampleInputPassword1">Password</label>
          <input v-model="pass"
            type="password"
            class="form-control"
            id="exampleInputPassword1"
            placeholder="Password"
          />
        </div>
        <button type="submit" @click="sendData" class="btn btn-primary">Submit</button>
        {{mail}}
    </form>
    </div>
  </div>
</template>

<script>

import axios from "axios";

export default {
  name: "BaseBlogArea",
  data() {
    return {
      post: [{emailAdress:"cagriceylan@gmail.com", emailPassword:"1234567"}],
      mail: "",
      pass: ""
    };
  },
  methods:{
    sendData(e){
        e.preventDefault();
        this.post.push({emailAdress:this.mail, emailPassword:this.pass});
        axios.post("https://vuejs-axios-blog-42ceb-default-rtdb.firebaseio.com/posts.json", this.post);
    }
  }
};
</script>

<style>
</style>