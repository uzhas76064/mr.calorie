<template>
    <form @submit.prevent="computeCalories">
        <div class="fieldset">
            <h2>Калькулятор калорий</h2>
            <div class="weight-block">
                <p><label for="weight">Введите ваш вес</label></p>
                <input v-model="weight" type="text" id="weight" placeholder="Вес" required>
            </div>
            <div class="growth-block">
                <p><label for="growth">Введите рост</label></p>
                <input v-model="growth" type="text" id="growth" placeholder="Рост" required>
            </div>
            <div class="age-block">
                <p><label for="age">Введите возраст</label></p>
                <input v-model="age" type="text" id="age" placeholder="Возраст" required>
                <button class="count-btn">Подсчитать</button>
            </div>

        </div>
        <p>{{weight}} {{growth}} {{age}}</p>
        <p :result="result">{{result}}</p>
    </form>
</template>

<script>
    export default {
        name: "FormInfo",
       data() {
           return {
               growth: null,
               weight: null,
               age: null,
               result: null
           }
       },

        methods: {
            computeCalories() {
                this.result = (10 * Number(this.weight)) + ( 5 * Number(this.age)) + (6.25 * Number(this.growth));
                return this.result;
            }
        }
    }
</script>

<style scoped>
    .fieldset {
        border: 1px solid #ccc;
        font-size: 15px;
        border-radius: 5px;
        padding: 1em;
    }

    input, button {
        padding: 0.5em;
        border-radius: 5px;
        outline: none;
        border: 1px solid #ccc;
    }

    .weight-block, .growth-block {
        display: inline-block;
    }

    .weight-block {
        margin-right: 1.3em;
        margin-bottom: 1.2em;
    }

    .count-btn {
        margin-left: 1.3em;
        width: 32.6%;
    }
</style>
