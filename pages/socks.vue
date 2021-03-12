<template>
    <div v-if="!errors.length" class="cards-wrapper">
        <sock-card 
          v-for="sock in socks" 
          v-bind:key="sock.id"
          v-bind:sock="sock"
        >
        </sock-card>
    </div>
    <error-indicator v-else-if="errors.length"></error-indicator>
</template>

<script>
import SockCard from '@/components/SockCard'
import ErrorIndicator from '@/components/ErrorIndicator'

export default {
    data() {
        return{
            socks: [],
            errors: []
        }
    },
    components: {
        SockCard,
        ErrorIndicator
    },
    async mounted(){
        try{
            const res = await fetch('https://eon.estate/api/v0/socks')
            const data =  await res.json()

            if(res.status === 200) this.socks = data
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