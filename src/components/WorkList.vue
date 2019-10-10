<template>
  <section>
    <button @click="toggle()">ALL</button>
    <button @click="toggle(data[0].type)">{{data[0].type}}</button>
    <button @click="toggle(data[9].type)">{{data[9].type}}</button>

    <ol class="work">
      <li class="work__item" v-for="(item, index) in data" :key="index">
        <router-link class="work__link" :to="'/work/'+item.id" v-if="item.type === tag">
          <img class="work__thumb" :src="data[item.id].hero" alt="">
          <div class="work__detail">
            <span class="work__title">
              {{data[item.id].title}}
            </span>
            <span class="work__date">
              {{data[item.id].date}}
            </span>
            <span :class="[
              data[item.id].tag === 'ui' ?
              'work__grade work__grade--ui' : 'work__grade work__grade--sub'
            ]"></span>
          </div>
        </router-link>
      </li>
    </ol>
  </section>

</template>

<script>
import data from '../data/data.json'

export default {
  name: 'WorkList',
  props: {
    num: Number
  },
  data: () => {
    return{
      data: data,
      flag: true,
      tag: 2019
    }
  },
  methods: {
    toggle(val) {
      this.tag = val;
    }
  }
}


</script>

<style scoped lang="scss">
@mixin shadow{
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  margin: auto;
  content: "";
  display: block;
  height: 100%;
  z-index: -10;
  border-radius: 4px;
}

.work{
  padding: 0 10px;
  display: flex;
  flex-direction: column;
  &__link{
    position: relative;
    margin: 20px auto;
    z-index: 10;
    display: flex;
    flex-direction: column;
    max-width: 360px;
    border-radius: 4px;
    border:1px solid #fcfcfc;
    background: #fff;
    transition: transform .3s cubic-bezier(.455,.03,.515,.955),
    box-shadow .1s ease;
    &:after{
      @include shadow;
      width: 100%;
      box-shadow: 0 1px 5px 0 rgba(0,0,0,.1);
      transition: .3s cubic-bezier(.455,.03,.515,.955);
    }
    &:hover{
      transform: scale(1.01);
      &:after{
      @include shadow;
      width: 90%;
      box-shadow: 0 3px 10px 3px rgba(0,0,0,.1);
    }
    }
  }
  &__detail{
    display: flex;
    flex-direction: column;
    background: #fff;
    padding: 20px;
    border-radius: 4px;
  }
  &__thumb{
    object-fit: cover;
    background: #fff;
    max-width: 360px;
    height: 260px;
    position: relative;
    top: 0;
    left: 0;
  }
  &__title{
    font-size: 14px;
    font-weight: bold;
    margin-bottom: 10px;
  }
  &__date{
    font-size: 12px;
    color: #999;
    margin-bottom: 20px;
  }
  &__grade{
    font-size: 12px;
    padding: 3px 10px 2px;
    width: fit-content;
    border-radius: 14px;
    &--ui{
      color: #fff;
      background: #96C8DC;
      &::before{
        content: "UI"
      }
    }
    &--sub{
      color: #aaa;
      border: 1px solid #aaa;
      &::before{
        content: "Sub"
      }
    }
  }
}
</style>
