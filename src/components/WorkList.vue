<template>
  <section>
    <div class="year">
      <button :class="{current: tag === 'all'}" @click="toggle('all')">ALL</button>
      <button :class="{current: tag === 2020}" @click="toggle(2020)">2020</button>
      <button :class="{current: tag === 2019}" @click="toggle(2019)">2019</button>
      <button :class="{current: tag === 2018}" @click="toggle(2018)">2018</button>
    </div>
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
              data[item.id].tag === 'main' ?
              'work__grade work__grade--ui' : 'work__grade work__grade--sub'
            ]"></span>
          </div>
        </router-link>
        <router-link class="work__link" :to="'/work/'+item.id" v-else-if="tag === 'all'">
          <img class="work__thumb" :src="data[item.id].hero" alt="">
          <div class="work__detail">
            <span class="work__title">
              {{data[item.id].title}}
            </span>
            <span class="work__date">
              {{data[item.id].date}}
            </span>
            <span :class="[
              data[item.id].tag === 'main' ?
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
      tag: 'all'
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
.year{
  display: flex;
  justify-content: center;
}
button{
	background: none;
	border: none;
	outline: none;
	appearance: none;
  cursor: pointer;
  text-align: center;
  color: #999;
  font-weight: bold;
  padding: 10px 20px;
  margin: 0 10px;
  position: relative;
  display: inline-block;
  transition: 0.5s;
  &::after {
    position: absolute;
    bottom: 0;
    left: 0;
    content: '';
    width: 0;
    border-bottom: solid 1px #999;
    transition: 0.5s;
  }
  &:hover::after {
    width: 100%;
  }
}

.current{
  border-bottom: solid 1px #414F57;
  &:after{
    display: none;
  }
}

.work{
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  max-width: 1280px;
  margin: 0 auto;
  &__link{
    position: relative;
    margin: 20px 8px;
    z-index: 10;
    display: flex;
    flex-direction: column;
    max-width: 300px;
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
    max-width: 300px;
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
        content: "Main"
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
