<template>
  <div>
    <div
      class="project-container"
      v-for="(project, idx) in projects"
      :key="idx"
    >
      <div class="tag-list">
        <div v-for="(tag, tag_idx) in project.tags" :key="tag_idx">
          {{tag.title}}
        </div>
      </div>
      <h3>{{project.title}}</h3>
      <a>{{project.text}}</a>
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
      <hr>
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
          title: 'Personal Portfolio ',
          text: 'This site was built using Vue CLI.',
          link: 'sarcasm-detector',
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'vue-cli' }, { title: 'web-development' }
          ]
        },
        {
          title: 'Sarcasm Detection',
          text: 'A sarcasm detector, oh, what a useful invention! I made this in university and while the results were disillusioning, it was a lot of fun implementing.',
          link: 'sarcasm-detector',
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'python' }, { title: 'scikit-learn' }
          ]
        },
        {
          title: 'Beanbot CLI',
          text: 'Save and modify your transactions and create a double-entry bookkeeping using beancount.',
          link: 'sarcasm-detector',
          mediaIcons: [
            { id: 1, title: 'github', href: 'https://github.com/rpurgstaller', iconName: 'brands/github' }
          ],
          tags: [
            { title: 'python' }, { title: 'sqlite3' }, { title: 'sqlAlchemy' }
          ]
        }
      ]
    }
  },
  methods: {
    getLink: function (projectLink) {
      return '/projects/' + projectLink
    }
  }

})
</script>

<style>
.vs-col{
  padding:1rem;
}
.cards{
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  gap: 4rem;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}
</style>
