<template>
  <div id="app" class="ui container">
    <div class="ui card">
      <div class="image">
        <img :src="user.avatar_url" />
      </div>
      <div class="content">
        <a class="header"> {{ user.name }}</a>
        <div class="meta">
          <span class="date"> {{ user.created_at }}</span>
        </div>
        <div class="description">
          {{ user.bio || "This User has no Bio" }}
        </div>
      </div>
      <div class="extra content">
        <a>
          <i class="user icon"></i>
          {{ user.followers }} Friends
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "GithubProfileCard",
  props: {
    username: String,
  },
  data() {
    return {
      user: [],
    };
  },
  mounted() {
    fetch(`https://api.github.com/users/${this.username}`)
      .then((res) => res.json())
      .then((data) => (this.user = data));
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
