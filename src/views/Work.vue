<template>
  <body>
    <WorkHead :data="data[this.$route.params.id]" />
    <h2>やったこと</h2>
    <ul>
      <li v-for="(item, index) in data[this.$route.params.id].done" :key="index">
        {{ item }}
      </li>
    </ul>
    <WorkBody :data="data[this.$route.params.id]" />
    <!-- <Related /> -->
  </body>
</template>

<script>
import data from '../data/data.json'
import WorkHead from '@/components/WorkHead.vue'
import WorkBody from '@/components/WorkBody.vue'
// import Related from '@/components/Related.vue'

export default {
  name: 'Work',
  components: {
    WorkHead,
    WorkBody
    // Related
  },
  props: {
    id: Number
  },
  data: () => {
    return{
      data: data
    }
  }
}
</script>

<style scoped lang="scss">
ul{
  background: #fafafa;
  padding: 24px;
  margin-top: 12px;
}
li::before{
  content: "-";
  line-height: 1.6;
}
</style>