<template>
    <div class="container">
        <img src="../assets/pcso-logo.png" alt="pcso-logo">
        <h1>My Lotto Generator</h1>
    </div>
    <button @click="generate()">Generate numbers</button>
    <div class="container">
        <div class="output" v-for="digit in randomDigits" :key="digit">
            {{ digit }}
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            randomDigits : [],
            isPlaying : false
        }
    },
    methods: {
        generate(){
            
            while(this.randomDigits.length < 6){
                let digits = Math.floor((Math.random() * 41))+1;
                if(!this.randomDigits.includes(digits)){
                    this.randomDigits.push(digits);
                }
            }
            
        }
    }
}
</script>

<style scope>
    .container {
        display: flex;
        align-items: center;
        justify-content: center;
    }
    img{
        width: 100px;
    }
    .output{
        padding: 10px;
    }
    button{
        margin: 10px;
        padding: 10px;
    }
</style>