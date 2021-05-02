<template>
  <div>
    <header class="header">
      
    </header>
    <ul class="lists">
      <li v-for="list in lists" :key="list.id">
        <img :src="list.logo" alt="">
        <div class="job_info">
          
          <div class="top_info">
            <h2 class="company">{{ list.company }}</h2>
            <span v-if="list.new" class="new">new!</span>
            <span v-if="list.featured" class="featured">featured</span>
          </div>
          <div>
            <h1 class="position">{{ list.position }}</h1>
          </div>
          <div class="bottom_info">
            <span class="postedAt">{{ list.postedAt }}</span>
            <span class="contract">{{ list.contract }}</span>
            <span class="location">{{ list.location }}</span>
          </div>
        </div>
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
// # Front-end Style Guide

// ## Layout

// The designs were created to the following widths:

// - Mobile: 375px
// - Desktop: 1440px

// ## Colors

// ### Primary

// - Desaturated Dark Cyan: hsl(180, 29%, 50%)

// ### Neutral

// - Light Grayish Cyan (Background): hsl(180, 52%, 96%)
// - Light Grayish Cyan (Filter Tablets): hsl(180, 31%, 95%)
// - Dark Grayish Cyan: hsl(180, 8%, 52%)
// - Very Dark Grayish Cyan: hsl(180, 14%, 20%)

// ## Typography

// ### Body Copy

// - Font size: 15px

// ### Headings

// - Family: [Spartan](https://fonts.google.com/specimen/Spartan)
// - Weights: 500, 700
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
.lists {
  li {
    width: 70%;
    margin: 0 auto;
    background-color: #fff;
    padding: 1.5rem;
    margin-bottom: 1rem;
    border-radius: 0.5rem;
    display: flex;
  }
  img {
    padding-right: 1.5rem;
    padding-left: 1rem;
  }
}
.job_info {
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
</style>