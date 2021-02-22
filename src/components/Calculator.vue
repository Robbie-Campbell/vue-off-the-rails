<template>
      <div class="calculator card">

    <input type="text" id="screen" class="calculator-screen z-depth-1" value="" disabled />

    <div class="calculator-keys">

      <button type="button" v-on:click="operationType('+')" class="operator btn btn-info" value="+">+</button>
      <button type="button" v-on:click="operationType('-')" class="operator btn btn-info" value="-">-</button>
      <button type="button" v-on:click="operationType('*')" class="operator btn btn-info" value="*">&times;</button>
      <button type="button" v-on:click="operationType('/')" class="operator btn btn-info" value="/">&divide;</button>

      <button type="button" value="7" v-on:click="selectNumber('7')" class="btn btn-light waves-effect">7</button>
      <button type="button" value="8" v-on:click="selectNumber('8')" class="btn btn-light waves-effect">8</button>
      <button type="button" value="9" v-on:click="selectNumber('9')" class="btn btn-light waves-effect">9</button>


      <button type="button" value="4" v-on:click="selectNumber('4')" class="btn btn-light waves-effect">4</button>
      <button type="button" value="5" v-on:click="selectNumber('5')" class="btn btn-light waves-effect">5</button>
      <button type="button" value="6" v-on:click="selectNumber('6')" class="btn btn-light waves-effect">6</button>


      <button type="button" value="1" v-on:click="selectNumber('1')" class="btn btn-light waves-effect">1</button>
      <button type="button" value="2" v-on:click="selectNumber('2')" class="btn btn-light waves-effect">2</button>
      <button type="button" value="3" v-on:click="selectNumber('3')" class="btn btn-light waves-effect">3</button>


      <button type="button" v-on:click="selectNumber('0')" value="0" class="btn btn-light waves-effect">0</button>
      <button type="button" v-on:click="selectNumber('.')" class="decimal function btn btn-secondary" value=".">.</button>
      <button type="button" v-on:click="clearNum" class="all-clear function btn btn-danger btn-sm" value="all-clear">AC</button>

      <button type="button" v-on:click="calculate" class="equal-sign operator btn btn-default" value="=">=</button>

    </div>
  </div>
</template>

<script>
export default {
    name: 'Calculator',
    methods : {
        selectNumber(val){
            document.getElementById('screen').value += val;
        },
        clearNum(){
            document.getElementById('screen').value = '';
        },

        operationType(val){
            this.number = parseFloat(document.getElementById('screen').value);
            this.operation = val;
            this.clearNum();
        },

        calculate()
        {
            switch(this.operation)
            {
                case '*':
                    document.getElementById('screen').value = this.number * parseFloat(document.getElementById('screen').value);
                    break;
                case '/':
                    document.getElementById('screen').value = this.number / parseFloat(document.getElementById('screen').value);
                    break;
                case '+':
                    document.getElementById('screen').value = this.number + parseFloat(document.getElementById('screen').value);
                    break;
                case '-':
                    document.getElementById('screen').value = this.number - parseFloat(document.getElementById('screen').value);
                    break;
                default:
                    document.getElementById('screen').value = '';
                    break;
            }
        }
    },
}
</script>

<style scoped>
     html {
      font-size: 62.5%;
      box-sizing: border-box;
    }

    *,
    *::before,
    *::after {
      margin: 0;
      padding: 0;
      box-sizing: inherit;
    }

    .calculator {
      border: 1px solid #ccc;
      border-radius: 5px;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 400px;
    }

    .calculator-screen {
      width: 100%;
      height: 80px;
      border: none;
      background-color: #252525;
      color: #fff;
      text-align: right;
      padding-right: 20px;
      padding-left: 10px;
      font-size: 4rem;
    }

    button {
      height: 60px;
      font-size: 2rem!important;
    }

    .equal-sign {
      height: 98%;
      grid-area: 2 / 4 / 6 / 5;
    }

    .calculator-keys {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      grid-gap: 20px;
      padding: 20px;
    }
</style>