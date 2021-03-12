<template>
    <div class="card" >
        <div class="card__img-cell">
            <img v-bind:src="img" alt="Socks">
            <div class="cards__btns">
                <button 
                    class="cards__btn" v-bind:class="addActiveClass(img, image)"
                    v-for="image in sock.images" 
                    v-bind:key="image"
                    v-on:click="chageImage(image)"
                ></button>
            </div>
        </div>
        <div class="card__text-cell">
            <h4 class="card__title">{{sock.name}}</h4>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return{
            img: this.sock.images[0]
        }
    },
    props: ['sock'],
    methods: {
        chageImage(img){
            this.img = img
        }, 
        addActiveClass(img1, img2){
            return img1 == img2 ? 'cards__btn--active' : ''
        }
    },
}
</script>

<style scoped>
    .card{
        display: flex;
        flex-direction: column;
        width: 470px;
        height: 368px;
        padding: 20px 25px 20px 25px;
        margin-bottom: 50px;
        margin-right: 50px;
        box-shadow: 0px 0px 1px rgba(12, 26, 75, 0.24), 0px 3px 8px -1px rgba(50, 50, 71, 0.05);
        box-sizing: border-box
    }

    .card__img-cell{
        position: relative;
        display: flex;
        justify-content: center;
        width: 100%;
        height: 250px;
        margin-bottom: 25px;
    }

    .cards__btns{
        display: flex;
        position: absolute;
        bottom: 15px;
    }

    .cards__btn{
        width: 20px;
        height: 10px;
        margin-right: 10px;
        padding: 0;
        background: #FFFFFF;
        border-radius: 2px;
        outline: none;
        border: none;
        cursor: pointer;
        background: rgba(255, 255, 255, 0.5);
    }

    .cards__btn:last-child{
        margin-right: 0;
    }

    .cards__btn--active{
        background: #FFFFFF;
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
        letter-spacing: 0;
        line-height: 1;
        color: #425466;
    }
</style>