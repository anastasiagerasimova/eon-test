<template>
    <div class="card" >
        <div class="card__img-cell">
            <img v-bind:src="tomato.image" alt="Tomato">
        </div>
        <div class="card__text-cell">
            <h4 class="card__title">{{tomato.name}}</h4>
            <p class="card__text">{{tomato.description}}</p>
            <div class="card__price">{{tomato.price}} руб.</div>
        </div>
    </div>
</template>

<script>

export default {
    props: ['tomato']
}
</script>

<style scoped>
    .card{
        display: flex;
        max-width: 995px;
        height: 300px;
        padding: 25px;
        margin-bottom: 50px;
        box-shadow: 0px 0px 1px rgba(12, 26, 75, 0.24), 0px 3px 8px -1px rgba(50, 50, 71, 0.05);
        box-sizing: border-box
    }

    .card:last-child{
        margin-bottom: 0;
    }

    .card__img-cell{
        display: flex;
        justify-content: center;
        max-width: 350px;
        flex-grow: 1;
        flex-shrink: 1;
        height: 100%;
        margin-right: 50px;
    }

    .card__img-cell img{
        max-width: 100%;
        height: 100%;
        object-fit: contain;
    }

    .card__text-cell{
        max-width: 545px;
        flex-grow: 1;
        flex-shrink: 3;
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

    .card__text{
        /* max-height: 145px;
        overflow: hidden; */

        display: -webkit-box;
        -webkit-line-clamp: 6;
        -webkit-box-orient: vertical;
        overflow: hidden;
    
        padding: 0;
        margin: 0;
        margin-bottom: 25px;
        font-weight: 400;
        font-size: 18px;
        line-height: 1.34;
        color: #425466;
    }

    .card__price{
        margin-top: auto;
        font-weight: bold;
        font-size: 24px;
        line-height: 1;
        color: #27272E;
    }

</style>