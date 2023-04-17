<script>
export default {
    name: "AppCard",
    props: {
        cards: Object
    }

}
</script>

<template>
<div>
    <img :src="cards.card_image.image_url_cropped
" alt="">
<h4>{{ cards.name }}</h4>
<p>{{ cards.type }}</p>
</div>
</template>

<style lang="scss" scoped>
</style>