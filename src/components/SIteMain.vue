<script>
export default {
    name: 'SiteMain',
    props: {
        cards : Array
    }
}
</script>

<template>
    <div class="main">
        <div class="card_box">
            <div class="result"></div>
            <div class="row d-flex justify-content-between">
                <div class="col-2 bg-black text-white">
                    <img src="cards.data" alt="">
                </div>      
            </div>
        </div>
    </div>
</template>


<style lang="scss" scoped></style>