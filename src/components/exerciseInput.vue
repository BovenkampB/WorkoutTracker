<script setup lang="ts">
defineProps(['excersiseName'])

</script>

<template>
    <h2>{{ excersiseName }}</h2>
    <div class="exercise">
        <p>
            <label class="setName">WU:</label>
            <input type="number" id="reps" name="reps" min="1" max="999"/>
            <label for="reps">Reps</label>
            <input type="number" name="weight" id="weight" min="1" max="999"/>
            <label for="weight">in kgs</label>
        </p>
        <p>
            <label class="setName">Set 1:</label>
            <input type="number" id="reps" name="reps" min="1" max="999"/>
            <label for="reps">Reps</label>

            <input type="number" name="weight" id="weight" min="1" max="999"/>
            <label for="weight">in kgs</label>
        </p>
        <p>
            <label class="setName">Set 2:</label>
            <input type="number" id="reps" name="reps" min="1" max="999"/>
            <label for="reps">Reps</label>

            <input type="number" name="weight" id="weight" min="1" max="999"/>
            <label for="weight">in kgs</label>
        </p>
        <p>
            <label class="setName">Set 3:</label>
            <input type="number" id="reps" name="reps" min="1" max="999"/>
            <label for="reps">Reps</label>

            <input type="number" name="weight" id="weight" min="1" max="999"/>
            <label for="weight">in kgs</label>
        </p>

        <button type="button">add set..</button>
    </div>

    <br/>
    <br/>

</template>

<style scoped>
.exercise {
    display: flex;
    flex-flow: column wrap;
}
.setName{
    /*width: 25px;*/
    //display: flex;
    //flex-flow: column wrap;
}
</style>