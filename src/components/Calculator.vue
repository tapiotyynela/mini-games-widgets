<template>
    <div>
        <h2>Calculator</h2>
        <form>
            <input type="number" v-model="num1" name="num1" placeholder="Add number">
            <br>
            <input type="number" v-model="num2" name="num2" placeholder="Add another number">
            <br>
        </form>
        <button class="btn" @click="doSum">+</button>
        <button class="btn" @click="doSub">-</button>
        <button class="btn" @click="doMultiply">x</button>
        <button class="btn" @click="doDivide">/</button>
        <button class="btn" @click="reset">Reset</button>
        <p>Summa: {{ sum }}</p>
        <p>Erotus: {{ substarction }}</p>
        <p>Kerto: {{ multiply }}</p>
        <p>Jako: {{ divide }}</p>
        <h3></h3>
    </div>
</template>

<script>
export default {
    name: "Calculator",
    data() {
        return {
            sum: 0,
            substarction: 0,
            divide: 0,
            multiply: 0
        }
    },
    methods: {
        doSum() {
            this.sum = parseInt(this.num1) + parseInt(this.num2)
        },
        doSub() {
            this.substarction = parseInt(this.num1) - parseInt(this.num2)
        },
        doMultiply() {
            this.multiply = parseInt(this.num1) * parseInt(this.num2)
        },
        doDivide() {
            this.divide = parseInt(this.num1) / parseInt(this.num2)
        },
        reset() {
            this.substarction = 0
            this.multiply = 0
            this.sum = 0
            this.divide = 0
        }
        }
    }
</script>