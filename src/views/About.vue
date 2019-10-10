<template>
  <body class="about">
    <section>
      <img :src="prof" alt="">
      <h2>
        Odashima Kei
        <span>小田島 慧</span>
      </h2>
      <p>大学で情報デザインを専攻、卒業後はヤフー株式会社のデザイナーとして2017年に入社。新規事業のサービスデザインに携わる。現在はスポーツナビのアプリやウェブのデザインとコーディングを担当。副業では新規サービスのUIデサインとコーディングを担当。</p>
    </section>

    <section class="skill">
      <section>
        <h3>Design</h3>
        <ul>
          <li>Information Design</li>
          <li>Visual Design</li>
          <li>Motion Design</li>
        </ul>
      </section>

      <section>
        <h3>Cording</h3>
        <ul>
          <li>HTML</li>
          <li>CSS</li>
          <li>JavaScrip</li>
        </ul>
      </section>
    </section>

  </body>
</template>

<script>

export default {
  name: 'about',
  data: () => {
    return{
      prof: "./assets/prof.jpg",
    }
  }
}
</script>

<style scoped lang="scss">
img{
  display: block;
  margin: 0 auto;
  width: 150px;
  border-radius: 50%;
  margin-top: 80px;
}
h2{
  font-size: 36px;
  text-align: center;
  display: flex;
  flex-direction: column;
  margin-top: 16px;
}
span{
  font-size: 20px;
  margin-top: 16px;
}
p{
  max-width: 700px;
  margin: 0 auto;
  margin-top: 46px;
  line-height: 1.5;
}
.skill{
  display: flex;
  justify-content: center;
  margin: 60px 0;
  section{
    margin: 0 100px;
  }
}
ul{
  margin: 24px 0;
}
li{
  margin: 12px 0;
}
</style>