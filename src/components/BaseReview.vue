<script setup>
import { onMounted, nextTick } from 'vue'
import ContentContainer from './ContentContainer.vue'
onMounted(async () => {
    await nextTick() // гарантируем, что div уже в DOM
    window.cackle_widget = window.cackle_widget || []
    window.cackle_widget.push({ widget: 'Review', id: 81869 })
    if (!document.getElementById('cackle-widget-script')) {
        const script = document.createElement('script')
        script.id = 'cackle-widget-script'
        script.type = 'text/javascript'
        script.async = true
        script.src = (location.protocol === 'https:' ? 'https:' : 'http:') + '//cackle.me/widget.js'
        document.head.appendChild(script)
    }
})

</script>

<template>

    <div id="comments"></div>
</template>
