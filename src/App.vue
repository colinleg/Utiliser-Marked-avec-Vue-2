<template>
  <div id="app">
    <div class="container">

      <div>
        <div class="infos">
          <input v-model="titre" id="titre" type="text" class="titre" placeholder="Le titre">
          <input :value="date" type="date" name="date" id="">
        </div>

        <md-input
        @update="update"
        class=""
        />
      </div>

      <div>
        <div class="infos">
          <input :value="titre" type="text" class="output" disabled>
          <input :value="dateNow" type="date" name="date" disabled id="">
        </div>
        <md-output
          v-html="marked"
          class=""
        />
      </div>
    </div>


  </div>
</template>

<script>

import marked from './marked'
import mdInput from '@/components/MarkdownInput.vue'
import mdOutput from '@/components/MarkdownOutput.vue'


export default {
  name: 'App',
  data(){
    return {
      marked: '',
      titre: '',
      date: new Date(),
      dateNow: null
    }
  },
  methods: {
    update(string) {
      this.marked = marked.parse(string)
    }
  },
  components: {
    mdInput,
    mdOutput
  }
}
</script>

<style lang="css" scoped>

.infos {
  display: flex;
  justify-content: space-between;
  margin-bottom: 2rem;
}

.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
</style>

