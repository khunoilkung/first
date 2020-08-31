<template>
  <div id="grid-images">
    <InstraCard
     v-for="(data,idx) in info"
     :info="data"
     :img="apis[idx]"
     :key="data.username+idx">
     </InstraCard>
  </div>
</template>

<script>
import axios from "axios";
import InstraCard from "@/components/InstraCard";

export default {
  name: "GridImages",
  data: function () {
    return {
      avatarImg:
        "https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4",
      usernames: [
        "AdaBrain",
        "Peter Parker",
        "Steve Jobs",
        "Bill Gates",
        "Elon Musk",
      ],
      apis: null,
      fakeApi: null,
      info: [
        {
          username: "ada",
          avatarImg:
            "https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4",
          image:
            "https://github.com/jigsawpieces/dog-api-images/blob/master/beagle/n02088364_12154.jpg?raw=true",
          numOfLikes: 92,
          numOfcomment: 108,
        },
        {
          username: "abc",
          avatarImg:
            "https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4",
          image:
            "https://github.com/jigsawpieces/dog-api-images/blob/master/beagle/n02088364_13464.jpg?raw=true",
          numOfLikes: 92,
          numOfcomment: 108,
        },
        {
          username: "abc",
          avatarImg:
            "https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4",
          image:
            "https://github.com/jigsawpieces/dog-api-images/blob/master/beagle/n02088364_13464.jpg?raw=true",
          numOfLikes: 92,
          numOfcomment: 108,
        },
        {
          username: "abc",
          avatarImg:
            "https://avatars0.githubusercontent.com/u/3336816?s=460&u=a3def04c56afd7220d835005dbf1879a0b497554&v=4",
          image:
            "https://github.com/jigsawpieces/dog-api-images/blob/master/beagle/n02088364_13464.jpg?raw=true",
          numOfLikes: 92,
          numOfcomment: 108,
        },
      ],
    };
  },
  mounted: function () {
    axios
      .get("https://dog.ceo/api/breed/pomeranian/images/random/10")
      .then((response) => (this.apis = response.data.message));

    axios
      .get("https://api.mocki.io/v1/9caa0ba8")
      .then((response) => (this.fakeApi = response));
  },
  components: {
    InstraCard,
  },
};
</script>

<style>
#grid-images {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
}
</style>
