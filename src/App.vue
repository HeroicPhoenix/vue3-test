<template>
    <div class="app">
        hello
        <Games></Games>
        <Person></Person>
    </div>
</template>

<script>
    import Games from "./components/Games.vue"
    import Person from "./components/Person.vue"
    export default {
        name: 'App',
        components: {Games, Person}
    }
</script>

<style>
.app{
    background-color: #ddd;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
}
</style>