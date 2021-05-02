<template>
  <div>
    <header class="header">
      
    </header>
    <ul class="lists">
        <JobList v-for="list in lists" :key="list.id" :list="list" />
    </ul>
  </div>
</template>

<script>
import { ref } from 'vue'
import { data } from '@/data.js'
import JobList from '@/components/JobList.vue'

export default {
  components: {
    JobList
  },
  setup () {
    const lists = ref(data)

    
    
    return {
      lists,
      
    }
  }
}
</script>

<style lang="scss">

body {
  width: 100%;
  height: auto;
  margin: 0;
  font-size: 15px;
  background-color: hsl(180, 52%, 96%);
  font-family: 'Spartan', sans-serif;
}
ul li {
  list-style: none;
}
.header {
  width: 100%;
  height: 155px;
  background-image: url('../public/images/bg-header-desktop.svg');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  background-color: hsl(180, 29%, 50%);
}
.tags span a {
    background-color: hsl(180, 52%, 96%);
    margin-left: 1rem;
    padding: 0.5rem;
    text-decoration: none;
    border-radius: 0.25rem;
    font-size: 0.8rem;
    font-weight: 400;
    color: hsl(180, 29%, 50%);
}
.tags span:hover a {
  background-color: hsl(180, 29%, 50%);
  color: hsl(180, 52%, 96%);
}
.lists {
  li {
    width: 70%;
    margin: 0 auto;
    background-color: #fff;
    padding: 1.5rem;
    margin-bottom: 1rem;
    border-radius: 0.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    --tw-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
    
  }
  img {
    padding-right: 1.5rem;
    padding-left: 1rem;
  }
}
.job_info {
  display: flex;
  h1 {
    font-size: 1.2rem;
    font-weight: 700;
  }
  h2 {
    font-size: 0.9rem;
    margin: 0;
    color: hsl(180, 29%, 50%);
    padding-right: 0.5rem;
  }
}
.top_info {
  display: flex;
  align-items: center;
}
.new {
  font-size: 0.7rem;
  color: #fff;
  text-transform: uppercase;
  background-color: hsl(180, 29%, 50%);
  padding-top: 0.4rem;
  padding-bottom: 0.2rem;
  padding-left: 0.5rem;
  padding-right: 0.5rem;
  border-radius: 1rem;
}
.featured {
  font-size: 0.7rem;
  color: #fff;
  text-transform: uppercase;
  background-color: #000;
  padding-top: 0.4rem;
  padding-bottom: 0.2rem;
  padding-left: 0.5rem;
  padding-right: 0.5rem;
  border-radius: 1rem;
  margin-left: 0.5rem;
}
.postedAt:after, .contract:after {
  content: "";
    width: 3px;
    height: 3px;
    border-radius: 3px;
    background-color: hsl(180, 8%, 52%);
    display: inline-block;
    margin: 5px 15px;
}
.bottom_info {
  color: hsl(180, 8%, 52%);
}
.tags {
  display: flex;
  ul {
    display: flex;
  }
}
</style>