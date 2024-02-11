<script setup>
import {RouterLink} from "vue-router";
import {ref} from "vue";
import TemperatureEm from "../components/TemperatureCnv.vue";
import LengthEm from "../components/LengthCnv.vue";


let currentSection = ref(0);

function changeSection(order) { // order = 0 is Length Converter and order = 1 is Temperature one
    switch (order) {
        case 0:
            currentSection.value = 0;
            break;
        case 1:
            currentSection.value = 1;
            break
        default:
            break;
    }
}
</script>
<template>
    <div id="toolElement">
        <h1>Tools</h1>
        <nav id="buttonGroup">
            <button @click="changeSection(0)">Length converter</button>
            <button @click="changeSection(1)">Temperature converter</button>
        </nav>
        <div v-if="currentSection == 0">
            <LengthEm />
        </div>
        <div v-else>
            <TemperatureEm />
        </div>
        
    </div>    
</template>

<style lang="scss" scoped>
#toolElement {    
    width: 60vw;
    padding: 10px;
    margin-bottom: 10px;
    display: flex;    
    background: #588157; //c3c9ce
    color: white;
    border-radius: 10px;
    flex-direction: column;
    h1 {
        font-size: 30px;
        margin-left: 12px;        
    }
    p {
        margin-top: 20px;
        font-size: 20px;
        line-height: 120%;
    }
    #buttonGroup {
        display: inline-block;
        margin-top: 20px;
        
    }
    button {
        width: 48%;
        min-height: 35px;
        border-radius: 10px;
        border: none;
        margin-left: 12px;
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
    
}
TemperatureEm {
    margin: 0;
    padding: 0;
}
LengthEm {
    margin: 0;
    padding: 0;
}



</style>