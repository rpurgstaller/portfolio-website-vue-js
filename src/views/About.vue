<template>
  <div id="about" class="wrapper">
    <div class="container-img">
      <img id="about-img" src="./../assets/images/about.jpeg">
    </div>
    <div class="container-content">
      <p>Hi, my name is Roman. These days I live in Graz and work at <a href=https://www.b4b-solutions.com/>b4b-solutions</a> as a Cloud Architect advancing SAP Software.</p>
      <br>
      <p>After finishing my studies in Software Engineering / Management at Graz University of Technology, I had the opportunity to work in different fields as a software engineer and product owner.</p>
      <a>While I am fascinated with the variety of possibilities in software engineering, I especially have a strong personal interest in web development and machine learning.</a>
      <br><br>
      <p>When I'm not coding, I'm propably climbing, hiking, on a run or enjoy a game of chess. I am also a sport climbing instructor at the <a href="https://www.c-a-c.at/">city adventure center</a> in Graz.</p>
      <br>
      <p>Want to get in touch? Just send me an <a href="mailto:roman.purgstaller@protonmail.com">e-mail</a>.</p>
      <br>
      <p>You can also download my <a href="./roman-purgstaller-resume.pdf" target="_blank">resume</a>.</p>
    </div>
  </div>
</template>

<script>
import '@/styles/about.scss'

export default ({
  name: 'about',
  data: () => {
    return {}
  }
})
</script>
