<template>
    <div>
    <li v-for="message in messages">
        {{ message}}<br>
    </li>
    </div>
</template>

<script>
    export default {
        name: "YouWouldRather",
        props:{
            messages:Array
        }
    }
</script>

<style>

</style>