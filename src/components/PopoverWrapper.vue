<script setup lang="ts">
import { ref } from 'vue'
const popoverDiv = ref()

defineExpose({ popoverDiv })
</script>
<template>
    <div popover="auto" ref="popoverDiv" aria-live="polite" role="tooltip">
        <slot></slot>
    </div>
</template>

<style scoped></style>
