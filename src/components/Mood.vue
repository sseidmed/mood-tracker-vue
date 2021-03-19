<template>
    <div>
        <div class="type-and-date">
            <h3>{{ mood.mood_type }}</h3>
            <p>{{ mood.date }}</p>
            <div class="icons">
                <i class="fa fa-edit" aria-hidden="true"></i>
                <i class="fa fa-trash"></i>
            </div>
        </div>

        <p v-for="activity in mood.selected" 
        :key="activity"
        class="activities">
            {{ activity }}
        </p>
        <hr>
    </div>
</template>

<script>
    export default {
        name: "Mood",
        props: {
            mood: Object
        }, 

    }
</script>

<style scoped>

.type-and-date {
    display: flex;
    justify-content: space-between;
}
.fa {
    margin-left: 10px;
}
.fa-trash {
    color: red;
}
.fa-edit {
    color: #60a3bc;
}
.activities {
    display: inline;
    background-color: #c8effd;
    margin-right: 5px;
    border-radius: 10px;
}
</style>