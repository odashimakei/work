<template>
  <main>
    <div class="profile">
      <img :src="prof" alt="">
      <h1>
        <p>小田島<span>慧</span></p>
        <p>Odashima<span>Kei</span></p>
      </h1>
      <p>3年目の社会人デザイナー。ストレングスファインダーの最上位資質は学習欲。業務はデザインから開発まで担当。最近はデザインシステムを作ることが多い。目標はデザインを軸に経営から開発までを推進できるようになること。写真の飲み物は麦茶。あだ名はおだし。</p>
    </div>

    <section class="career">
      <h2>Career</h2>
      <ol>
        <li>
          <p>ヤフーに新卒デザイナーとして入社。新規事業のサービスのデザインと開発を担当。</p>
        </li>
        <li>
          <p>10月にスポーツナビへ出向し、Webとアプリのデザインと開発を担当。<br>副業で、複数の新規事業の立ち上げのデザインと開発を担当。現在も継続中。</p>
        </li>
        <li>
          <p>サービスのリデザインPJでデザインと開発を担当。<br>副業で、デザイン未経験者をWebデザイナーとして鍛え、デザイン会社の内定を頂く。</p>
        </li>
        <li>
          <p>ヤフー全社の東京オリンピック特集のデザインと開発を担当中。</p>
        </li>
      </ol>
    </section>

    <AboutSkill />

  </main>
</template>

<script>
import AboutSkill from '@/components/AboutSkill.vue'

export default {
  name: 'about',
  components: {
    AboutSkill
  },
  data: () => {
    return{
      prof: "./assets/prof.jpg",
    }
  }
}
</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css?family=Oswald:300,600&display=swap');

.profile{
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 900px;
  margin: 100px auto 40px;
  position: relative;
  flex-wrap: wrap;
  padding: 12px;

  img{
    display: block;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    position: relative;
    z-index: 1;
    margin-left: 8px;
  }

  &::after{
    z-index: 0;
    position: absolute;
    content: "";
    left: 12px;
    top: 4px;
    display: block;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background: #EEE;
  }

  h1{
    display: flex;
    flex-direction:column-reverse;
    justify-content: space-between;
    font-weight: bold;
    height: 80px;
    margin-right: auto;
    margin-left: 20px;

    p{
      display: flex;
      justify-content: space-between;
      text-align: justify;
      &:first-child{
        color: #666;
        font-size: 24px;
        letter-spacing: 0.3em;
        font-family: 'Hiragino Kaku Gothic ProN';
      }
      &:last-child{
        color: #999;
        font-family: 'Oswald', sans-serif;
        font-size: 12px;
        letter-spacing: 0.5em;
        text-transform: uppercase;
      }
      span{
        font-weight: 100;
        margin-left: 8px;
      }
    }
    &:before{
      margin-top: 8px;
      display: block;
      content: "";
      width: 50px;
      height: 4px;
      background: #999;
    }
  }

  p{
    max-width: 590px;
    font-size: 14px;
    line-height: 26px;
    text-align: justify;
    margin-top: 12px;
  }
}

.career{
  display: flex;
  flex-direction: column;
  max-width: 950px;
  margin: 100px auto 40px;
  padding: 12px;

  h2 {
    display: flex;
    justify-content: center;
    flex-direction: column-reverse;
    align-items: center;
    font-family: 'Oswald';
    font-size: 20px;
    color: #999;
    &::before{
      content: '';
      margin-top: 8px;
      display: block;
      width: 50px;
      height: 2px;
      background: #C4C4C4;
    }
  }

  ol {
    max-width: 950px;
    margin: 40px auto;
    counter-reset: count 2016;
    li {
      display: flex;
      margin-bottom: 20px;
      &::before{
        counter-increment: count;
        content:counter(count);
        margin-top: 6px;
        font-weight: bold;
        font-size: 12px;
        color: #999;
      }
      p {
        margin-left: 20px;
        display: flex;
        font-size: 14px;
        line-height: 26px;
        &::before{
          content: '';
          margin-right: 20px;
          display: block;
          margin-top: 10px;
          width: 12px;
          height: 2px;
          background: #C4C4C4;
        }
      }
    }
  }
}

</style>