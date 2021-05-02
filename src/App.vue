<template>
  <div>
    <header class="header">
      
    </header>
    <ul>
      <li v-for="list in lists" :key="list.id">
        <section class="job_info">
          <img :src="list.logo" alt="">
          <header>
            <h2 class="company">{{ list.company }}</h2>
            <span class="new"></span>
            <span class="featured"></span>
          </header>
          <main>
            <h1 class="position"></h1>
          </main>
          <footer>
            <span class="postedAt"></span>
            <span class="contract"></span>
            <span class="location"></span>
          </footer>
        </section>
      </li>
    </ul>
  </div>
</template>

<script>
import { ref } from 'vue'
import { data } from '@/data.js'

export default {
  setup () {
    const lists = ref(data)
  
    return {
      lists
    }
  }
}
</script>

<style lang="scss">
body {
  width: 100%;
  height: auto;
  margin: 0;
}
.header {
  width: 100%;
  height: 155px;
  background-image: url('../public/images/bg-header-desktop.svg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
</style>