<template>
  <div class="card-wrapper">
    <h1 class="app-header">GitHub Profiles</h1>
    <div class="positioning-cards">
      <GithubProfileCard
        v-for="username in usernames"
        :username="username"
        :key="username"
      ></GithubProfileCard>
    </div>
  </div>
</template>

<script>
import GithubProfileCard from "@/components/GithubProfileCard.vue";

export default {
  name: "App",
  components: {
    GithubProfileCard,
  },
  data() {
    return {
      usernames: ["danielkellyio", "hootlex", "rahaug", "akryum"],
    };
  },
};
</script>

<style>
.card-wrapper {
  background-color: lightgoldenrodyellow;
  width: 800px;
  height: 1000px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 5rem;
}

.app-header {
  text-align: center;
  padding: 1rem 0;
}

.positioning-cards {
  display: grid;
  grid-template-columns: 300px 300px;
  grid-template-rows: auto;
  justify-content: center;
  align-items: center;
  gap: 10px;
}
</style>
