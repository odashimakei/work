<template>
  <body>
    <WorkHead :data="data[this.$route.params.id]" />
    <section v-if="data[this.$route.params.id].done">
      <h2>やったこと</h2>
      <ul>
        <li v-for="(item, index) in data[this.$route.params.id].done" :key="index">
          {{ item }}
        </li>
      </ul>
    </section>
    <WorkBody :data="data[this.$route.params.id]" />
  </body>
</template>

<script>
import data from '../data/data.json'
import WorkHead from '@/components/WorkHead.vue'
import WorkBody from '@/components/WorkBody.vue'

export default {
  name: 'Work',
  components: {
    WorkHead,
    WorkBody
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
section{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    max-width: 1000px;
    margin: 0 auto;
}
ul{
  background: #fafafa;
  padding: 24px;
  margin-top: 12px;
  margin: 20px 40px 0;
  width: 100%;
}
li::before{
  content: "-";
  line-height: 1.6;
}
h2{
  width: 100%;
  padding: 0 40px;
}
</style>