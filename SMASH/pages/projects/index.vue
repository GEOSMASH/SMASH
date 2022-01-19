<template>
  <div>
    <basic-page-template
      :title="content.title"
      :body-content="content"
    >
    </basic-page-template>
  </div>
</template>

<script>
import BasicPageTemplate from '@/components/basicPageTemplate.vue'
export default {
  components: {
    BasicPageTemplate,
  },
  layout: 'header-footer',
  data() {
    return {
      content: '',
    }
  },
  async fetch() {
    const content = await this.$content('projects/index').fetch()
    this.content = content
  },
}
</script>
