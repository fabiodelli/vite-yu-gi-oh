<script>
export default {
    name: 'SiteMain',
    props: { cards: Array},
    emits:['changed'],
    data(){
        return{
            search:'' 

        }
    },
    methods:{
        test(){
            console.log('funziona!');
        }
    }
}
</script>

<template>
    <div class="main">
        <select class="form-select select" aria-label="Default select example" v-model="search" @change="$emit('changed')">
            <option value="alien">Alien</option>
            <option value="mage">Mage</option>
            <option value="warrior">Warrior</option>
            <option value="dragon">Dragon</option>
        </select>
        <div class="card_box">
            <div class="result"><!-- Founded: {{ cards.length }} --></div>
            <div class="row d-flex justify-content-between">
                <div v-for="card in cards" class="col_2 d-flex">
                    <div class="card_item mt-3">
                        <img class="w-100 " :src="card.card_images[0].image_url" alt="">
                        <div class="info p-2 text-center">
                          <div class="mb-2">{{ card.name }}</div>
                          <strong>{{ card.archetype }}</strong>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<style lang="scss" ></style>