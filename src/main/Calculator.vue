<template>
  <div class="calculator">
      <Display :value = "displayValue" />
      <Button label = "AC" triple @on-click = "clearMemory" />
      <Button label = "/" operation @on-click = "setOperation" />
      <Button label = "7" @on-click = "addDigit" />
      <Button label = "8" @on-click = "addDigit"/>
      <Button label = "9" @on-click = "addDigit"/>
      <Button label = "*" operation @on-click = "setOperation"/>
      <Button label = "4" @on-click = "addDigit"/>
      <Button label = "5" @on-click = "addDigit"/>
      <Button label = "6" @on-click = "addDigit"/>
      <Button label = "-" operation @on-click = "setOperation"/>
      <Button label = "1" @on-click = "addDigit"/>
      <Button label = "2" @on-click = "addDigit"/>
      <Button label = "3" @on-click = "addDigit"/>
      <Button label = "+" operation @on-click = "setOperation"/>
      <Button label = "0" double @on-click = "addDigit"/>
      <Button label = "." @on-click = "addDigit"/>
      <Button label = "=" operation @on-click = "setOperation"/>
  </div>
</template>

<script>
import Display from "../components/Display"
import Button from "../components/Button"
export default {
    data: function(){
        return {
            displayValue: "0",
            clearDisplay: false,
            operation: null,
            values: [0, 0],
            corrent: 0
        }
    },
    components: { Button, Display },
    methods: {
        clearMemory(){
            Object.assign(this.$data, this.$options.data())
        },
        setOperation(operation){
            console.log('Operação ' + operation)
        },
        addDigit(n){
            console.log('Digito ' + n)
        }
    }
}
</script>

<style>
    .calculator {
        height: 320px;
        width: 235px;
        border-radius: 5px;
        overflow: hidden;


        display: grid;
        grid-template-columns: repeat(4, 25%);
        grid-template-rows: 1fr 48px 48px 48px 48px 48px;
    }
</style>