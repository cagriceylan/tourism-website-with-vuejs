<template>
  <div class="container">
    <div class="row py-5">
      <div class="col-md-4 py-3" v-for="(i, index) in postList" :key="index">
        <div class="card">
          <img class="card-img-top" :src="i.img" alt="Card image cap">
          <ul class="list-group list-group-flush text-left">
            <li class="list-group-item">user:{{ i.mail }}</li>
            <li class="list-group-item">pass:{{ i.pass}}</li>
          </ul>
        </div>
      </div>
    </div>
    <h3>Add new item</h3>
    <div class="d-flex p-5 card-shadow">
      <form>
        <div class="form-group">
          <label for="exampleInputImg">Logo Img Link</label>
          <input
            v-model="post.img"
            type="text"
            class="form-control"
            id="exampleInputImg"
            aria-describedby="emailHelp"
            placeholder="Enter Img link"
          />
        </div>
        <div class="form-group">
          <label for="exampleInputEmail1">Email address</label>
          <input
            v-model="post.mail"
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
          <input
            v-model="post.pass"
            type="password"
            class="form-control"
            id="exampleInputPassword1"
            placeholder="Password"
          />
        </div>
        <button type="submit" @click="sendData" class="btn btn-primary">
          Submit
        </button>
        <button type="submit" @click="getData" class="btn btn-primary">
          Get
        </button>
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
      postList: [],
      post: {
        img: "",
        mail: "",
        pass: ""
      },

    };
  },
  created(){

  },
  methods: {
    sendData(e) {
      e.preventDefault();
      console.log(this.post);
      axios.post( "https://vuejs-axios-blog-42ceb-default-rtdb.firebaseio.com/posts.json", this.post);
    },
    getData(w)
    {
      this.postList= [];
      console.log("start");
      w.preventDefault();
      axios.get("https://vuejs-axios-blog-42ceb-default-rtdb.firebaseio.com/posts.json")
      .then(response => {
        let data = response.data;
        for(let key in data){
          this.postList.push({...data[key], id : key});
          console.log("continue");
        }
      })
      .catch(e => console.log(e))

      console.log("end");
    }
  },
};
</script>

<style>
</style>