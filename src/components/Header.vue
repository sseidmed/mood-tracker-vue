<template>
 
        <div class="heading">
            <h1>Mood Tracker</h1>
            <Button 
            :onClick="toggleAddMood"
            :text="showAddMood ? 'Close' : 'Add Mood'"
            :class="showAddMood ? 'red' : '' ">
            Close
            </Button>
            <div v-if="showAddMood">
                <AddMood />
            </div>
        </div>

</template>

<script>
import Button from '@/components/Button.vue';
import AddMood from '@/components/AddMood.vue';
export default {
    name: "Header",
    components: {
       Button,
       AddMood
    },
    data() {
        return {
            showAddMood: false 
        }
    },
    methods: {
        toggleAddMood() {
        // alert(this.showAddMood)
        this.showAddMood = !this.showAddMood
    }
  }

};

</script>

<style>

.heading {
    display: grid;
    grid-template-columns: 2fr 1fr;
    width: 40%;
    height: 8vh;
    margin: 50px auto;
}

h1 {
    grid-auto-columns: 1/2;
}
.red {
    background-color: red
}
.green {
    background-color: green;
}
</style>