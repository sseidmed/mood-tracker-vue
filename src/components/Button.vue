<template>
 
        <button 
            @click="onClick" 
            class="button">
            <slot></slot>
        </button>
        
 
</template>

<script>
    export default {
        name: "Button",
        props: {
            onClick: {
                type: Function,
                required: true
            },   
            showAddMood: Boolean

        }
    }
</script>

<style>
button {
    color: #fff !important;
    text-transform: uppercase;
    text-decoration: none;
    background: #60a3bc;
    padding: 20px;
    border-radius: 30px;
    display: inline-block;
    height: 8vh;
    border: 1px solid black;
    transition: all 0.4s ease 0s;
}
button:hover {
    text-shadow: 0px 0px 6px rgba(255, 255, 255, 1);
    -webkit-box-shadow: 0px 5px 40px -10px rgba(0,0,0,0.57);
    -moz-box-shadow: 0px 5px 40px -10px rgba(0,0,0,0.57);
    transition: all 0.4s ease 0s;
}
button:focus-within{
  outline: none;
}
</style>