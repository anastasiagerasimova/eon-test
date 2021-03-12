<template>
    <div class="error-indicator">
        <h3>Произошла ошибка!</h3>
        <p>Что-то пошло не так! Перезагрузите страницу или попробуйте позжу.</p>
    </div>
</template>

<script>
</script>

<style scoped>
    .error-indicator{
        margin: 0 auto;
        margin-top: 70px;
        margin-bottom: 70px;
        max-width: 1170px;
        padding: 70px 50px;
        text-align: center;
        font-size: 18px;
        color: #18191F;
        background: rgba(24, 25, 31, 0.04);
        box-shadow: 0px 0px 1px rgb(12 26 75 / 24%), 0px 3px 8px -1px rgb(50 50 71 / 5%);
    }

    .error-indicator h3{
        font-size: 35px;
        color: #9F06FF;
    }
</style>