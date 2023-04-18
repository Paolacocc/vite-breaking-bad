<script>
export default {
    name: "AppCard",
    props: {
        cards: Object
    }

}
</script>

<template>
<div class="card-details">
    <img :src="cards.card_images[0].image_url_cropped
" alt="">
<h4 class="text-center mt-1 p-2">{{ cards.name }}</h4>
<p class="text-center">{{ cards.type }}</p>
</div>
</template>

<style lang="scss" scoped>
@use "../styles/variables.scss" as *;
.card-details {
    height: 250px;
    background-color: $primary;
}
img {
    height: 150px;
    object-fit: cover;
}
h4 {
    font-size: .8rem;
    color: white;
}
p {
    font-size: .5rem;
}
</style>