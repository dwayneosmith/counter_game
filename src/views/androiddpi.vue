<template lang="html">
  <div class="">
    <select v-model="selected">
  <option disabled value="">Please select one</option>
  <option value="inches">Convert from inches</option>
  <option value="dp">Convert from DP</option>
  <option value="sp">Convert from SP</option>
  <option value="px">Convert from px</option>
  <option value="mm">Convert from mm</option>
  <option value="pt">Convert from PT</option>
</select>

    <div v-if="selected === 'inches'" style="height: 290px;"><br>
      Inches:
    <input type="number" v-model="text_value" style="width: 50%" v-on:change="changed" placeholder="Counter start value"/><br><br>
    <p>DP</p>
    <input type="number" v-model="dp" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>SP</p>
    <input type="number" v-model="sp" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PX</p>
    <input type="number" v-model="px" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>MM</p>
    <input type="number" v-model="mm" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PT</p>
    <input type="number" v-model="pt" style="width: 50%" placeholder="Counter start value"/><br><br>
    </div>

    <div v-if="selected === 'dp'" style="height: 290px;"><br>
      Inches:
    <input type="number" v-model="text_value1" style="width: 50%" v-on:change="changed1" placeholder="Counter start value"/><br><br>
    <p>Inches</p>
    <input type="number" v-model="inches1" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>SP</p>
    <input type="number" v-model="sp1" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PX</p>
    <input type="number" v-model="px1" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>MM</p>
    <input type="number" v-model="mm1" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PT</p>
    <input type="number" v-model="pt1" style="width: 50%" placeholder="Counter start value"/><br><br>
    </div>

    <div v-if="selected === 'sp'" style="height: 290px;"><br>
      Inches:
    <input type="number" v-model="text_value2" style="width: 50%" v-on:change="changed2" placeholder="Counter start value"/><br><br>
    <p>Inches</p>
    <input type="number" v-model="inches2" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>SP</p>
    <input type="number" v-model="dp2" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PX</p>
    <input type="number" v-model="px2" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>MM</p>
    <input type="number" v-model="mm2" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PT</p>
    <input type="number" v-model="pt2" style="width: 50%" placeholder="Counter start value"/><br><br>
    </div>

    <div v-if="selected === 'px'" style="height: 290px;"><br>
      Inches:
    <input type="number" v-model="text_value3" style="width: 50%" v-on:change="changed3" placeholder="Counter start value"/><br><br>
    <p>Inches</p>
    <input type="number" v-model="inches3" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>SP</p>
    <input type="number" v-model="dp3" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PX</p>
    <input type="number" v-model="sp3" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>MM</p>
    <input type="number" v-model="mm3" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PT</p>
    <input type="number" v-model="pt3" style="width: 50%" placeholder="Counter start value"/><br><br>
    </div>

    <div v-if="selected === 'mm'" style="height: 290px;"><br>
      Inches:
    <input type="number" v-model="text_value4" style="width: 50%" v-on:change="changed4" placeholder="Counter start value"/><br><br>
    <p>Inches</p>
    <input type="number" v-model="inches4" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>SP</p>
    <input type="number" v-model="dp4" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PX</p>
    <input type="number" v-model="sp4" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>MM</p>
    <input type="number" v-model="px4" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PT</p>
    <input type="number" v-model="pt4" style="width: 50%" placeholder="Counter start value"/><br><br>
    </div>

    <div v-if="selected === 'pt'" style="height: 290px;"><br>
      Inches:
    <input type="number" v-model="text_value5" style="width: 50%" v-on:change="changed5" placeholder="Counter start value"/><br><br>
    <p>Inches</p>
    <input type="number" v-model="inches5" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>SP</p>
    <input type="number" v-model="dp5" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PX</p>
    <input type="number" v-model="sp5" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>MM</p>
    <input type="number" v-model="px5" style="width: 50%" placeholder="Counter start value"/><br><br>
    <p>PT</p>
    <input type="number" v-model="mm5" style="width: 50%" placeholder="Counter start value"/><br><br>
    </div>
  </div>
</template>

<script>
export default {
data(){
  return{
    text_value: 1,
    dp: null,
    sp: null,
    px: null,
    mm: null,
    pt: null,
    selected: '',
    text_value1: 1,
    inches1: null,
    sp1: null,
    px1: null,
    mm1: null,
    pt1: null,
    text_value3: 1,
    inches3: null,
    dp3: null,
    sp3: null,
    mm3: null,
    pt3: null,
    text_value4: 1,
    inches4: null,
    dp4: null,
    sp4: null,
    px4: null,
    pt4: null,
    text_value5: 1,
    inches5: null,
    dp5: null,
    sp5: null,
    px5: null,
    pt5: null
  }
},
computed: {
    parsedInput () {
        return this.text_value;
    },
    parsedInput1(){
      return this.text_value1;
    },
    parsedInput2(){
      return this.text_value2;
    },
    parsedInput3(){
      return this.text_value3;
    },
    parsedInput4(){
      return this.text_value4;
    },
    parsedInput5(){
      return this.text_value5;
    }
},
methods: {
  changed(){
    this.dp = this.text_value * 160.000;
    this.sp = this.text_value * 160;
    this.px = this.text_value * 160;
    this.mm = this.text_value * 25.400;
    this.pt = this.text_value * 72;
  },
  changed1(){
    this.inches1 = this.text_value1 * 0.006;
    this.sp1 = this.text_value1 * 1;
    this.px1 = this.text_value1 * 1;
    this.mm1 = this.text_value1 * 0.159;
    this.pt1 = this.text_value1 * 0.5;
  },
  changed2(){
    this.inches2 = this.text_value2 * 0.006;
    this.dp2 = this.text_value2 * 1;
    this.px2 = this.text_value2 * 1;
    this.mm2 = this.text_value2 * 0.159;
    this.pt2 = this.text_value2 * 0.5;
  },
  changed3(){
    this.inches3 = this.text_value3 * 0.008;
    this.dp3 = this.text_value3 * 1.333;
    this.sp3 = this.text_value3 * 1;
    this.mm3 = this.text_value3 * 0.212;
    this.pt3 = this.text_value3 * 1;
  },
  changed4(){
    this.inches4 = this.text_value4 * 0.039;
    this.dp4 = this.text_value4 * 6.299;
    this.sp4 = this.text_value4 * 6;
    this.px4 = this.text_value4 * 5;
    this.pt4 = this.text_value4 * 3;
  },
  changed5(){
    this.inches5 = this.text_value5 * 0.014;
    this.dp5 = this.text_value5 * 2.222;
    this.sp5 = this.text_value5 * 2;
    this.px5 = this.text_value5 * 2;
    this.mm5 = this.text_value5 * 0.353;
  }
},
watch: {
    parsedInput() {
        this.changed()
    },
    parsedInput1() {
      this.changed1()
    },
    parsedInput2() {
      this.changed2()
    },
    parsedInput3() {
      this.changed3()
    },
    parsedInput4() {
      this.changed4()
    },
    parsedInput5() {
      this.changed5()
    }
}

}
</script>

<style lang="css" scoped>
</style>
