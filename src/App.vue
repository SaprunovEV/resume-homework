<template>
  <div class="container column">
    <resume-form
        @add-block="addBlock"
    ></resume-form>
    <resume-view
      :blocks="blocks"
    ></resume-view>
  </div>

  <div class="container">
    <app-loader v-if="loading"></app-loader>
    <resume-comments
        :comments="comments"
        :loading="loading"
        @load-comments="loadComments"
    ></resume-comments>
  </div>
</template>

<script>
import ResumeView from "@/components/ResumeView.vue";
import ResumeForm from "@/components/ResumeForm.vue";
import ResumeComments from "@/components/ResumeComments.vue";
import AppLoader from "@/components/AppLoader.vue";
export default {
  name: 'App',
  data() {
    return {
      blocks: [],
      comments: [],
      loading: false,
    }
  },
  methods: {
    addBlock(value) {
      this.blocks.push(value);
      console.log(this.blocks);
    },
    async loadComments() {
      this.loading = true;
      const res = await fetch('https://jsonplaceholder.typicode.com/comments?_limit=42')
      this.comments = await res.json()
      this.loading = false
    }
  },
  components: {
    ResumeView, ResumeForm, ResumeComments, AppLoader
  }
}
</script>

<style>

</style>
