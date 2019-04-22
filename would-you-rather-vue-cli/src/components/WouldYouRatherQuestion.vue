<template>
    <div>
        <div>
            <h1>Would you rather...</h1>
            <p>{{question}}</p>

            <input type ="radio" v-bind:value="answer1" v-model="choice" v-on:change="$emit('answer-changed',choice)">
            <label>{{answer1}}</label>
            <input type ="radio" v-bind:value="answer2" v-model="choice" v-on:change="$emit('answer-changed',choice)">
            <label>{{answer2}}</label>

        </div>
    </div>
</template>

<script>
    export default {
        name: "WouldYouRatherQuestion.vue",
        data() {
            return {
                choice: ''
            }
        },

        props: {
            question: String,
            answer1: String,
            answer2: String
        },

    }
</script>

<style scoped>

</style>