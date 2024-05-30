<script setup lang="ts">
import { ref } from 'vue'
const popoverDiv = ref()

defineExpose({ popoverDiv })
</script>
<template>
    <div popover="auto" ref="popoverDiv">
        <slot></slot>
    </div>
</template>

<style scoped>

</style>
