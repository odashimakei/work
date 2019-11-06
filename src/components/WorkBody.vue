<template>
  <section>
    <div class="wrap" v-for="(item2, index2) in data.detail" :key="index2">
      <h2 v-if="data.detail[index2].head">{{data.detail[index2].head}}</h2>
      <p v-if="data.detail[index2].description">{{data.detail[index2].description}}</p>
      <h3 v-if="data.detail[index2].subhead">{{data.detail[index2].subhead}}</h3>
      <div v-if="data.detail[index2].img">
        <img :src="data.detail[index2].img" alt="">
      </div>
      <a v-if="data.detail[index2].link_text" :href="data.detail[index2].link_url" target="_blunk">{{data.detail[index2].link_text}}</a>
      <ul v-if="data.detail[index2].lists">
        <li v-for="(item, index) in data.detail[index2].lists" :key="index">{{item}}</li>
      </ul>
    </div>
  </section>
</template>

<script>

export default {
  name: 'WorkBody',
  props: {
    data: Object
  }
}
</script>

<style scoped lang="scss">
section{
  margin: 100px 0;
}
h2{
  border-bottom: 1px solid #ddd;
  line-height: 2;
  font-size: 20px;
  margin: 40px 0 24px;
}
h3{
  border-bottom: 1px solid #eee;
  line-height: 2;
  font-size: 16px;
  margin: 40px 0 16px;
}
p{
  line-height: 1.5;
}
.wrap{
  padding: 40px;
}
img{
  display: block;
  width: 100%;
  margin: 0 auto;
}
a{
  border: 1px solid #eee;
  border-radius: 4px;
  margin: 24px auto;
  width: 300px;
  display: block;
  padding: 24px;
  text-align: center;
  transition: transform .3s cubic-bezier(.455,.03,.515,.955),box-shadow .3s ease;
  &:hover{
    box-shadow: 0 3px 10px 0 rgba(0,0,0,.1);
    transform: scale(1.01);
  }
}
ul{
  background: #fafafa;
  padding: 24px;
  line-height: 2;
}
li::before{
  content: "・"
}
</style>
