<template>
 
        <div class="heading">
            <div class="heading-elements">
                <h1>Mood Tracker</h1>
                <MyButton 
                @btn-click="$emit('toggle-add-mood')"
                :text="showAddMood ? 'Close' : 'Add Mood'"
                :color="showAddMood ? 'red' : '#60a3bc'" />
            </div>
        </div>

</template>

<script>
import MyButton from '@/components/MyButton.vue';
// import AddMood from '@/components/AddMood.vue';
export default {
    name: "Header",
    components: {
       MyButton,
    },
    props: {
        showAddMood: Boolean
    },
};

</script>

<style>
.heading {
    display: flex;
    flex-direction: column;
    padding: 10px;
}
.heading-elements {
    display: flex;
    justify-content: space-around;
}

h1 {
    grid-auto-columns: 1/2;
}

</style>