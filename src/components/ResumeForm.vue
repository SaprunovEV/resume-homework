<template>
  <form class="card card-w30" @submit.prevent="update">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select id="type" v-model="type">
        <option value="title">Заголовок</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea v-model="value" id="value" rows="3"></textarea>
    </div>

    <button class="btn primary" :disabled="!isValid">Добавить</button>
  </form>
</template>

<script>
export default {
  emits: ['add-block'],
  data() {
    return {
      type: 'title',
      value: '',
    }
  },
  computed: {
    isValid() {
      return this.value.length > 3
    }
  },
  methods: {
    update() {
      console.log(this.value)
      console.log(this.type)

      this.$emit('add-block', {
        type: this.type,
        value: this.value,
        id: Date.now(),
      })

      this.value=''
      this.type='title'
    }
  }
}
</script>

<style scoped>

</style>