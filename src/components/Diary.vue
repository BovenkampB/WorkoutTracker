<script setup lang="ts">
import {ref} from 'vue'
import axios from "axios";
import ExerciseInput from "@/components/exerciseInput.vue";

const selected = ref('')

const workoutNames = ["Maandag FB", "Woensdag FB", "Vrijdag FB"]
const workout0 = ["Squat", "DB incline press", "Lat pulldown", "Tricep kickbacks", "Calf raises", "DB curls"]
const workout1 = ["Deadlift", "Overhead Press", "Machine rows", "Leg extensions", "Cable flies", "DB skull crushers"]
const workout2 = ["BP", "DB walking lunges", "Reverse grip lat pulldowns", "Seated face pulls (cable)", "DB lateral raises", "Lying leg curls"]


// const ex1 = ["squats", "Deadlift", "Bench Press"];
// const ex2 = ["DB incline press", "Overhead Press", "DB walking lunges"];
// const ex3 = ["Lat pulldown", "Machine rows", "Reverse grip lat pulldowns"];
// const ex4 = ["Tricep kickbacks", "Leg extensions", "Seated face pulls (cable)"];
// const ex5 = ["Calf raises", "Cable flies", "DB lateral raises"];
// const ex6 = ["DB curls", "DB skull crushers", "Lying leg curls"];


defineProps(['modelValue'])
defineEmits(['update:modelValue'])



async function logData() {
    try {
        const response = await axios.get('http://localhost:3000/');
        console.log(response);
        alert(response);
    } catch (error) {
        console.error(error);
    }
}

</script>
<template>
    <div class="diary">
        <div class="selectbox">
            <select v-model="selected">
                <option disabled value="">Which workout?</option>
                <option value="0">Monday - FB 1</option>
                <option value="1">Wednesday - FB 2</option>
                <option value="2">Friday - FB 3</option>
            </select>
        </div>

        <form class="child inputForm">

            <h1 v-if="selected">{{ workoutNames[selected] }}</h1>
            <h1 v-else>Kies je workout hierboven..</h1>


            <ExerciseInput v-if="selected==0" v-for="ex in workout0"
                           :excersiseName="ex"/>
            <ExerciseInput v-if="selected==1" v-for="ex in workout1"
                           :excersiseName="ex"/>
            <ExerciseInput v-if="selected==2" v-for="ex in workout2"
                           :excersiseName="ex"/>

                        <p>
                            <button @click="logData" type="button">Submit</button>
                        </p>
        </form>
        <!--        <button @click="count++">Voeg setje toe</button>-->
        <!--        <p>Count is: {{ count }}</p>-->
    </div>
</template>

<style scoped>
.diary {
    display: flex;
    min-height: 100vh;
    flex-flow: column;
}

.child {
    width: 450px; /* Or whatever */
    height: 150px; /* Or whatever */
    margin-top: 50px;
}

.inputForm {

}


</style>