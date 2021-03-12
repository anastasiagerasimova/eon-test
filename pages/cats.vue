<template>
    <div v-if="!errors.length" class="cards-wrapper">
        <cat-card
          v-for="cat in cats" 
          v-bind:key="cat.id"
          v-bind:cat="cat"
        >
        </cat-card>
    </div>
    <error-indicator v-else-if="errors.length"></error-indicator>

</template>

<script>
import CatCard from '@/components/CatCard.vue'
import ErrorIndicator from '@/components/ErrorIndicator'

export default {
    data() {
        return{
            cats: [],
            errors: []
        }
    },
    components: {
        CatCard,
        ErrorIndicator
    },
    async mounted(){
        try{
            const res = await fetch('https://eon.estate/api/v0/cats')
            const data =  await res.json()

            if(res.status === 200) this.cats = data
            else this.errors.push(data)

        }catch(error){
            this.errors.push(error)
        }
    }

}
</script>

<style scoped>
    .cards-wrapper{
        padding-top: 70px;
        display: flex;
        flex-wrap: wrap;
    }
</style>