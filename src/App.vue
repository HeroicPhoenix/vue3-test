<template>
    <div class="app">
        hello
        <Games></Games>
        <Person2></Person2>
        <Person></Person>
    </div>
</template>

<script>
    import Games from "./components/Games.vue"
    import Person from "./components/Person.vue"
    import Person2 from "./components/Person2.vue"
    export default {
        name: 'App',
        components: {Games, Person, Person2}
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