<template>
  <body class="home">
    <h2>Works</h2>
    <WorkList />
  </body>
</template>

<script>
import WorkList from '@/components/WorkList.vue'

export default {
  name: 'home',
  components: {
    WorkList
  }
}
</script>

<style scoped lang="scss">
h2{
  font-size: 24px;
  margin: 80px 0 40px;
  display: flex;
  justify-content: center;
  font-family: 'Raleway';
}

</style>