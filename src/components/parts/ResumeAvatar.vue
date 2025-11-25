<script setup>

</script>

<template>
<div class="avatar">
  <img alt="Аватар нашего человека" :src="$attrs.value" />
</div>
</template>

<style scoped>
  .avatar {
    display: flex;
    align-items: center;
  }

  .avatar img {
    width: 150px;
    height: auto;
    border-radius: 50%;
  }
</style>