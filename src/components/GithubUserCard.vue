<template>
  <div>
    <div>
      <h1 class="heading">GitHub Profiles</h1>
    </div>
    <div>
       <input
        type="text"
        class="text-center"
        @keyup.enter="fetchUser"
        :value="modelValue" 
        @input="$emit('update:modelValue', $event.target.value)"
        placeholder="Search for a User"
        v-bind="$attrs"
      >
    </div>
    <article v-show="this.modelValue.length !== 0">
      <div class="gitImage">
        <img :src="user.avatar_url" alt="github avatar">
      </div>
      <div>
        <a :href="`https://github.com/${user.login}`" class="header">{{user.login}}</a>
        <div class="meta">
          <span>{{user.created_at}}</span>
        </div>
        <div>
          {{user.bio}}
        </div>
      </div>
      <div class="extra content">
        <a :href="`https://github.com/${user.login}?tab=followers`">
          <i class="user icon"></i>
          {{user.followers}} Friends
        </a>
      </div>
  </article>
  </div>
</template>

<script>
  export default {
    props: {
      modelValue: {}
    },
    data() {
      return {
        user: {}
      }
    },
    methods: {
      async fetchUser() {
        const response = await fetch(`https://api.github.com/users/${this.modelValue}`)
        const user = await response.json()
        this.user = user
      }
    }
  }
</script>

<style scoped>
  .heading{
    color: #525FE1;
  }
  
  .text-center {
    text-align: center;
  }
  
  article {
    padding-top: 2em;
  }

  img {
    margin-bottom: .5em;
    box-shadow: .5em .5em 1em #333;
    border-radius: 20px;
  }
</style>
