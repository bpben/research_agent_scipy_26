<script setup lang="ts">
import { computed } from 'vue'
import { handleBackground } from '@slidev/client/layoutHelper.ts'

const props = defineProps({
  image: { type: String },
  class: { type: String },
  backgroundSize: { type: String, default: 'cover' },
})

const style = computed(() => handleBackground(props.image, false, props.backgroundSize))
</script>

<template>
  <div class="grid grid-cols-2 h-full w-full gap-4 auto-rows-fr">
    <div class="slidev-layout default min-w-0 overflow-y-auto" :class="props.class">
      <slot />
    </div>
    <div class="flex min-h-0 min-w-0 flex-col">
      <div class="min-h-0 w-full flex-1" :style="style" />
      <div class="shrink-0 pt-2 text-left text-xs leading-snug opacity-85">
        <slot name="caption" />
      </div>
    </div>
  </div>
</template>
