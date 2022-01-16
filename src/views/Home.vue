<template>
  <div id="home" class="wrapper">
    <div class="static-container-content">
      <h1>Roman Purgstaller</h1>
      <h3>Software Engineer / Architect / Product Designer</h3>
      <h3>currently based in Graz, Austria</h3>
      <div class="media-icon-container">
        <a
          v-for='mediaIcon in mediaIcons'
          :key="mediaIcon.id"
          :href="mediaIcon.href"
          :title="mediaIcon.title"
          target="_blank"
        >
          <v-icon :name="mediaIcon.iconName" :href="mediaIcon.ref"/>
        </a>
      </div>
    </div>
    <div class="static-container-img">
      <img id="lander-img" src="./../assets/images/lander.jpeg">
      <div class="portfolio-title">
        <!--<a>Portfolio</a>-->
      </div>
    </div>
  </div>
</template>

<script>
import '@/styles/home.scss'

export default ({
  name: 'projects',
  data: () => {
    return {
      mediaIcons: [
        { id: 1, title: 'github', href: 'https://github.com/rpurgstaller', iconName: 'brands/github' },
        { id: 2, title: 'hackerrank', href: 'https://www.hackerrank.com/romanpurgstaller', iconName: 'brands/hackerrank' },
        { id: 3, title: 'stack-overflow', href: 'https://stackoverflow.com/users/1618893/roman-purgstaller?tab=profile', iconName: 'brands/stack-overflow' },
        { id: 4, title: 'linkedin', href: '', iconName: 'brands/linkedin' },
        { id: 5, title: 'resume', href: 'roman-purgstaller-resume.pdf', iconName: 'cv' }
      ]
    }
  }
})
</script>
