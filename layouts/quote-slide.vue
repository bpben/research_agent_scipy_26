<template>
  <div class="slidev-layout default quote-slide">
    <slot />
  </div>
</template>

<style scoped>
/* Overrides `.slidev-layout blockquote { text-sm }` for this layout only */
.quote-slide :deep(h1) {
  font-size: 1.65em;
  line-height: 1.2;
  margin-bottom: 0.45em;
}
.quote-slide :deep(blockquote) {
  font-size: 1.12em;
  line-height: 1.35;
  margin-top: 0.55em;
  margin-bottom: 0.55em;
  padding-inline-start: 0.8em;
}
.quote-slide :deep(blockquote > *) {
  font-size: inherit;
  margin-top: 0;
  margin-bottom: 0;
}
.quote-slide :deep(blockquote ul),
.quote-slide :deep(blockquote ol) {
  margin-top: 0.35em;
  margin-bottom: 0.35em;
}
</style>
