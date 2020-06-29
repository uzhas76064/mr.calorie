<template>
    <div class="results">
        <div class="calorie-results">
            <h3>Имеем следующее...</h3>
            <p>Ваш вес: <span>{{weight}}</span></p>
            <p>Ваш возраст: <span>{{age}}</span></p>
            <p>Ваш рост: <span>{{growth}}</span></p>
            <strong>Ваша норма калорий: <span>{{result}}</span></strong>
        </div>

        <div class="weight-results">
            <p>Учитывая рост - {{growth}} и ваш возраст - {{age}}, ваш идеальный вес должен быть: {{idealWeight}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "CommonResults",
        props: {
            weight: String,
            age: String,
            growth: String,
            result: Number,
            idealWeight: Number
        }
    }
</script>

<style scoped>
    .results {
        margin-top: 25px;
        border-top: 1px solid white;
        display: flex;
        justify-content: space-between;
    }

    .weight-results {
        width: 52%;
        align-self: center;
    }
</style>
