<template>
  <div class="about">
    <div class="w3-twothird w3-container">
    <h1 class="w3-text-teal">Number Counter</h1><br>
    <button v-on:click="addcounter()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">Add Counter</button>
      <p>Counter starts with zero or you can start the counter by replacing zero with any other number.</p>
    <div class="w3-hover-shadow w3-panel w3-leftbar w3-light-grey" style="height: 290px;"><br>

    <input type="text" v-model="text_value" style="width: 100%" class="w3-border w3-padding-large w3-padding-32 w3-center" placeholder="Counter start value"/><br><br>
    <button v-on:click="plus1()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 1</button>
    <button v-on:click="plus2()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 2</button>
    <button v-on:click="plus3()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 3</button>
    <button v-on:click="plus4()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 4</button>
    <button v-on:click="plus5()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 5</button>
    <button v-on:click="plus6()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 6</button>
    <button v-on:click="plus7()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 7</button>
    <button v-on:click="plus8()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 8</button>
    <button v-on:click="plus9()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 9</button>
    <button v-on:click="reset()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">Reset</button><br><br>
    </div>

    <div v-if="firstcounter === 1" class="w3-hover-shadow w3-panel w3-leftbar w3-light-grey" style="height: 375px;"><br>
    <button v-on:click="removefirst()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">Remove this counter</button><br>
    <p></p>
    <input type="text" v-model="text_value1" style="width: 100%" class="w3-border w3-padding-large w3-padding-32 w3-center" placeholder="Counter start value"/><br><br>
    <button v-on:click="firstplus1()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 1</button>
    <button v-on:click="firstplus2()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 2</button>
    <button v-on:click="firstplus3()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 3</button>
    <button v-on:click="firstplus4()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 4</button>
    <button v-on:click="firstplus5()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 5</button>
    <button v-on:click="firstplus6()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 6</button>
    <button v-on:click="firstplus7()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 7</button>
    <button v-on:click="firstplus8()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 8</button>
    <button v-on:click="firstplus9()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 9</button>
    <button v-on:click="firstreset()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">Reset</button><br><br>
    </div>

    <div v-if="firstcounter1 === 1" class="w3-hover-shadow w3-panel w3-leftbar w3-light-grey" style="height: 376px;"><br>
    <button v-on:click="removefirst1()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">Remove this counter</button><br>
    <p></p>
    <input type="text" v-model="text_value2" style="width: 100%" class="w3-border w3-padding-large w3-padding-32 w3-center" placeholder="Counter start value"/><br><br>
    <button v-on:click="secondplus1()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 1</button>
    <button v-on:click="secondplus2()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 2</button>
    <button v-on:click="secondplus3()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 3</button>
    <button v-on:click="secondplus4()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 4</button>
    <button v-on:click="secondplus5()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 5</button>
    <button v-on:click="secondplus6()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 6</button>
    <button v-on:click="secondplus7()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 7</button>
    <button v-on:click="secondplus8()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 8</button>
    <button v-on:click="secondplus9()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">+ 9</button>
    <button v-on:click="secondreset()" class="w3-button w3-border w3-teal w3-padding-large w3-hover-gray" style="display: inline-block">Reset</button><br><br>
    </div>
</div>
  </div>
</template>
<script type="text/javascript">

  export default {
    data(){
      return {
        text_value: 0,
        firstcounter: 0,
        text_value1: 0,
        firstcounter1: 0,
        text_value2: 0
      }
    },
    methods: {
      addcounter(){
        if(this.firstcounter === 0){
        this.firstcounter = 1;
        this.text_value1 = 0;
      }
      else if(this.firstcounter === 1){
        this.firstcounter1 = 1;
        this.text_value2 = 0;
      }
      else{
        alert("cannot")
      }
      },
      plus1(){
        var x = parseInt(this.text_value);
        this.text_value = x + 1;
      },
      plus2(){
        var y = parseInt(this.text_value);
        this.text_value = y + 2;
      },
      plus3(){
        var z = parseInt(this.text_value);
        this.text_value = z + 3;
      },
      plus4(){
        var a = parseInt(this.text_value);
        this.text_value = a + 4;
      },
      plus5(){
        var b = parseInt(this.text_value);
        this.text_value = b + 5;
      },
      plus6(){
        var c = parseInt(this.text_value);
        this.text_value = c + 6;
      },
      plus7(){
        var d = parseInt(this.text_value);
        this.text_value = d + 7;
      },
      plus8(){
        var e = parseInt(this.text_value);
        this.text_value = e + 8;
      },
      plus9(){
        var f = parseInt(this.text_value);
        this.text_value = f + 9;
      },
      reset(){
        this.text_value = 0;
      },
      firstplus1(){
        var x = parseInt(this.text_value1);
        this.text_value1 = x + 1;
      },
      firstplus2(){
        var y = parseInt(this.text_value1);
        this.text_value1 = y + 2;
      },
      firstplus3(){
        var z = parseInt(this.text_value1);
        this.text_value1 = z + 3;
      },
      firstplus4(){
        var a = parseInt(this.text_value1);
        this.text_value1 = a + 4;
      },
      firstplus5(){
        var b = parseInt(this.text_value1);
        this.text_value1 = b + 5;
      },
      firstplus6(){
        var c = parseInt(this.text_value1);
        this.text_value1 = c + 6;
      },
      firstplus7(){
        var d = parseInt(this.text_value1);
        this.text_value1 = d + 7;
      },
      firstplus8(){
        var e = parseInt(this.text_value1);
        this.text_value1 = e + 8;
      },
      firstplus9(){
        var f = parseInt(this.text_value1);
        this.text_value1 = f + 9;
      },
      firstreset(){
        this.text_value1 = 0;
      },
      secondplus1(){
        var x = parseInt(this.text_value2);
        this.text_value2 = x + 1;
      },
      secondplus2(){
        var y = parseInt(this.text_value2);
        this.text_value2 = y + 2;
      },
      secondplus3(){
        var z = parseInt(this.text_value2);
        this.text_value2 = z + 3;
      },
      secondplus4(){
        var a = parseInt(this.text_value2);
        this.text_value2 = a + 4;
      },
      secondplus5(){
        var b = parseInt(this.text_value2);
        this.text_value2 = b + 5;
      },
      secondplus6(){
        var c = parseInt(this.text_value2);
        this.text_value2 = c + 6;
      },
      secondplus7(){
        var d = parseInt(this.text_value2);
        this.text_value2 = d + 7;
      },
      secondplus8(){
        var e = parseInt(this.text_value2);
        this.text_value2 = e + 8;
      },
      secondplus9(){
        var f = parseInt(this.text_value2);
        this.text_value2 = f + 9;
      },
      secondreset(){
        this.text_value2 = 0;
      },
      removefirst(){
        this.firstcounter = 0;
      },
      removefirst1(){
        this.firstcounter1 = 0;
      }
    }
  }
</script>
