<template>
  <section>
    <div class="hero">
      <img :src="data.hero" alt="">
    </div>
    <div class="overview">
      <div class="overview__wrap">
        <h1>{{data.title}}</h1>
        <p>{{data.description}}</p>
      </div>
      <aside class="overview__aside">
        <dl>
          <dt>役割</dt>
          <dd>{{data.role}}</dd>
        </dl>
        <dl>
          <dt>期間</dt>
          <dd>{{data.date}}</dd>
        </dl>
      </aside>
    </div>
  </section>
</template>

<script>

export default {
  name: 'WorkHead',
  props: {
    data: Object
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
.hero{
  overflow: hidden;
  max-width: 1000px;
}
img{
  width: 100%;
}
h1{
  font-size: 24px;
  margin-bottom: 24px;
}
dl{
  margin-bottom: 24px;
}
dt{
  font-size: 12px;
  font-weight: bold;
  margin-bottom: 6px;
}
.overview{
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 40px;
  margin-bottom: 40px;
  flex-wrap: wrap;
  width: 100%;
  &__wrap{
    margin: 24px 0;
    display: flex;
    flex-direction: column;
    max-width: 700px;
    line-height: 1.6;
  }
  &__aside{
    font-size: 14px;
    max-width: 130px;
  }
}
</style>
