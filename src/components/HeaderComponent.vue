<script>
    var day = new Date().getDate();
    if (day < 10) day = '0' + day;
    var month = new Date().getMonth();
    if (month < 10) month = '0' + month;
    var year = new Date().getFullYear();

    export default {
        data() {
            return {
                today: `${day}.${month}.${year}`
            } 
        }
    }
</script>

<template>
    <h1 class="header__title">To-Do приложение</h1>
    <h2 class="header__subtitle">Приложение для отслеживания выполнения задач</h2>
    <p class="header__date">Сегодня: {{ today }} </p>
</template>

<style scoped>
.header__title {
    margin: 0;
    margin-top: 20px;
    font-size: 34px;
    font-weight: 700;
    color: #3b6486;
}

.header__subtitle {
    margin: 0;
    margin-top: 15px;
    font-size: 24px;
    font-weight: 400;
    color: #3b6486;
}

.header__date {
    margin: 0;
    margin-top: 15px;
    font-size: 24px;
    font-weight: 400;
    color: #3b6486;
}
</style>