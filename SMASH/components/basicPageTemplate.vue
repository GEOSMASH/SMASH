<template>
  <section
    class="container w-full mx-auto mt-16 space-y-12 overflow-hidden max-w-7xl"
  >
  <div class="w-full py-2 space-y-2 text-center">
      <h2 class="text-6xl font-bold tracking-wide md:text-7xl">
        {{ title || null}}
      </h2>
      <p v-if="subtitle" class="text-2xl font-medium">{{ subtitle }}</p>
  </div>
  
  <div
  class="max-w-6xl px-4 mx-auto mt-4 md:px-0"
  >
  
  <nuxt-content
  v-if="bodyContent"
  :document="bodyContent"
  class="mx-auto prose text-justify md:prose-2xl"
  />
  <slot></slot>
  </div>
  </section>
</template>
<script>
export default {
  name: 'BasicPageTemplate',
  props: {
    title: {
      type: String,
      required: true,
      default: '',
    },
    subtitle: {
      type: String,
      required: false,
      default: '',
    },
    bodyContent: {
      type: Object,
      required: false,
      default: () => {}
      
    }
  },
}
</script>
