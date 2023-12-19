<template>
<div>
    <div class="container mt-5">
    <div class="row">
        <div class="col-md-4 offset-md-4">
        <h2 class="mb-4">Calculadora Aritmética</h2>
        <form>
            <div class="form-group">
            <label for="num1">Número 1</label>
            <input type="number" class="form-control" v-model="num1" @input="calcularResultado" />
            </div>
            <div class="form-group">
            <label for="num2">Número 2</label>
            <input type="number" class="form-control" v-model="num2" @input="calcularResultado" />
            </div>
            <div class="form-group">
            <label for="operacao">Operação</label>
            <select class="form-control" v-model="operacao" @change="calcularResultado">
                <option value="soma">Soma</option>
                <option value="subtracao">Subtração</option>
                <option value="multiplicacao">Multiplicação</option>
                <option value="divisao">Divisão</option>
            </select>
            </div>
        </form>
        <div class="mt-3">
            <h4>Resultado: {{ resultado }}</h4>
        </div>
        </div>
    </div>
    </div>
</div>
</template>

<script>
export default {
data() {
    return {
    num1: 0,
    num2: 0,
    operacao: 'soma',
    resultado: 0,
    };
},
methods: {
    calcularResultado() {
    switch (this.operacao) {
        case 'soma':
        this.resultado = this.num1 + this.num2;
        break;
        case 'subtracao':
        this.resultado = this.num1 - this.num2;
        break;
        case 'multiplicacao':
        this.resultado = this.num1 * this.num2;
        break;
        case 'divisao':
        this.resultado = this.num1 / this.num2;
        break;
        default:
        this.resultado = 0;
    }
    },
},
};
</script>

<style scoped>
</style>
