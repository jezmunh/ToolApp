<script setup>
import {ref} from "vue";

let selected = ref("");

let form = ref({
    user_input: "",
    result: "Result"
})

function convert() {
    switch (selected.value) {
        case "0":
            form.value.user_input = form.value.user_input.replace(",",".");
            form.value.result = ((Number(form.value.user_input)*0.0328)).toFixed(1); // Calculating the feet value                       
            break;
        case "1":
            form.value.user_input = form.value.user_input.replace(",",".");
            form.value.result = ((Number(form.value.user_input)/0.0328)).toFixed(1); // Calculating the cantimeters value                       
            break;
        default:
            break;
    }
}
</script>
<template>
    <div id="LengthBlock">
        <h1>Enter the value to convert it</h1>
        <p>
        <select v-model="selected">
            <option disabled value="">Please select the unit of measurement</option>
            <option value="0">cm -> ft</option>
            <option value="1">ft -> cm</option>            
          </select>          
        </p>
        <form @submit.prevent="">
            <input type="text" v-model="form.user_input" placeholder="Enter the length value" autocomplete="off" />
            <input type="text" v-model="form.result" placeholder="Result" autocomplete="off" readonly/>
            <button @click="convert">Convert</button>
        </form>
    </div>
</template>
<style lang="scss" scoped>
#LengthBlock {    
    width: 55vw;
    padding: 10px;
    margin-bottom: 10px;
    display: flex;    
    background: #588157;
    color: white;
    border-radius: 10px;
    flex-direction: column;
    margin-left: 0;
    padding-left: 0;
    text-align: center;
    h1 {
        font-size: 30px;
        margin-left: 12px;        
    }
    p {
        margin-top: 20px;
        font-size: 20px;
        line-height: 120%;
    }   
    button {
        width: 48%;
        min-height: 35px;
        border-radius: 10px;
        border: none;
        margin-left: 12px;
        margin-top: 10px;
        transition: all 0.2s;
        background: #3A5A40;
        color: white;        
        &:hover {
            background: #A3B18A;
            cursor: pointer;
        }
        @media screen and (orientation: portrait) {
            width: 90%;
            margin-top: 15px;
          }
    }
    input[type="text"] {
        width: 48%;
        min-height: 30px;
        border-radius: 5px;
        border: none;
        margin-left: 12px;
        margin-top: 10px;
        font-size: 18px;

        &:focus {
            outline: none;
        }
        @media screen and (orientation: portrait) {
            width: 90%;
            margin-top: 15px;
          }
    }
    form {
        display: inline-block;
        text-align: center;
    }
    
}
</style> 