<template>
  <ul class="job-list">
    <li v-for="job in jobs" :key="job.id">
      <h2>{{ job.title }} in {{ job.location }}</h2>
      <div class="salary">
        <p>{{ job.salary }} rupees</p>
      </div>
      <div class="description">
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Rem omnis voluptatum eius doloremque optio iusto sequi dignissimos. Pariatur earum assumenda dolores possimus quidem quam, reprehenderit aliquid consequuntur amet non facere.</p>
      </div>
    </li>
  </ul>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Job from '@/types/Job'

export default defineComponent({
  props: {
    jobs: {
      type: Array as PropType<Job[]>,
      required: true
    }
  },
  setup(props) {
    console.log(props.jobs)
  },
})
</script>

<style scoped>
  .job-list {
    padding: 0;
    max-width: 960px;
    margin: 40px auto;
  }
  .job-list li {
    list-style-type: none;
    background: white;
    padding: 16px;
    margin: 16px 0;
    border-radius: 4px;
  }
  .job-list h2 {
    margin: 0 0 10px;
    text-transform: capitalize;
  }
  .salary {
    display: flex;
  }
  .salary img {
    width: 30px;
  }
  .salary p {
    color: #17bf66;
    font-weight: bold;
    margin: 10px 4px;
  }
</style>