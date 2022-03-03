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
        <p><span v-html="project.text"></span></p>
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
      projects: [
        {
          title: 'Beanbot CLI',
          text: 'Save and modify your transactions and create a double-entry bookkeeping using beancount. It is possible to import and save your transactions from csv to a sqlite database. You can also create rules to transform attributes from your transactions and export your database to a double-entry accounting text file based on <a href="https://beancount.github.io/">beancount</a>. I\'m currently working on a text similarity measure to find similar transactions.',
          img: { src: 'beanbot.jpeg' },
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller/beanbot-personal-finance-manager', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'python' }, { title: 'sqlite3' }, { title: 'sqlAlchemy' }, { title: 'beancount' }
          ]
        },
        {
          title: 'Personal Portfolio ',
          text: 'This site was built using Vue CLI. I did my best to make the site responsive. Feel free to copy and reuse parts of this project.',
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
          text: 'Web application using Flask-RESTPlus and neo4j as a database. I did this project especially because I wanted to dive into graph databases. I really enjoyed working with cypher and looking forward for the next project with this technology.',
          img: { src: 'neo4j-flask-backend.jpeg' },
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller/Flask-RESTPlus-neo4j-backend', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'python' }, { title: 'neo4j' }, { title: 'flask' }, { title: 'py2neo' }, { title: 'rest' }
          ]
        },
        {
          title: 'Angular Login and Sign-Up',
          text: 'Angular web app for user registration using Material design. The app supports user registration, form validation and a admin user panel.',
          img: { src: 'angular-frontend.jpeg' },
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller/angular-login-and-signup', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'angular' }, { title: 'material' }, { title: 'typescript' }, { title: 'rest' }
          ]
        },
        {
          title: 'Sarcasm Detection',
          text: 'A sarcasm detector, oh, what a useful invention! For this project I used the tweepy library to access the twitter api and mine german tweets with the hashtags #sarcasm and #irony. I made this project a while after the european migrant crisis in 2015, hence I found a lot of tweets complaining about politians and journalists. Unfortunately I can hardly blame the dreadful results of this study on the European Union. Nevertheless I had a lot of fun with this project. You can read more about it in the paper on the github repo.',
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
