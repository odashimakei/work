<template>
  <header>
    <router-link to="/">
      <h1>
        Kodashim
        <span>Portfolio</span>
      </h1>
    </router-link>
    <router-link to="/about" v-if="$route.path !== '/about'">
      <p class="profile">Profile<img class="about about--link" :src="prof" alt=""></p>
    </router-link>
    <router-link v-else to="/">
      <p class="works">Works</p>
    </router-link>
  </header>
</template>

<script>

export default {
  name: 'headerWrap',
  data: () => {
    return{
      prof: "./assets/prof.jpg",
    }
  }
}
</script>

<style scoped lang="scss">
header{
  padding: 40px 20px 20px;
  height: 36px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid rgba(100, 100, 100, 0.1);
}
h1{
  font-size: 20px;
  transition: transform .3s cubic-bezier(.455,.03,.515,.955),box-shadow .3s ease;
  &:hover{
    transform: scale(1.04);
  }
}
span{
  font-weight: normal;
}
.about{
  display: block;
  width: 36px;
  border-radius: 50%;
  &--link{
    transition: transform .3s cubic-bezier(.455,.03,.515,.955),box-shadow .3s ease;
    &:hover{
      box-shadow: 0 3px 10px 0 rgba(0,0,0,.2);
      transform: scale(1.07);
    }
  }
  &--unlink{
    filter: grayscale(60%);
  }
}
.profile{
  display: flex;
  align-items: center;
  img{
    transition: transform .3s cubic-bezier(.455,.03,.515,.955),box-shadow .3s ease;
    content: "";
    margin-left: 8px;
  }
  &:hover img{
    box-shadow: 0 3px 10px 0 rgba(0,0,0,.2);
    transform: scale(1.07);
  }
}
.works{
  display: flex;
  align-items: center;
  &::after{
    transition: transform .3s cubic-bezier(.455,.03,.515,.955),box-shadow .3s ease;
    content: "";
    margin-left: 8px;
    display: block;
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background: linear-gradient(to right, #abbaab, #f0f0f0);
    transform: rotate(-135deg);
  }
  &:hover::after{
    transform: rotate(-90deg);
  }
}
</style>