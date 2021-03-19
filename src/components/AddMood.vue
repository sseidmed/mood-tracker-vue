<template>
    <div class="addmood">
        <form @submit="onSubmit">
            <label for="date">Date:</label>
            <input v-model="date" type="date" id="date" name="date"><br>

            <label for="cars">Choose your mood:</label>

            <select v-model="mood_type" name="moods" id="moods">
                <option value="Excellent">Excellent</option>
                <option value="Good">Good</option>
                <option value="Meh">Meh</option>
                <option value="Bad">Bad</option>
                <option value="Awful">Awful</option>
            </select>

            <h3 class="activities-title">Activities</h3>
            <div class="activities">
                <div>
                    <input v-model="selected" type="checkbox" id="sleep" name="sleep" value="Good Sleep">
                    <label for="sleep">Good Sleep</label>
                </div>
                <div>
                    <input v-model="selected" type="checkbox" id="eat" name="eat" value="Eat Healthy">
                    <label for="eat">Eat Healthy</label>
                </div>
                <div>
                    <input v-model="selected" type="checkbox" id="exercise" name="exercise" value="Exercise">
                    <label for="Exercise">Exercise</label>
                </div>
                <div>
                    <input v-model="selected" type="checkbox" id="read" name="read" value="read">
                    <label for="Read">Read</label>
                </div>
                <div>
                    <input v-model="selected" type="checkbox" id="meditate" name="meditate" value="Meditate">
                    <label for="Meditate">Meditate</label>
                </div>
                <div>
                    <input v-model="selected" type="checkbox" id="code" name="code" value="Code">
                    <label for="Code">Code</label>
                </div>
            </div>
            <button type="submit" value="Save Mood">Save Mood</button>
        </form>
    </div>
</template>

<script>

    export default {
        name: "AddMood",
        data() {
            return {
                date: '',
                mood_type: '',
                selected: [],
                activities: [
                    { text: 'Excellent', value: 'Excellent' },
                    { text: 'Good', value: 'Good' },
                    { text: 'Meh', value: 'Meh' },
                    { text: 'Bad', value: 'Bad' },
                    { text: 'Awful', value: 'Awful' }
                ]
            }
        },
        methods: {
            onSubmit(e) {
                e.preventDefault()
                if (!this.date) {
                    alert('Please choose a date')
                    return
                }

                const newMood = {
                    id: Math.floor(Math.random() * 100000),
                    date: this.date, 
                    mood_type: this.mood_type,
                    selected: this.selected
                }
                this.$emit('add-mood', newMood)

                this.date = ''
                this.mood_type = '',
                this.selected = []
            }
            
        }
    }
</script>

<style scoped>

.activities > div {
    margin-top: 10px;
}
select {
    background: #60a3bc;
    width: 140px;
    height: 35px;
    border: 1px solid rgba(204, 204, 204, 0.575);
    font-size: 18px;
}
/* Removes the clear button from date inputs */
input[type="date"]::-webkit-clear-button {
    display: none;
}

/* Removes the spin button */
input[type="date"]::-webkit-inner-spin-button { 
    display: none;
}

/* Always display the drop down caret */
input[type="date"]::-webkit-calendar-picker-indicator {
    color: #2c3e50;
}

/* A few custom styles for date inputs */
input[type="date"] {
    appearance: none;
    -webkit-appearance: none;
    color: #95a5a6;
    font-family: "Helvetica", arial, sans-serif;
    font-size: 18px;
    border:1px solid #ecf0f1;
    background:#60a3bc;
    padding:5px;
    display: inline-block !important;
    visibility: visible !important;
}

input[type="date"], focus {
    color: #1d1d1d;
    box-shadow: none;
    -webkit-box-shadow: none;
    -moz-box-shadow: none;
}

.addmood {
    display: flex;
    background-color: #c8effd;
    padding: 40px;
}
.activities {
    display: flex;
    flex-wrap: wrap;
    margin: 20px 0;
}
.activities > div {
    width: 50%;
}
.activities-title {
    text-align: center;
}

</style>