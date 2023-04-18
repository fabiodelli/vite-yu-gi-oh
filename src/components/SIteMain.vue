<script>
export default {
    name: 'SiteMain',
    props: {
        cards: Array
    }
}
</script>

<template>
    <div class="main">
        <select class="form-select select" aria-label="Default select example">
            <option selected>Alien</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
        </select>
        <div class="card_box">
            <div class="result"></div>
            <div class="row d-flex justify-content-between">
                <div v-for="card in cards" class=" d-flex">
                    <div class="card_item mt-3">
                        <img class="w-100 " :src="card.card_images[0].image_url" alt="">
                        <div class="info p-2">
                          <div class="mb-2">{{ card.name }}</div>
                          <div>{{ card.archetype }}</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" ></style>