<template>
  <ScoreScreen :score="score" :count="questions.length" />
</template>

<script lang="ts">
import Vue from 'vue';
import IQuestion from '../models/question';
import { mapState, mapGetters, mapMutations } from 'vuex';
import ScoreScreen from '../components/ScoreScreen.vue';
import router from '../router';

export default Vue.extend({
  name: 'home',
  components: {
    ScoreScreen,
  },
  computed: {
    ...mapState('questions', ['questions', 'index', 'score']),
  },
  created(): void {
    if (this.index === 0) {
      router.push({ name: 'home' });
    }
  },
});
</script>
