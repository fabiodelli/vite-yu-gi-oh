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

        <select class="form-select" aria-label="Default select example">
            <option selected>Open this select menu</option>
            <option value="1">One</option>
            <option value="2">Two</option>
            <option value="3">Three</option>
        </select>

        <div class="card_box">
            <div class="result"></div>
            <div class="row d-flex justify-content-between">
                <div class="col-2 bg-black text-white" v-for="card in cards">
                    <img :src="cards.data" alt="">
                </div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped></style>