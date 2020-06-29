<template>
    <form @submit.prevent="computeCalories">
        <div class="fieldset">
            <h2 class="header">Калькулятор калорий</h2>
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
            <CommonResults v-if="show" :growth="growth" :weight="weight" :age="age" :idealWeight="idealWeight" :result="result"/>
        </div>
    </form>
</template>

<script>
    import CommonResults from '../components/CommonResults';

    export default {
        name: "FormInfo",
        components: {
            CommonResults
        },
       data() {
           return {
               growth: null,
               weight: null,
               age: null,
               result: null,
               show: false,
               idealWeight: null
           }
       },

        methods: {
            computeIdealWeight() {
                this.idealWeight = ((this.growth - 100) * 1.15).toFixed(0);
                return this.idealWeight;
            },

            computeCalories() {
                this.result = (10 * Number(this.weight)) + ( 5 * Number(this.age)) + (6.25 * Number(this.growth));

                this.computeIdealWeight();

                this.show = true;
                return this.result;
            }
        }
    }
</script>

<style scoped>
    .fieldset {
        font-family: 'Roboto', sans-serif;
        color: white;
        border: none;
        font-size: 15px;
        border-radius: 5px;
        padding: 2em;
        -webkit-box-shadow: 0px 0px 8px 0px rgba(97,97,97,1);
        -moz-box-shadow: 0px 0px 8px 0px rgba(97,97,97,1);
        box-shadow: 0px 0px 8px 0px rgba(97,97,97,1);
        background-color: #4CAF50;
    }

    .header {
        font-weight: 700;
        color: #34495e;
    }

    input, button {
        font-family: 'Roboto', sans-serif;
        font-size: 0.9rem;
        padding: 0.5em;
        border-radius: 5px;
        outline: none;
        border: 1px solid #ccc;
        font-weight: 500;
    }

    label {
        color: #4C4A48;
        font-size: 1rem;
        font-family: 'Roboto', sans-serif;
    }

    input {
        color: #9E9E9E;
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
        background-color: #651FFF;
        border: none;
        color: white;
    }
</style>
