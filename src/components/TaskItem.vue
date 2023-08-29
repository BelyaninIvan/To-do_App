<script>
    export default {
        props: {
            task: {
                type: Object,
                required: true
            }
        }
    }
</script>

<template>
    <li class="list-item">
        <h2 class="list-item__title">{{ task.title }}</h2>
        <p class="list-item__desc">{{ task.desc }}</p>
    </li>
</template>

<style scoped>
  .list-item {
    border-bottom: 2px solid rgb(241,255,207);
  }
  .list-item__title {
    margin: 0;
    font-size: 22px;
    line-height: 1.2;
    font-weight: 700;
  }

  .list-item__desc {
    margin: 10px 0 10px;
    font-size: 16px;
    line-height: 1.2;
    font-weight: 400;
  }
</style>