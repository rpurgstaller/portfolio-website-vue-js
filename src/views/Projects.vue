<template>
  <div class="wrapper">
    <div
      class="project-container"
      v-for="(project, idx) in projects"
      :key="idx"
    >
      <div class="project-img-container">
        <img class="project-img" v-bind:src="getImage(project.img.src)">
      </div>
      <div class="project-content">
        <div class="tag-list roboto-font">
          <div v-for="(tag, tag_idx) in project.tags" :key="tag_idx">
            {{tag.title}}
          </div>
        </div>
        <h3>{{project.title}}</h3>
        <a>{{project.text}}</a>
      </div>
      <div class="projects-media-icon-container">
        <a
          v-for='mediaIcon in project.mediaIcons'
          :key="mediaIcon.id"
          :href="mediaIcon.href"
          :title="mediaIcon.title"
          target="_blank"
        >
          <v-icon :name="mediaIcon.iconName" :href="mediaIcon.ref"/>
        </a>
      </div>
      <hr class="project-separator" v-if="idx !== projects.length-1">
    </div>
  </div>
</template>

<script>
import '@/styles/projects.scss'

export default ({
  name: 'projects',
  data: () => {
    return {
      imgPath: './../assets/images/',
      projects: [
        {
          title: 'Beanbot CLI',
          text: 'Save and modify your transactions and create a double-entry bookkeeping using beancount.',
          img: { src: 'sarcasm-f1-accuracy.jpeg' },
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller/beanbot-personal-finance-manager', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'python' }, { title: 'sqlite3' }, { title: 'sqlAlchemy' }, { title: 'beancount' }
          ]
        },
        {
          title: 'Personal Portfolio ',
          text: 'This site was built using Vue CLI.',
          img: { src: 'lander.jpeg' },
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller/portfolio-website', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'vue-cli' }, { title: 'scss' }
          ]
        },
        {
          title: 'Flask-RESTPlus Web Service',
          text: 'Web application using Flask-RESTPlus and neo4j as a database. py2neo is used as OGM. Currently, CRUD operations for users are supported.',
          img: { src: 'neo4j-flask-backend.jpeg' },
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller/Flask-RESTPlus-neo4j-backend', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'python' }, { title: 'neo4j' }, { title: 'flask' }, { title: 'py2neo' }
          ]
        },
        {
          title: 'Angular Login and Sign-Up',
          text: 'Angular web app for user registration using Material design.',
          img: { src: 'angular-frontend.jpeg' },
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller/angular-login-and-signup', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'angular' }, { title: 'material' }
          ]
        },
        {
          title: 'Sarcasm Detection',
          text: 'A sarcasm detector, oh, what a useful invention! For this project I used the tweepy library to access the twitter api and mine german tweets with the hashtags #sarcasm and #irony. I made this project a while after the european migrant crisis in 2015, hence I found a lot of tweets complaining about politians and journalists. The results were quite disillusioning, but it was a lot of fun implementing. You can read more about it in the paper on the github repo.',
          img: { src: 'sarcasm-f1-accuracy.jpeg' },
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller/sarcasm-detector', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'python' }, { title: 'scikit-learn' }, { title: 'nltk' }
          ]
        }
      ]
    }
  },
  methods: {
    getImage: function (filename) {
      return require('./../assets/images/' + filename)
    }
  }
})
</script>
