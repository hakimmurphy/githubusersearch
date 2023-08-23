<template>
  <div>
    <form @submit.prevent="onSubmit">
      <GithubUserCard v-model="newUser"></GithubUserCard>
      <Footer></Footer>
    </form>
  </div>
</template>

<script>
  import GithubUserCard from './components/GithubUserCard.vue'
  import Footer from './components/Footer.vue'
  export default {
    components: {GithubUserCard, Footer},
    data() {
        return {
        newUser: '',
      }
    },
    methods: {
      onSubmit(e) {
        e.preventDefault()
      }
    }
  }
</script>

<style scoped>

</style>
