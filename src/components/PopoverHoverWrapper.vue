<script setup lang="ts">
import { ref, watchEffect } from 'vue'
import PopoverWrapper from '@/components/PopoverWrapper.vue'
const popover = ref()
const isHover = ref(false)
const popoverId = 'popover'
interface Props {
    title: string
    description: string
}
defineProps<Props>()

watchEffect(() => {
    const popoverDiv = popover.value?.popoverDiv
    if (!popoverDiv) return
    if (isHover.value) {
        return popoverDiv.showPopover()
    }
    if (!isHover.value) {
        return popoverDiv.hidePopover()
    }
})
</script>

<template>
    <div
        class="popover-hover-trigger w-fit h-fit"
        @mouseenter="isHover = true"
        @mouseleave="isHover = false"
        :aria-describedby="isHover ? popoverId : undefined"
    >
        <slot></slot>
        <PopoverWrapper ref="popover" v-if="isHover" :id="popoverId">
            <div class="bg-slate-700 p-6 rounded-lg my-2 mr-5 max-w-lg">
                <h3 class="text-gray-50 text-xl mb-3 font-semibold">{{ title }}</h3>
                <p class="text-gray-50">{{ description }}</p>
            </div>
        </PopoverWrapper>
    </div>
</template>
<style scoped>
.popover-hover-trigger:hover {
    anchor-name: --anchor_el;
}
</style>
