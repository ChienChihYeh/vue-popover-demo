<script setup lang="ts">
import PopoverHoverWrapper from '@/components/PopoverHoverWrapper.vue'

const myTitle = "I'm a popover"
const myDescription =
    'The Popover API provides developers with a standard, consistent, flexible mechanism for displaying popover content on top of other page content. Popover content can be controlled either declaratively using HTML attributes, or via JavaScript.'
</script>

<template>
    <main>
        <div class="h-screen flex flex-col items-start justify-center mx-5 gap-3">
            <h1 class="text-3xl">Hello There!</h1>
            <PopoverHoverWrapper :title="myTitle" :description="myDescription">
                <p class="p-3 border rounded-lg">Hover Here To Show Popover</p>
            </PopoverHoverWrapper>
            <PopoverHoverWrapper :title="myTitle" :description="myDescription">
                <p class="p-3 border rounded-lg">Hover Here To Show Popover</p>
            </PopoverHoverWrapper>
            <PopoverHoverWrapper :title="myTitle" :description="myDescription">
                <p class="p-3 border rounded-lg">Hover Here To Show Popover</p>
            </PopoverHoverWrapper>
        </div>
    </main>
</template>
