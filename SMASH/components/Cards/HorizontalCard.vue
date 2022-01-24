<template>
    <div class="flex items-center max-w-6xl p-3 overflow-hidden rounded shadow-md min-w-20 justify-evenly">
        <div class="flex items-center justify-center w-1/2">
            <Icon
                :icon="icon"
                class="w-10 h-10 text-gray-400 md:w-20 md:h-20"
                aria-hidden="true"
            />
        </div>

        <p class="w-1/2 text-base font-medium leading-tight text-center md:text-left lg:text-xl md:text-lg">
            {{text}}
        </p>
    </div>
</template>


<script>
import Icon from '@/components/Icon.vue'
export default {
  name: 'HorizontalCard',
  components: {
    Icon  
  },
  props: {
    text: {
      type: String,
      required: true,
    },
    icon: {
      type: String,
      required: true,
    }
  }
}
</script>