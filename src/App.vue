<template>
  <div id="app">
    <div class="tracker">
        <Header @toggle-add-mood="toggleAddMood" 
        :showAddMood="showAddMood"
        />
        <div v-if="showAddMood">
          <AddMood @add-mood="addMood"/>
        </div>
    </div>
    <Moods class="moods" :moods="moods" />
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Moods from '@/components/Moods.vue';
import AddMood from '@/components/AddMood.vue';


export default {
  data() {
    return {
      moods: [],
      showAddMood: true,
    }
  },
  components: {
    Header,
    Moods,
    AddMood
  },
  methods: {
    toggleAddMood() {
      this.showAddMood = !this.showAddMood
    },
    addMood(mood) {
      this.moods = [...this.moods, mood]
    }
  },
  created() {
    this.moods = [
      {
        id: 1,
        date: '03/23/2021',
        mood_type: 'Excellent',
        selected: ['Exercise']
      },
      {
        id: 2,
        date: '03/24/2021',
        mood_type: 'Bad',
        selected: ['Read', 'Exercise']
      },
      {
        id: 3,
        date: '03/25/2021',
        mood_type: 'Meh',
        selected: ['Good Sleep', 'Code']
      },
    ]
  }
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 70%;
  margin: 60px auto;
  display: flex;
}
.tracker {
  display: flex;
  flex-direction: column;
  flex-basis: 50%;
}
.moods {
  margin-left: 30px;
}
</style>
