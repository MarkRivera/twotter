<template>
  <div id="app">@{{ user.username }} - {{ fullName }}</div>
  <strong>Followers: </strong> {{ followers }}
  <button @click="followUser">Follow</button>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      followers: 0,
      user: {
        id: 1,
        username: "_MarkRivera",
        fname: "Mark",
        lname: "Rivera",
        email: "Mrivera1991@gmail.com",
        isAdmin: true,
      },
    };
  },

  watch: {
    followers(newFollowerCount, oldFollowerCount) {
      oldFollowerCount < newFollowerCount &&
        console.log(`${this.user.username} has gained a follower!`);
    },
  },

  computed: {
    fullName() {
      return `${this.user.fname} ${this.user.lname}`;
    },
  },
  methods: {
    followUser() {
      this.followers++;
    },
  },

  mounted() {
    this.followUser();
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
