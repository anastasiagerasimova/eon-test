<template>
    <div class="card" >
        <div class="card__img-cell">
            <img v-bind:src="cat.image" alt="Cat">
        </div>
        <div class="card__text-cell">
            <h4 class="card__title">{{cat.name}}</h4>
            <ul class="card__list">
                <li class="card__list-item"
                    v-for="advantage in cat.advantages" 
                    v-bind:key="advantage"
                >{{advantage}}</li>
            </ul>
        </div>
    </div>
</template>

<script>

export default {
    props: ['cat']
}
</script>

<style scoped>
    .card{
        display: flex;
        flex-direction: column;
        max-width: 470px;
        width: 470px;
        height: 461px;
        padding: 25px;
        margin-bottom: 50px;
        margin-right: 50px;
        box-shadow: 0px 0px 1px rgba(12, 26, 75, 0.24), 0px 3px 8px -1px rgba(50, 50, 71, 0.05);
        box-sizing: border-box
    }

    .card__img-cell{
        display: flex;
        justify-content: center;
        width: 100%;
        height: 250px;
        margin-bottom: 25px;
    }

    .card__img-cell img{
        width: 100%;
        max-height: 100%;
        object-fit: cover;
    }

    .card__text-cell{

    }

    .card__title{
        padding: 0;
        margin: 0;
        margin-bottom: 20px;
        font-weight: 600;
        font-size: 24px;
        line-height: 1;
        color: #425466;
    }

    .card__list{
        margin: 0;
        padding: 0;
        list-style: none;
        font-family: Inter;
        font-weight: 400;
        font-size: 18px;
        line-height: 1.333;
        color: #425466;
    }

    .card__list-item{
        position: relative;
        padding-left: 24px;
        padding-bottom: 10px;
    }

    .card__list-item::before{
        content: '—';
        left: 0;
        position: absolute;

    }
</style>