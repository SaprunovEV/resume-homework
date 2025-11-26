<template>
  <div class="card" v-if="comments.length">
    <h2>Комментарии</h2>
    <ul class="list">
      <li
          v-for="comment in comments"
          :key="comment.id"
      >
        <p><strong>{{ comment.email }}</strong></p>
        <small>{{ comment.body }}</small>
      </li>
    </ul>
  </div>
  <p v-else>
    <button class="btn primary" @click="$emit('load-comments')">Загрузить комментарии</button>
  </p>

</template>

<script>
export default {
  name: 'ResumeComments',
  emits: ['load-comments'],
  props: {
    "comments": {
      type: Array,
      validator(value) {
        return value;
      }
    }
  },
}
</script>


<style scoped>

</style>