<template>
    <div class="results">
        <h3>Имеем следующее...</h3>
        <p>Ваш вес: <span>{{weight}}</span></p>
        <p>Ваш возраст: <span>{{age}}</span></p>
        <p>Ваш рост: <span>{{growth}}</span></p>
        <strong>Ваша норма калорий: <span>{{result}}</span></strong>
    </div>
</template>

<script>
    export default {
        name: "CommonResults",
        props: {
            weight: String,
            age: String,
            growth: String,
            result: Number
        }
    }
</script>

<style scoped>
    .results {
        margin-top: 25px;
        border-top: 1px solid white;
    }
</style>
