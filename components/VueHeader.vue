<template>
    <header class="header">
        <div class="container">
          <img class="header__background" src="@/assets/img/header-background.png" alt="Background image">
          <div class="header__content">
            <h1 class="header__tittle">Найдется всё!</h1>
            <p class="header__text">
                Самые важные вещи для качественной жизни. Ласковые коты, вкусные помидоры и умопомрачительные носки!
            </p>
            <div class="header__btns">
                <nuxt-link active-class="header__btn--active" class="header__btn" to="/tomatoes">Помидоры</nuxt-link>
                <nuxt-link active-class="header__btn--active" class="header__btn" to="/cats">Коты</nuxt-link>
                <nuxt-link active-class="header__btn--active" class="header__btn" to="/socks">Носки</nuxt-link>
            </div>
          </div>
        </div>
    </header>
</template>

<script>
    export default {
        date(){
            return{
  
            }

        },
        methods: {

        },
    }
</script>

<style scoped>
  .container {
    position: relative;
    margin: 0 auto;
    max-width: 1170px;
  }

  .header__background{
    position: absolute;
    right: 0;
    top: -159px;
    bottom: 0;
    z-index: 0;
  }

  .header{
    height: 650px;
    padding-top: 159px;
    background: #18191F;
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  }

  .header__content{
    position: relative;
    z-index: 1;
  }

  .header__tittle{
    margin: 0;
    margin-bottom: 53px;
    padding: 0;
    font-weight: 800;
    font-size: 72px;
    color: #FFFFFF;
  }

  .header__text{
    width: 540px;
    margin: 0;
    margin-bottom: 50px;
    padding: 0;
    font-weight: 400;
    font-size: 18px;
    line-height: 1.778;
    color: #FFFFFF;
  }

  .header__btn{
    display: inline-block;
    width: 190px;
    margin-right: 17px;
    padding: 19px 0;
    border-radius: 33px;
    
    outline: none;
    border: none;
    background: linear-gradient(44.11deg, #CD10FF 15.75%, #9F06FF 84.63%);
    
    text-decoration: none;
    text-align: center;
    white-space: nowrap;
    letter-spacing: 0.02em;
    font-weight: 600;
    font-size: 18px;
    line-height: 22px;
    color: #FFFFFF;

    transition: all 0.22s;
  }

  .header__btn:last-child {
    margin-right: 0;
  }

  .header__btn:hover{
    background: linear-gradient(44.11deg, #10C6FF 15.75%, #9F06FF 84.63%);
  }

  .header__btn--active{
    color: #18191F;
  }
</style>