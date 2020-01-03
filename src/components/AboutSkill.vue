<template>
  <section class="skill">
    <header>
      <h2>Skill</h2>
      <div class="tip">
        <i>i</i>
        <ul>
          <li class="rate-3">
            <p>人に教えられる</p>
          </li>
          <li class="rate-2">
            <p>1人でできる</p>
          </li>
          <li class="rate-1">
            <p>経験したことがある</p>
          </li>
        </ul>
      </div>
    </header>
    <section v-for="(obj, index) in skill" :key="index">
      <h3>{{obj.title}}</h3>
      <ul>
        <li v-for="(item, index2) in obj.list" :key="index2" :class="'rate-'+item.rate">
          {{item.text}}
        </li>
      </ul>
    </section>
  </section>
</template>

<script>
import skill from '../data/skill.json'

export default {
  name: 'AboutSkill',
  data: () => {
    return{
      skill: skill
    }
  }
}
</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css?family=Oswald:300,600&display=swap');

.skill{
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  max-width: 950px;
  margin: 100px auto 40px;
  align-items: baseline;
  padding: 12px;

  header{
    width: 100%;
    display: flex;
    justify-content: center;
    position: relative;
    .tip{
      position: absolute;
      right: 0;
      i{
        cursor: pointer;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 12px;
        width: 20px;
        height: 20px;
        border-radius: 50%;
        box-shadow: 0 0 6px 0 rgba(0,0,0,.3);
      }
      ul {
        display: none;
        position: absolute;
        padding-top: 10px;
        line-height: 1.6em;
        color: #fff;
        width: 190px;
        li {
          text-align: right;
          padding-left: 8px;
          width: 100px;
          z-index: 1;
          font-size: 12px;
          margin-bottom: 4px;
          p{
            margin-right: -12px;
          }
        }
        .rate-1::after{
          right: -38px;
        }
        .rate-2::after{
          right: -55px;
        }
        .rate-3::after{
          right: -72px;
        }
        &::after{
          content: "";
          display: block;
          border-radius: 5px;
          opacity: .1;
          background: #333;
          width: 190px;
          height: 96px;
          position: absolute;
          top: 1px;
        }
        &:before {
          content: "";
          position: absolute;
          top: 100%;
          left: 50%;
          border: 15px solid transparent;
          opacity: .1;
          border-top: 15px solid #333;
          margin-left: -15px;
        }
      }
      &:hover ul{
        cursor: pointer;
        display: flex;
        top: -116px;
        left: -85px;
      }
    }
  }

  h2 {
    display: flex;
    justify-content: center;
    flex-direction: column-reverse;
    align-items: center;
    font-family: 'Oswald';
    font-size: 20px;
    color: #999;
    margin-left: 20px;

    &::before{
      content: '';
      margin-top: 8px;
      display: block;
      width: 50px;
      height: 2px;
      background: #C4C4C4;
    }
  }

  section{
    margin: 40px 0;
    text-align: right;
    display: flex;
    flex-direction: column;
    flex: 1;
    padding-right: 80px;

    h3{
      font-size: 14px;
      color: #666;
      margin-bottom: 20px;
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      &::after{
        content: '';
        margin-top: 4px;
        display: block;
        width: 50px;
        height: 1px;
        background: #ccc;
      }
    }
  }

  ul {
    display: flex;
    flex-direction: column;

    li {
      margin-bottom: 12px;
      font-size: 14px;
      color: #666;
    }

    .rate-{
      &1, &2, &3{
        position: relative;
        display: inline-block;
        &::after, &::before{
          content: '★★★';
          position: absolute;
          right: -72px;
          top:0;
          color: #f5b83d;
          letter-spacing: 0.4em;
        }
        &::before{
          color: #ccc;
        }
      }
      &1::after{
        content: '★';
        right: -33px;
      }
      &2::after{
        content: '★★';
        right: -52px;
      }
    }
  }
}

</style>
