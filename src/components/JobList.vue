<template>
    <li>
       
        <div class="job_info">
          <img :src="list.logo" alt="">
          <div>
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
         
        </div>

        <div class="tags">
          
            <span v-for="tag in JobTags" :key="tag.index">
              <a href=""> {{ tag }} </a>
            </span>
          
        </div>
    </li>
</template>

<script>
import { reactive, toRefs } from 'vue'

export default {
    props: {
        list: {
            type: Object
        }
    },
    setup (props) {
        const state = reactive({
            count: 0,
        })
    
        const JobTags =  [
            props.list.role,
            props.list.level,
            ...props.list.languages,
            ...props.list.tools
        ]

        return {
            ...toRefs(state),
            JobTags
        }
    }
}
</script>

<style lang="scss" scoped>
.tags span a {
    background-color: hsl(180, 52%, 96%);
    margin-left: 1rem;
    padding: 0.5rem;
    text-decoration: none;
    border-radius: 0.25rem;
    font-size: 0.8rem;
    font-weight: 700;
}
</style>