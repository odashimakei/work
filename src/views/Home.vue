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
  margin: 80px auto 40px;
  padding: 0 10px;
  max-width: 760px;
  display: flex;
  justify-content: flex-start;
  font-family: 'Raleway';
}

</style>