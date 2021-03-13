<template>
    <div class="addmood">
        <form action="">
            <label for="date">Date</label>
            <input type="date" id="date" name="date">

            <label for="cars">Choose your mood:</label>

            <select name="moods" id="moods">
                <option value="excellent">Excellent</option>
                <option value="good">Good</option>
                <option value="meh">Meh</option>
                <option value="bad">Bad</option>
                <option value="awful">Awful</option>
            </select>

            <div class="activities">
                <div>
                    <input type="checkbox" id="sleep" name="sleep" value="sleep">
                    <label for="sleep">Good Sleep</label>
                </div>
                <div>
                    <input type="checkbox" id="eat" name="eat" value="eat">
                    <label for="vehicle2">Eat Healthy</label>
                </div>
                <div>
                    <input type="checkbox" id="exercise" name="exercise" value="exercise">
                    <label for="exercise">Exercise</label>
                </div>
                <div>
                    <input type="checkbox" id="read" name="read" value="read">
                    <label for="read">Read</label>
                </div>
                <div>
                    <input type="checkbox" id="meditate" name="meditate" value="meditate">
                    <label for="meditate">Meditate</label>
                </div>
                <div>
                    <input type="checkbox" id="code" name="code" value="code">
                    <label for="code">Code</label>
                </div>
            </div>
            <Button :onClick="submitView">Submit</Button>
        </form>
    </div>
</template>

<script>
import Button from '@/components/Button.vue';
    export default {
        name: "AddMood",
        components: {
            Button
        },
        methods: {
            submitView() {
                alert("Alert from the Submit button")
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
    width: 420px;
    margin: auto;
    padding: 40px;
}
</style>