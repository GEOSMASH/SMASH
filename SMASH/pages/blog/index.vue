<template>
  <div>
    <basic-page-template
      title="E[scale]ating Spatial Analysis"
    >
    <ul
        class="px-3 pb-5 space-y-6 overflow-visible md:px-0"
      >
        <li
          v-for="project in posts"
          :key="project.title"
          class="flex flex-col items-center justify-start w-full"
        >
            <horizontal-card
              class="w-3/4"
              :image="project.image"
              :link="project.path"
            >
                <div class="flex flex-col items-center justify-center w-full h-full space-y-2">
                    <p class="w-full text-xs text-left text-gray-500 md:text-base">
                        {{ new Date(project.date).toLocaleDateString() }}
                    </p>
                    <p class="text-base font-medium leading-tight text-center flex-grow-1 md:text-left lg:text-xl md:text-lg">
                        {{project.title}}
                    </p>
                    <div v-if="project.authors" class="w-full space-x-3">
                        <Pill
                            v-for="author in project.authors"
                            :key="author"
                            :text="author"
                            color="bg-gray-500"
                        />
                    </div>
                </div>
            </horizontal-card>
        </li>
      </ul>
    </basic-page-template>
  </div>
</template>

<script>
import BasicPageTemplate from '@/components/basicPageTemplate.vue'
import Pill from '@/components/Pill'
import HorizontalCard from '~/components/Cards/HorizontalCard.vue'

export default {
  components: {
    BasicPageTemplate,
    HorizontalCard,
    Pill
  },
  layout: 'header-footer',
  async asyncData({ $content }) {
    const posts = await $content('blog').fetch()
    return {
      posts,
    }
  },
}
</script>
