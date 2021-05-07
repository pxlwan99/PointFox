<template>
  <div id="cnnodeWrapper">
    <div>
      <span>cnnode论坛</span>
    </div>
    <div>
      <div style="display: none">
        {{ allArray[1].author.avatar_url }}
      </div>
      <div v-for="(u, index2) in this.urlArray" :key="index2">
        <span>
          <img id="avatar" :src="allArray[index2].author.avatar_url" alt="" />
        </span>
        <!-- <router-link to="/target"> -->
        <span @click="jump_a(u)" style="cursor: pointer">
          {{ allArray[index2].title }}
        </span>
        <!-- </router-link> -->
      </div>
    </div>
    <!-- <div>
      <div v-for="(value, index2) in this.Array" :key="index2">
        <span>
          <img id="avatar" :src="value.author.avatar_url" alt="" />
        </span>
        <router-link to="/target">
          <span style="cursor: pointer">
            {{ value.title }}
          </span>
        </router-link>
      </div>
    </div> -->
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      allArray: [],
      // url: "http://localhost:8080/#/target?",
      url: "https://cnodejs.org/topic/",
      urlArray: [],
    };
  },
  //生命周期函数（钩子函数）
  created() {
    let that = this;
    //console.log("this is vue");
    axios.get("https://cnodejs.org/api/v1/topics").then(function (response) {
      console.log(response.data);
      if (response.data.success) {
        that.allArray = response.data.data;
        console.log("allArray = " + that.allArray);
        // url =
        //   "http://localhost:8080/#/target?avatar_id=" +
        //   that.Array[index2].avatar_id +
        //   "&id=" +
        //   that.Array[index2].id +
        //   "&reply_count=" +
        //   that.Array[index2].reply_count;
        // console.log("url = " + url);
        for (var i = 0; i < that.allArray.length; i++) {
          //console.log("i = " + i);
          that.urlArray[i] = that.url + that.allArray[i].id;
          //console.log("urlArray = " + that.urlArray);
        }
      }
    });
  },
  methods: {
    jump_a: function (u) {
      console.log(u);
      window.location.href = u;
    },
  },
};
</script>

<style>
#avatar {
  width: 30px;
  height: 30px;
  vertical-align: middle;
}
li {
  list-style: none;
}
a {
  text-decoration: none;
  color: black;
  vertical-align: middle;
}
</style>