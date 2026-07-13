<script setup lang="ts">
const props = defineProps({
  class: {
    type: String,
  },
  layoutClass: {
    type: String,
  },
})
</script>

<template>
  <div class="slidev-layout default two-cols-header w-full h-full" :class="layoutClass">
    <div class="col-header">
      <slot />
    </div>
    <div class="col-left" :class="props.class">
      <div class="col-content">
        <slot name="left" />
      </div>
    </div>
    <div class="col-right" :class="props.class">
      <div class="col-content">
        <slot name="right" />
      </div>
    </div>
    <div class="col-bottom" :class="props.class">
      <slot name="bottom" />
    </div>
  </div>
</template>

<style scoped>
/* Stock Slidev had grid-area row 3→3, which collapsed the bottom row. */
.two-cols-header {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: auto 1fr auto;
}
.col-header {
  grid-area: 1 / 1 / 2 / 3;
  min-width: 0;
}
.col-left {
  grid-area: 2 / 1 / 3 / 2;
  min-width: 0;
  min-height: 0;
  overflow: auto;
}
.col-right {
  grid-area: 2 / 2 / 3 / 3;
  min-width: 0;
  min-height: 0;
  overflow: auto;
}
.col-content {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  min-height: 100%;
}
.col-content :deep(> :first-child) {
  margin-top: 0;
}
.col-bottom {
  align-self: end;
  grid-area: 3 / 1 / 4 / 3;
  min-height: 0;
  width: 100%;
  padding-top: 0.5rem;
}
</style>
