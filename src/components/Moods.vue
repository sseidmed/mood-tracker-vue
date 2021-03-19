<template>
    <div class='mood-content'>
        <div v-for="mood in moods" :key="mood.id">
            <Mood :mood="mood" class="mood"/>
        </div> 
    </div>
</template>

<script>
import Mood from '@/components/Mood.vue';

    export default {
        name: "Moods",
        props: {
            moods: Array
        },
        components: {
            Mood
        }
    }
</script>

<style scoped>
.mood-content {
    display: flex;
    flex-direction: column;
    flex: 70%;
}

</style>