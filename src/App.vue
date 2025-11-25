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
    <p>
      <button class="btn primary">Загрузить комментарии</button>
    </p>
    <div class="card" v-if="loading">
      <h2>Комментарии</h2>
      <ul class="list">
        <li class="list-item">
          <div>
            <p><strong>test@microsoft.com</strong></p>
            <small>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi, reiciendis.</small>
          </div>
        </li>
      </ul>
    </div>
    <div class="loader" v-else></div>
  </div>
</template>

<script>
import ResumeView from "@/components/ResumeView.vue";
import ResumeForm from "@/components/ResumeForm.vue";
export default {
  name: 'App',
  data() {
    return {
      blocks: [],
      loading: false,
    }
  },
  methods: {
    addBlock(value) {
      this.blocks.push(value);
      console.log(this.blocks);
    }
  },
  components: {
    ResumeView, ResumeForm
  }
}
</script>

<style>

</style>
