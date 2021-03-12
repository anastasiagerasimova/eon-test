<template>
    <div v-if="!errors.length" class="cards-wrapper">
        <tomato-card 
          v-for="tomato in tomatoes" 
          v-bind:key="tomato.id"
          v-bind:tomato="tomato"
        >
        </tomato-card>
    </div>
    <error-indicator v-else-if="errors.length"></error-indicator>
</template>

<script>
import TomatoCard from '@/components/TomatoCard'
import ErrorIndicator from '@/components/ErrorIndicator'

export default {
    data() {
        return{
            tomatoes: [],
            errors: []
        }
    },
    components: {
        TomatoCard,
        ErrorIndicator
    },
    async mounted(){
        try{
            const res = await fetch('https://eon.estate/api/v0/tomatoes')
            const data =  await res.json()

            if(res.status === 200) this.tomatoes = data
            else this.errors.push(data)

        }catch(error){
            this.errors.push(error)
        }
    }
}
</script>

<style>
    .cards-wrapper{
        padding-top: 70px;
    }
</style>