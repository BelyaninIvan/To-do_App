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
    <li class="list-item" v-if="!(task.complete)">
        <div class="list-item__text">
            <h2 class="list-item__title">{{ task.title }}</h2>
            <p class="list-item__desc">{{ task.desc }}</p>
        </div>
        <div class="list-item__buttons">
          <myButton
            @click="$emit('complete', task)"
          >
          Выполнено
          </myButton>
          <myButton
            @click="$emit('remove', task)"
          >
          Удалить
          </myButton>
        </div>
    </li>
    <li class="list-item list-item_complete" v-else>
        <div class="list-item__text list-item__text_complete">
            <h2 class="list-item__title">{{ task.title }}</h2>
            <p class="list-item__desc">{{ task.desc }}</p>
        </div>
        <div class="list-item__buttons">
          <myButton
            @click="$emit('remove', task)"
          >
          Удалить
          </myButton>
        </div>
    </li>
</template>

<style scoped>
  .list-item {
    border-bottom: 2px solid rgb(241,255,207);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .list-item_complete{
    border-bottom-color: rgb(123, 255, 154);
  }

  .list-item__text_complete{
    text-decoration: line-through;
    color: #3b8646;
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

  .list-item__buttons {
    display: flex;
    column-gap: 15px;
  }
</style>