<template>
  <div class="card card-w70">
    <template v-if="blocks.length">
      <component
          v-for="block in blocks"
          :key="block.id"
          :is="'resume-' + block.type"
          v-bind="{value: block.value}"
      ></component>
    </template>
    <h3 v-else>Добавьте первый блок, чтобы увидеть результат</h3>
  </div>
</template>

<script>
import ResumeTitle from "@/components/parts/ResumeTitle.vue";
import ResumeAvatar from "@/components/parts/ResumeAvatar.vue";
import ResumeSubtitle from "@/components/parts/ResumeSubtitle.vue";
import ResumeText from "@/components/parts/ResumeText.vue";


export default {
  props: ["blocks"],
  components: {
    ResumeTitle, ResumeAvatar, ResumeSubtitle, ResumeText
  }
}
</script>
