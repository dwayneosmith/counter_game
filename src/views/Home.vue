<template>
  <div class="w3-light-grey">

<!-- Header -->
  <div class="w3-padding w3-col l6 m8">
    <div class="w3-container w3-red">
      <h2><i class="fa fa-spoon w3-margin-right"></i>Cooking Recipe Converter</h2>
    </div>
    <div class="w3-container w3-white w3-padding-16">
              <input class="w3-input w3-border" type="number" v-model="user_input" name="Adults" placeholder="Please Enter units" required><br>
        <div class="w3-row-padding" style="margin:0 -16px;">

          <div class="w3-half w3-margin-bottom">
            <label><i class="fa fa-calendar-o"></i> Convert from</label>
            <select class="w3-input w3-border" v-model="select1">
              <option value="1" unittype="volume">Cups (US)</option>
              <option value="2" unittype="volume">Cups (Metric)</option>
              <option value="3" unittype="volume">Cups (Imperial)</option>
              <option value="4" unittype="volume">Deciliters [dL]</option>
              <option value="5" unittype="volume">Fluid Ounces (UK) [fl oz]</option>
              <option value="6" unittype="volume">Gallons (UK) [gal]</option>
              <option value="7" unittype="volume">Gallons (US)</option>
<option value="8" unittype="weight">Grams [g]</option>
<option value="9" unittype="weight">Kilograms [kg]</option>
<option value="10" unittype="volume">Liters [L]</option>
<option value="11" unittype="volume">Milliliters [mL]</option>
<option value="12" unittype="weight">Ounces [oz]</option>
<option value="13" unittype="volume">Pints (UK) [pt]</option>
<option value="14" unittype="volume">Pints (US) [pt]</option>
<option value="15" unittype="weight">Pounds [lb]</option>
<option value="16" unittype="volume">Quarts (UK) [qt]</option>
<option value="17" unittype="volume">Quarts (US) [qt]</option>
<option value="18" unittype="volume">Tablespoons (US)</option>
<option value="19" unittype="volume">Tablespoons (Metric)</option>
<option value="20" unittype="volume">Tablespoons (Imperial)</option>
<option value="21" unittype="volume">Teaspoons (US)</option>
<option value="22" unittype="volume">Teaspoons (Metric)</option>
<option value="23" unittype="volume">Teaspoons (Imperial)</option>
<option value="24" unittype="volume">Fluid Ounces (UK) [fl oz]</option>
            </select>
          </div>
          <div class="w3-half">
            <label><i class="fa fa-calendar-o"></i> Convert to</label>
            <select class="w3-input w3-border" v-model="select2">
              <option value="1" unittype="volume">Cups (US)</option>
              <option value="2" unittype="volume">Cups (Metric)</option>
              <option value="3" unittype="volume">Cups (Imperial)</option>
              <option value="4" unittype="volume">Deciliters [dL]</option>
              <option value="5" unittype="volume">Fluid Ounces (UK) [fl oz]</option>
              <option value="6" unittype="volume">Gallons (UK) [gal]</option>
              <option value="7" unittype="volume">Gallons (US)</option>
<option value="8" unittype="weight">Grams [g]</option>
<option value="9" unittype="weight">Kilograms [kg]</option>
<option value="10" unittype="volume">Liters [L]</option>
<option value="11" unittype="volume">Milliliters [mL]</option>
<option value="12" unittype="weight">Ounces [oz]</option>
<option value="13" unittype="volume">Pints (UK) [pt]</option>
<option value="14" unittype="volume">Pints (US) [pt]</option>
<option value="15" unittype="weight">Pounds [lb]</option>
<option value="16" unittype="volume">Quarts (UK) [qt]</option>
<option value="17" unittype="volume">Quarts (US) [qt]</option>
<option value="18" unittype="volume">Tablespoons (US)</option>
<option value="19" unittype="volume">Tablespoons (Metric)</option>
<option value="20" unittype="volume">Tablespoons (Imperial)</option>
<option value="21" unittype="volume">Teaspoons (US)</option>
<option value="22" unittype="volume">Teaspoons (Metric)</option>
<option value="23" unittype="volume">Teaspoons (Imperial)</option>
<option value="24" unittype="volume">Fluid Ounces (UK) [fl oz]</option>
</select><br>
          </div>
          <select class="w3-input w3-border" v-model="select3" v-if="select1 === '8' || select2 === '8' || select1 === '9' || select2 === '9' || select2 === '12' || select2 === '15'">
            <option value="">-- List of Ingredients --</option>

<option value="1">Water (pure)</option>

<optgroup label="Flour">
<option value="2">All purpose flour</option>
<option value="3">Almond flour</option>
<option value="4">Bread flour</option>
<option value="5">Cake flour</option>
<option value="6">Pastry flour</option>
<option value="7">Whole wheat flour</option>
<option value="8">Baking powder</option>
<option value="9">Baking soda (bicarb)</option>
</optgroup>

<optgroup label="Sugars and sweeteners">
<option value="10">Brown sugar (packed)</option>
<option value="11">Granulated sugar</option>
<option value="12">Powdered sugar (unsift)</option>
<option value="13">Raw cane sugar</option>
<option value="14">Honey</option>
<option value="15">Maple syrup</option>
<option value="16">Stevia</option>
</optgroup>

<optgroup label="Fats and oils">
<option value="17">Butter</option>
<option value="18">Lard</option>
<option value="19">Margarine</option>
<option value="20">Coconut oil</option>
<option value="21">Olive oil</option>
<option value="22">Palm oil</option>
<option value="23">Rapeseed oil</option>
<option value="24">Sunflower oil</option>
</optgroup>

<optgroup label="Milk and cream">
<option value="25">Milk</option>
<option value="26">Milk (condensed)</option>
<option value="27">Milk (evaporated)</option>
<option value="28">Light cream</option>
<option value="29">Heavy cream</option>
<option value="30">Whipped cream</option>
<option value="31">Yogurt (Greek)</option>
</optgroup>

<optgroup label="Nuts and seeds">
<option value="32">Almonds</option>
<option value="33">Cashew nuts</option>
<option value="34">Peanuts, not shelled</option>
<option value="35">Peanuts, shelled</option>
<option value="36">Pecan nuts</option>
<option value="37">Sunflower seeds</option>
<option value="38">Walnuts</option>
</optgroup>

<optgroup label="Fruit and veg">
<option value="39">Apples</option>
<option value="40">Avocado (cubes)</option>
<option value="41">Avocado (pureed)</option>
<option value="42">Corn, grits</option>
<option value="43">Corn, on the cob</option>
<option value="44">Corn, shelled</option>
<option value="45">Potatoes (white)</option>
</optgroup>

<optgroup label="Other ingredients">

<option value="46">Alcohol, pure (ethanol)</option>
<option value="47">Bran</option>
<option value="48">Breadcrumbs</option>
<option value="49">Chocolate (grated)</option>
<option value="50">Chocolate chips</option>
<option value="51">Cinnamon</option>
<option value="52">Cocoa powder</option>
<option value="53">Coconut, shredded</option>
<option value="54">Cumin (powdered)</option>
<option value="55">Currants (dried)</option>
<option value="56">Dried fruits</option>
<option value="57">Fruit juice</option>
<option value="58">Jam</option>
<option value="59">Mascarpone</option>
<option value="60">Mayonnaise</option>
<option value="61">Oats</option>
<option value="62">Oats, rolled</option>
<option value="63">Peanut butter</option>
<option value="64">Rice (hulled)</option>
<option value="65">Rice (rough)</option>
<option value="66">Ricotta cheese</option>
<option value="67">Rye</option>
<option value="68">Salt, fine</option>
<option value="69">Turmeric</option>
<option value="70">Yeast</option>
<option value="71">Yogurt (plain)</option>
</optgroup>
</select><br>

        </div>
        <button class="w3-button w3-dark-grey" @click="first();"><i class="fa fa-search w3-margin-right"></i> Convert Values</button>
        <div class="w3-row-padding" style="margin:8px -16px;">
          <div class="w3-full w3-margin-bottom">
            <label><i class="fa fa-commenting"></i> Conversion</label><br>
            <input class="w3-input w3-border" v-model="answer" placeholder="answer">
          </div>
          </div>
    </div>
  </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {
  },
  data(){
    return {
      answer: '',
      user_input: '',
      select1: '',
      select2: '',
      conversion: '',
      cupmetricintocupimperial: 0.88,
      select3: ''
    }
  },
  methods:{
    first(){
      if(this.user_input === '' || this.select1 === '' || this.select2 === ''){
        alert("please enter required fields");
          }
          else {
            if(this.select1 === '1' && this.select2 === '2')
            {
              this.answer = this.user_input * 0.95;
            }
            else if(this.select1 === '1' && this.select2 === '3')
            {
              this.answer = this.user_input * 0.83;
            }
            else if(this.select1 === '1' && this.select2 === '4')
            {
              this.answer = this.user_input * 2.37 + 'dL';
            }
            else if(this.select1 === '1' && this.select2 === '5')
            {
              this.answer = this.user_input * 8.33 + 'fl oz';
            }
            else if(this.select1 === '1' && this.select2 === '6')
            {
              this.answer = this.user_input * 8 + 'fl oz';
            }
            else if(this.select1 === '1' && this.select2 === '7')
            {
              this.answer = this.user_input * 0.05 + 'gal';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '1')
            {
              this.answer = this.user_input * 236.59 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '2')
            {
              this.answer = this.user_input * 125.16 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '3')
            {
              this.answer = this.user_input * 96.05 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '4')
            {
              this.answer = this.user_input * 130.12 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '5')
            {
              this.answer = this.user_input * 114.04 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '6')
            {
              this.answer = this.user_input * 105.99 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '7')
            {
              this.answer = this.user_input * 113.09 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '8')
            {
              this.answer = this.user_input * 212.93 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '9')
            {
              this.answer = this.user_input * 163.01 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '10')
            {
              this.answer = this.user_input * 194.71 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '11')
            {
              this.answer = this.user_input * 200.86 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '12')
            {
              this.answer = this.user_input * 120.09 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '13')
            {
              this.answer = this.user_input * 227.36 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '14')
            {
              this.answer = this.user_input * 335.96 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '15')
            {
              this.answer = this.user_input * 312.3 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '16')
            {
              this.answer = this.user_input * 104.81 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '17')
            {
              this.answer = this.user_input * 226.89 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '18')
            {
              this.answer = this.user_input * 217.42 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '19')
            {
              this.answer = this.user_input * 230.2 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '20')
            {
              this.answer = this.user_input * 218.67 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '21')
            {
              this.answer = this.user_input * 217.66 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '22')
            {
              this.answer = this.user_input * 210.56 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '23')
            {
              this.answer = this.user_input * 217.66 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '24')
            {
              this.answer = this.user_input * 227.12 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '25')
            {
              this.answer = this.user_input * 244.87 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '26')
            {
              this.answer = this.user_input * 306 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '27')
            {
              this.answer = this.user_input * 251.99 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '28')
            {
              this.answer = this.user_input * 239.43 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '29')
            {
              this.answer = this.user_input * 235.17 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '30')
            {
              this.answer = this.user_input * 117.35 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '31')
            {
              this.answer = this.user_input * 227.12 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '32')
            {
              this.answer = this.user_input * 108.83 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '33')
            {
              this.answer = this.user_input * 118.29 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '34')
            {
              this.answer = this.user_input * 64.35 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '35')
            {
              this.answer = this.user_input * 151.65 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '36')
            {
              this.answer = this.user_input * 109.78 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '37')
            {
              this.answer = this.user_input * 146.68 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '38')
            {
              this.answer = this.user_input * 117 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '39')
            {
              this.answer = this.user_input * 151.65 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '40')
            {
              this.answer = this.user_input * 150 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '41')
            {
              this.answer = this.user_input * 230 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '42')
            {
              this.answer = this.user_input * 159.22 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '43')
            {
              this.answer = this.user_input * 170.58 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '44')
            {
              this.answer = this.user_input * 170.58 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '45')
            {
              this.answer = this.user_input * 181.94 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '46')
            {
              this.answer = this.user_input * 186.67 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '47')
            {
              this.answer = this.user_input * 60.57 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '48')
            {
              this.answer = this.user_input * 106.46 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '49')
            {
              this.answer = this.user_input * 124.92 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '50')
            {
              this.answer = this.user_input * 170.34 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '51')
            {
              this.answer = this.user_input * 132.49 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '52')
            {
              this.answer = this.user_input * 151.65 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '53')
            {
              this.answer = this.user_input * 83.28 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '54')
            {
              this.answer = this.user_input * 134.86 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '55')
            {
              this.answer = this.user_input * 152.13 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '56')
            {
              this.answer = this.user_input * 169.07 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '57')
            {
              this.answer = this.user_input * 250.78 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '58')
            {
              this.answer = this.user_input * 315.37 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '59')
            {
              this.answer = this.user_input * 224 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '60')
            {
              this.answer = this.user_input * 215.3 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '61')
            {
              this.answer = this.user_input * 102.21 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '62')
            {
              this.answer = this.user_input * 71.92 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '63')
            {
              this.answer = this.user_input * 283.91 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '64')
            {
              this.answer = this.user_input * 178.15 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '65')
            {
              this.answer = this.user_input * 136.51 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '66')
            {
              this.answer = this.user_input * 257.88 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '67')
            {
              this.answer = this.user_input * 166.79 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '68')
            {
              this.answer = this.user_input * 284.14 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '69')
            {
              this.answer = this.user_input * 151.42 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '70')
            {
              this.answer = this.user_input * 224.76 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '8' && this.select3 === '71')
            {
              this.answer = this.user_input * 250.78 + 'g';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '1')
            {
              this.answer = this.user_input * 0.24 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '2')
            {
              this.answer = this.user_input * 0.13 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '3')
            {
              this.answer = this.user_input * 0.1 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '4')
            {
              this.answer = this.user_input * 0.13 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '5')
            {
              this.answer = this.user_input * 0.11 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '6')
            {
              this.answer = this.user_input * 0.11 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '7')
            {
              this.answer = this.user_input * 0.11 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '8')
            {
              this.answer = this.user_input * 0.21 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '9')
            {
              this.answer = this.user_input * 0.16 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '10')
            {
              this.answer = this.user_input * 0.19 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '11')
            {
              this.answer = this.user_input * 0.2 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '12')
            {
              this.answer = this.user_input * 0.12 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '13')
            {
              this.answer = this.user_input * 0.23 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '14')
            {
              this.answer = this.user_input * 0.34 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '15')
            {
              this.answer = this.user_input * 0.31 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '16')
            {
              this.answer = this.user_input * 0.1 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '17')
            {
              this.answer = this.user_input * 0.23 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '18')
            {
              this.answer = this.user_input * 0.22 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '19')
            {
              this.answer = this.user_input * 0.23 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '20')
            {
              this.answer = this.user_input * 0.22 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '21')
            {
              this.answer = this.user_input * 0.22 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '22')
            {
              this.answer = this.user_input * 0.21 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '23')
            {
              this.answer = this.user_input * 0.22 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '24')
            {
              this.answer = this.user_input * 0.23 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '25')
            {
              this.answer = this.user_input * 0.24 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '26')
            {
              this.answer = this.user_input * 0.31 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '27')
            {
              this.answer = this.user_input * 0.25 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '28')
            {
              this.answer = this.user_input * 0.24 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '29')
            {
              this.answer = this.user_input * 0.24 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '30')
            {
              this.answer = this.user_input * 0.12 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '31')
            {
              this.answer = this.user_input * 0.23 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '32')
            {
              this.answer = this.user_input * 0.11 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '33')
            {
              this.answer = this.user_input * 0.12 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '34')
            {
              this.answer = this.user_input * 0.06 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '35')
            {
              this.answer = this.user_input * 0.15 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '36')
            {
              this.answer = this.user_input * 0.11 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '37')
            {
              this.answer = this.user_input * 0.15 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '38')
            {
              this.answer = this.user_input * 0.12 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '39')
            {
              this.answer = this.user_input * 0.15 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '40')
            {
              this.answer = this.user_input * 0.15 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '41')
            {
              this.answer = this.user_input * 0.23 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '42')
            {
              this.answer = this.user_input * 0.16 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '43')
            {
              this.answer = this.user_input * 0.17 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '44')
            {
              this.answer = this.user_input * 0.17 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '45')
            {
              this.answer = this.user_input * 0.18 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '46')
            {
              this.answer = this.user_input * 0.19 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '47')
            {
              this.answer = this.user_input * 0.06 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '48')
            {
              this.answer = this.user_input * 0.11 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '49')
            {
              this.answer = this.user_input * 0.12 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '50')
            {
              this.answer = this.user_input * 0.17 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '51')
            {
              this.answer = this.user_input * 0.13 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '52')
            {
              this.answer = this.user_input * 0.15 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '53')
            {
              this.answer = this.user_input * 0.08 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '54')
            {
              this.answer = this.user_input * 0.13 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '55')
            {
              this.answer = this.user_input * 0.15 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '56')
            {
              this.answer = this.user_input * 0.17 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '57')
            {
              this.answer = this.user_input * 0.25 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '58')
            {
              this.answer = this.user_input * 0.32 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '59')
            {
              this.answer = this.user_input * 0.22 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '60')
            {
              this.answer = this.user_input * 0.22 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '61')
            {
              this.answer = this.user_input * 0.1 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '62')
            {
              this.answer = this.user_input * 0.07 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '63')
            {
              this.answer = this.user_input * 0.28 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '64')
            {
              this.answer = this.user_input * 0.18 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '65')
            {
              this.answer = this.user_input * 0.14 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '66')
            {
              this.answer = this.user_input * 0.26 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '67')
            {
              this.answer = this.user_input * 0.17 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '68')
            {
              this.answer = this.user_input * 0.28 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '69')
            {
              this.answer = this.user_input * 0.15 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '70')
            {
              this.answer = this.user_input * 0.22 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '9' && this.select3 === '71')
            {
              this.answer = this.user_input * 0.25 + 'kg';
            }
            else if(this.select1 === '1' && this.select2 === '10')
            {
              this.answer = this.user_input * 0.24 + 'L';
            }
            else if(this.select1 === '1' && this.select2 === '11')
            {
              this.answer = this.user_input * 236.59 + 'mL';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '1'){
              this.answer = this.user_input * 8.35 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '2'){
              this.answer = this.user_input * 4.41 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '3'){
              this.answer = this.user_input * 3.39 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '4'){
              this.answer = this.user_input * 4.59 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '5'){
              this.answer = this.user_input * 4.02 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '6'){
              this.answer = this.user_input * 3.74 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '7'){
              this.answer = this.user_input * 3.99 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '8'){
              this.answer = this.user_input * 7.51 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '9'){
              this.answer = this.user_input * 5.75 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '10'){
              this.answer = this.user_input * 6.87 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '11'){
              this.answer = this.user_input * 7.09 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '12'){
              this.answer = this.user_input * 4.26 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '13'){
              this.answer = this.user_input * 8.02 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '14'){
              this.answer = this.user_input * 11.85 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '15'){
              this.answer = this.user_input * 11.02 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '16'){
              this.answer = this.user_input * 3.7 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '17'){
              this.answer = this.user_input * 8 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '18'){
              this.answer = this.user_input * 7.67 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '19'){
              this.answer = this.user_input * 8.12 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '20'){
              this.answer = this.user_input * 7.71 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '21'){
              this.answer = this.user_input * 7.68 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '22'){
              this.answer = this.user_input * 7.43 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '23'){
              this.answer = this.user_input * 7.68 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '24'){
              this.answer = this.user_input * 8.01 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '25'){
              this.answer = this.user_input * 8.64 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '26'){
              this.answer = this.user_input * 10.79 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '27'){
              this.answer = this.user_input * 8.89 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '28'){
              this.answer = this.user_input * 8.45 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '29'){
              this.answer = this.user_input * 8.3 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '30'){
              this.answer = this.user_input * 4.14 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '31'){
              this.answer = this.user_input * 8.01 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '32'){
              this.answer = this.user_input * 3.84 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '33'){
              this.answer = this.user_input * 4.17 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '34'){
              this.answer = this.user_input * 2.27 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '35'){
              this.answer = this.user_input * 5.35 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '36'){
              this.answer = this.user_input * 3.87 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '37'){
              this.answer = this.user_input * 5.17 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '38'){
              this.answer = this.user_input * 4.13 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '39'){
              this.answer = this.user_input * 5.35 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '40'){
              this.answer = this.user_input * 5.29 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '41'){
              this.answer = this.user_input * 8.11 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '42'){
              this.answer = this.user_input * 5.62 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '43'){
              this.answer = this.user_input * 6.02 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '44'){
              this.answer = this.user_input * 6.02 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '45'){
              this.answer = this.user_input * 6.42 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '46'){
              this.answer = this.user_input * 6.58 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '47'){
              this.answer = this.user_input * 2.14 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '48'){
              this.answer = this.user_input * 3.76 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '49'){
              this.answer = this.user_input * 4.41 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '50'){
              this.answer = this.user_input * 6.01 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '51'){
              this.answer = this.user_input * 4.67 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '52'){
              this.answer = this.user_input * 5.35 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '53'){
              this.answer = this.user_input * 2.94 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '54'){
              this.answer = this.user_input * 4.76 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '55'){
              this.answer = this.user_input * 5.37 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '56'){
              this.answer = this.user_input * 5.96 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '57'){
              this.answer = this.user_input * 8.85 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '58'){
              this.answer = this.user_input * 11.12 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '59'){
              this.answer = this.user_input * 7.9 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '60'){
              this.answer = this.user_input * 7.59 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '61'){
              this.answer = this.user_input * 3.61 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '62'){
              this.answer = this.user_input * 2.54 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '63'){
              this.answer = this.user_input * 10.01 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '64'){
              this.answer = this.user_input * 6.28 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '65'){
              this.answer = this.user_input * 4.82 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '66'){
              this.answer = this.user_input * 9.1 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '67'){
              this.answer = this.user_input * 5.88 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '68'){
              this.answer = this.user_input * 10.02 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '69'){
              this.answer = this.user_input * 5.34 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '70'){
              this.answer = this.user_input * 7.93 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '12' && this.select3 === '71'){
              this.answer = this.user_input * 8.85 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '13'){
              this.answer = this.user_input * 0.42 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '14'){
              this.answer = this.user_input * 0.5 + 'oz';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '1'){
              this.answer = this.user_input * 0.52 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '2'){
              this.answer = this.user_input * 0.28 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '3'){
              this.answer = this.user_input * 0.21 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '4'){
              this.answer = this.user_input * 0.29 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '5'){
              this.answer = this.user_input * 0.25 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '6'){
              this.answer = this.user_input * 0.23 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '7'){
              this.answer = this.user_input * 0.25 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '8'){
              this.answer = this.user_input * 0.47 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '9'){
              this.answer = this.user_input * 0.36 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '10'){
              this.answer = this.user_input * 0.43 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '11'){
              this.answer = this.user_input * 0.44 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '12'){
              this.answer = this.user_input * 0.27 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '13'){
              this.answer = this.user_input * 0.5 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '14'){
              this.answer = this.user_input * 0.74 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '15'){
              this.answer = this.user_input * 0.69 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '16'){
              this.answer = this.user_input * 0.23 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '17'){
              this.answer = this.user_input * 0.5 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '18'){
              this.answer = this.user_input * 0.48 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '19'){
              this.answer = this.user_input * 0.51 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '20'){
              this.answer = this.user_input * 0.48 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '21'){
              this.answer = this.user_input * 0.48 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '22'){
              this.answer = this.user_input * 0.46 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '23'){
              this.answer = this.user_input * 0.48 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '24'){
              this.answer = this.user_input * 0.5 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '25'){
              this.answer = this.user_input * 0.54 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '26'){
              this.answer = this.user_input * 0.67 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '27'){
              this.answer = this.user_input * 0.56 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '28'){
              this.answer = this.user_input * 0.53 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '29'){
              this.answer = this.user_input * 0.52 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '30'){
              this.answer = this.user_input * 0.26 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '31'){
              this.answer = this.user_input * 0.5 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '32'){
              this.answer = this.user_input * 0.24 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '33'){
              this.answer = this.user_input * 0.26 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '34'){
              this.answer = this.user_input * 0.14 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '35'){
              this.answer = this.user_input * 0.33 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '36'){
              this.answer = this.user_input * 0.24 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '37'){
              this.answer = this.user_input * 0.32 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '38'){
              this.answer = this.user_input * 0.26 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '39'){
              this.answer = this.user_input * 0.33 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '40'){
              this.answer = this.user_input * 0.33 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '41'){
              this.answer = this.user_input * 0.51 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '42'){
              this.answer = this.user_input * 0.35 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '43'){
              this.answer = this.user_input * 0.38 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '44'){
              this.answer = this.user_input * 0.38 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '45'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '46'){
              this.answer = this.user_input * 0.41 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '47'){
              this.answer = this.user_input * 0.13 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '48'){
              this.answer = this.user_input * 0.23 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '49'){
              this.answer = this.user_input * 0.28 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '50'){
              this.answer = this.user_input * 0.38 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '51'){
              this.answer = this.user_input * 0.29 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '52'){
              this.answer = this.user_input * 0.33 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '53'){
              this.answer = this.user_input * 0.18 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '54'){
              this.answer = this.user_input * 0.3 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '55'){
              this.answer = this.user_input * 0.34 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '56'){
              this.answer = this.user_input * 0.37 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '57'){
              this.answer = this.user_input * 0.55 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '58'){
              this.answer = this.user_input * 0.7 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '59'){
              this.answer = this.user_input * 0.49 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '60'){
              this.answer = this.user_input * 0.47 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '61'){
              this.answer = this.user_input * 0.23 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '62'){
              this.answer = this.user_input * 0.16 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '63'){
              this.answer = this.user_input * 0.63 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '64'){
              this.answer = this.user_input * 0.39 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '65'){
              this.answer = this.user_input * 0.3 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '66'){
              this.answer = this.user_input * 0.57 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '67'){
              this.answer = this.user_input * 0.37 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '68'){
              this.answer = this.user_input * 0.63 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '69'){
              this.answer = this.user_input * 0.33 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '70'){
              this.answer = this.user_input * 0.5 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '15' && this.select3 === '71'){
              this.answer = this.user_input * 0.55 + ' lb';
            }
            else if(this.select1 === '1' && this.select2 === '16'){
              this.answer = this.user_input * 0.21 + ' qt';
            }
            else if(this.select1 === '1' && this.select2 === '17'){
              this.answer = this.user_input * 0.25 + ' qt';
            }
            else if(this.select1 === '1' && this.select2 === '18'){
              this.answer = this.user_input * 16;
            }
            else if(this.select1 === '1' && this.select2 === '19'){
              this.answer = this.user_input * 15.77;
            }
            else if(this.select1 === '1' && this.select2 === '20'){
              this.answer = this.user_input * 13.32;
            }
            else if(this.select1 === '1' && this.select2 === '21'){
              this.answer = this.user_input * 48;
            }
            else if(this.select1 === '1' && this.select2 === '22'){
              this.answer = this.user_input * 47.32;
            }
            else if(this.select1 === '1' && this.select2 === '23'){
              this.answer = this.user_input * 39.97;
            }
            else if(this.select1 === '1' && this.select2 === '24'){
              this.answer = this.user_input * 8 + ' fl oz';
            }
            else if(this.select1 === '2' && this.select2 === '1'){
              this.answer = this.user_input * 1.06;
            }
            else if(this.select1 === '2' && this.select2 === '3'){
              this.answer = this.user_input * 0.88;
            }
            else if(this.select1 === '2' && this.select2 === '4'){
              this.answer = this.user_input * 2.5 + ' dL';
            }
            else if(this.select1 === '2' && this.select2 === '5'){
              this.answer = this.user_input * 8.8 + ' fl oz';
            }
            else if(this.select1 === '2' && this.select2 === '6'){
              this.answer = this.user_input * 0.05 + ' gal';
            }
            else if(this.select1 === '2' && this.select2 === '7'){
              this.answer = this.user_input * 0.07 + ' gal';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '1'){
              this.answer = this.user_input * 250 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '2'){
              this.answer = this.user_input * 132.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '3'){
              this.answer = this.user_input * 101.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '4'){
              this.answer = this.user_input * 137.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '5'){
              this.answer = this.user_input * 120.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '6'){
              this.answer = this.user_input * 112 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '7'){
              this.answer = this.user_input * 119.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '8'){
              this.answer = this.user_input * 225 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '9'){
              this.answer = this.user_input * 172.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '10'){
              this.answer = this.user_input * 205.75 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '11'){
              this.answer = this.user_input * 212.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '12'){
              this.answer = this.user_input * 127.75 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '13'){
              this.answer = this.user_input * 240.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '14'){
              this.answer = this.user_input * 355 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '15'){
              this.answer = this.user_input * 330 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '16'){
              this.answer = this.user_input * 110.75 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '17'){
              this.answer = this.user_input * 239.75 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '18'){
              this.answer = this.user_input * 229.75 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '19'){
              this.answer = this.user_input * 243.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '20'){
              this.answer = this.user_input * 231.07 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '21'){
              this.answer = this.user_input * 230 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '22'){
              this.answer = this.user_input * 222.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '23'){
              this.answer = this.user_input * 230 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '24'){
              this.answer = this.user_input * 240 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '25'){
              this.answer = this.user_input * 258.75 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '26'){
              this.answer = this.user_input * 323.35 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '27'){
              this.answer = this.user_input * 266.28 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '28'){
              this.answer = this.user_input * 253 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '29'){
              this.answer = this.user_input * 248.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '30'){
              this.answer = this.user_input * 124 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '31'){
              this.answer = this.user_input * 240 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '32'){
              this.answer = this.user_input * 115 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '33'){
              this.answer = this.user_input * 125 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '34'){
              this.answer = this.user_input * 68 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '35'){
              this.answer = this.user_input * 160.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '36'){
              this.answer = this.user_input * 116 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '37'){
              this.answer = this.user_input * 155 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '38'){
              this.answer = this.user_input * 123.63 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '39'){
              this.answer = this.user_input * 160.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '40'){
              this.answer = this.user_input * 158.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '41'){
              this.answer = this.user_input * 243.04 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '42'){
              this.answer = this.user_input * 168.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '43'){
              this.answer = this.user_input * 180.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '44'){
              this.answer = this.user_input * 180.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '45'){
              this.answer = this.user_input * 192.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '46'){
              this.answer = this.user_input * 197.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '47'){
              this.answer = this.user_input * 64 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '48'){
              this.answer = this.user_input * 112.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '49'){
              this.answer = this.user_input * 132 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '50'){
              this.answer = this.user_input * 180 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '51'){
              this.answer = this.user_input * 140 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '52'){
              this.answer = this.user_input * 160.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '53'){
              this.answer = this.user_input * 88 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '54'){
              this.answer = this.user_input * 142.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '55'){
              this.answer = this.user_input * 160.75 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '56'){
              this.answer = this.user_input * 178.65 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '57'){
              this.answer = this.user_input * 265 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '58'){
              this.answer = this.user_input * 333.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '59'){
              this.answer = this.user_input * 236.7 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '60'){
              this.answer = this.user_input * 227.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '61'){
              this.answer = this.user_input * 108 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '62'){
              this.answer = this.user_input * 76 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '63'){
              this.answer = this.user_input * 300 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '64'){
              this.answer = this.user_input * 188.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '65'){
              this.answer = this.user_input * 144.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '66'){
              this.answer = this.user_input * 272.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '67'){
              this.answer = this.user_input * 176.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '68'){
              this.answer = this.user_input * 300.25 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '69'){
              this.answer = this.user_input * 160 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '70'){
              this.answer = this.user_input * 237.5 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '8' && this.select3 === '71'){
              this.answer = this.user_input * 265 + ' g';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '1'){
              this.answer = this.user_input * 0.25 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '2'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '3'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '4'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '5'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '6'){
              this.answer = this.user_input * 0.11 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '7'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '8'){
              this.answer = this.user_input * 0.23 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '9'){
              this.answer = this.user_input * 0.17 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '10'){
              this.answer = this.user_input * 0.21 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '11'){
              this.answer = this.user_input * 0.21 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '12'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '13'){
              this.answer = this.user_input * 0.24 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '14'){
              this.answer = this.user_input * 0.36 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '15'){
              this.answer = this.user_input * 0.33 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '16'){
              this.answer = this.user_input * 0.11 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '17'){
              this.answer = this.user_input * 0.24 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '18'){
              this.answer = this.user_input * 0.23 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '19'){
              this.answer = this.user_input * 0.24 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '20'){
              this.answer = this.user_input * 0.23 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '21'){
              this.answer = this.user_input * 0.23 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '22'){
              this.answer = this.user_input * 0.22 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '23'){
              this.answer = this.user_input * 0.23 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '24'){
              this.answer = this.user_input * 0.24 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '25'){
              this.answer = this.user_input * 0.26 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '26'){
              this.answer = this.user_input * 0.32 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '27'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '28'){
              this.answer = this.user_input * 0.25 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '29'){
              this.answer = this.user_input * 0.25 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '30'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '31'){
              this.answer = this.user_input * 0.24 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '32'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '33'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '34'){
              this.answer = this.user_input * 0.07 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '35'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '36'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '37'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '38'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '39'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '40'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '41'){
              this.answer = this.user_input * 0.24 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '42'){
              this.answer = this.user_input * 0.17 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '43'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '44'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '45'){
              this.answer = this.user_input * 0.19 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '46'){
              this.answer = this.user_input * 0.2 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '47'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '48'){
              this.answer = this.user_input * 0.11 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '49'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '50'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '51'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '52'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '53'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '54'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '55'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '56'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '57'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '58'){
              this.answer = this.user_input * 0.33 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '59'){
              this.answer = this.user_input * 0.24 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '60'){
              this.answer = this.user_input * 0.23 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '61'){
              this.answer = this.user_input * 0.11 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '62'){
              this.answer = this.user_input * 0.08 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '63'){
              this.answer = this.user_input * 0.3 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '64'){
              this.answer = this.user_input * 0.19 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '65'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '66'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '67'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '68'){
              this.answer = this.user_input * 0.3 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '69'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '70'){
              this.answer = this.user_input * 0.24 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '9' && this.select3 === '71'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '2' && this.select2 === '10'){
              this.answer = this.user_input * 0.25 + ' L';
            }
            else if(this.select1 === '2' && this.select2 === '11'){
              this.answer = this.user_input * 250 + ' ml';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '1'){
              this.answer = this.user_input * 8.82 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '2'){
              this.answer = this.user_input * 4.66 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '3'){
              this.answer = this.user_input * 3.58 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '4'){
              this.answer = this.user_input * 4.85 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '5'){
              this.answer = this.user_input * 4.25 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '6'){
              this.answer = this.user_input * 3.95 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '7'){
              this.answer = this.user_input * 4.22 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '8'){
              this.answer = this.user_input * 7.94 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '9'){
              this.answer = this.user_input * 6.08 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '10'){
              this.answer = this.user_input * 7.26 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '11'){
              this.answer = this.user_input * 7.49 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '12'){
              this.answer = this.user_input * 4.51 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '13'){
              this.answer = this.user_input * 8.47 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '14'){
              this.answer = this.user_input * 12.52 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '15'){
              this.answer = this.user_input * 11.64 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '16'){
              this.answer = this.user_input * 3.91 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '17'){
              this.answer = this.user_input * 8.46 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '18'){
              this.answer = this.user_input * 8.1 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '19'){
              this.answer = this.user_input * 8.58 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '20'){
              this.answer = this.user_input * 8.15 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '21'){
              this.answer = this.user_input * 8.11 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '22'){
              this.answer = this.user_input * 7.85 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '23'){
              this.answer = this.user_input * 8.11 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '24'){
              this.answer = this.user_input * 8.47 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '25'){
              this.answer = this.user_input * 9.13 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '26'){
              this.answer = this.user_input * 11.41 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '27'){
              this.answer = this.user_input * 9.39 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '28'){
              this.answer = this.user_input * 8.92 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '29'){
              this.answer = this.user_input * 8.77 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '30'){
              this.answer = this.user_input * 4.37 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '31'){
              this.answer = this.user_input * 8.47 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '32'){
              this.answer = this.user_input * 4.06 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '33'){
              this.answer = this.user_input * 4.41 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '34'){
              this.answer = this.user_input * 2.4 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '35'){
              this.answer = this.user_input * 5.65 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '36'){
              this.answer = this.user_input * 4.09 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '37'){
              this.answer = this.user_input * 5.47 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '38'){
              this.answer = this.user_input * 4.36 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '39'){
              this.answer = this.user_input * 5.65 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '40'){
              this.answer = this.user_input * 5.59 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '41'){
              this.answer = this.user_input * 8.57 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '42'){
              this.answer = this.user_input * 5.93 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '43'){
              this.answer = this.user_input * 6.36 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '44'){
              this.answer = this.user_input * 6.36 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '45'){
              this.answer = this.user_input * 6.78 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '46'){
              this.answer = this.user_input * 6.96 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '47'){
              this.answer = this.user_input * 2.26 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '48'){
              this.answer = this.user_input * 3.97 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '49'){
              this.answer = this.user_input * 4.66 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '50'){
              this.answer = this.user_input * 6.35 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '51'){
              this.answer = this.user_input * 4.94 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '52'){
              this.answer = this.user_input * 5.65 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '53'){
              this.answer = this.user_input * 3.1 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '54'){
              this.answer = this.user_input * 5.03 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '55'){
              this.answer = this.user_input * 5.67 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '56'){
              this.answer = this.user_input * 6.3 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '57'){
              this.answer = this.user_input * 9.35 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '58'){
              this.answer = this.user_input * 11.76 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '59'){
              this.answer = this.user_input * 8.35 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '60'){
              this.answer = this.user_input * 8.02 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '61'){
              this.answer = this.user_input * 3.81 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '62'){
              this.answer = this.user_input * 2.68 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '63'){
              this.answer = this.user_input * 10.58 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '64'){
              this.answer = this.user_input * 6.64 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '65'){
              this.answer = this.user_input * 5.09 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '66'){
              this.answer = this.user_input * 9.61 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '67'){
              this.answer = this.user_input * 6.22 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '68'){
              this.answer = this.user_input * 10.59 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '69'){
              this.answer = this.user_input * 5.64 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '70'){
              this.answer = this.user_input * 8.38 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '12' && this.select3 === '71'){
              this.answer = this.user_input * 9.35 + ' oz';
            }
            else if(this.select1 === '2' && this.select2 === '13'){
              this.answer = this.user_input * 0.44 + ' pt';
            }
            else if(this.select1 === '2' && this.select2 === '14'){
              this.answer = this.user_input * 0.53 + ' pt';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '1'){
              this.answer = this.user_input * 0.55 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '2'){
              this.answer = this.user_input * 0.29 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '3'){
              this.answer = this.user_input * 0.22 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '4'){
              this.answer = this.user_input * 0.3 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '5'){
              this.answer = this.user_input * 0.27 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '6'){
              this.answer = this.user_input * 0.25 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '7'){
              this.answer = this.user_input * 0.26 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '8'){
              this.answer = this.user_input * 0.5 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '9'){
              this.answer = this.user_input * 0.38 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '10'){
              this.answer = this.user_input * 0.45 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '11'){
              this.answer = this.user_input * 0.47 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '12'){
              this.answer = this.user_input * 0.28 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '13'){
              this.answer = this.user_input * 0.53 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '14'){
              this.answer = this.user_input * 0.78 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '15'){
              this.answer = this.user_input * 0.73 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '16'){
              this.answer = this.user_input * 0.24 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '17'){
              this.answer = this.user_input * 0.53 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '18'){
              this.answer = this.user_input * 0.51 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '19'){
              this.answer = this.user_input * 0.54 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '20'){
              this.answer = this.user_input * 0.51 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '21'){
              this.answer = this.user_input * 0.51 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '22'){
              this.answer = this.user_input * 0.49 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '23'){
              this.answer = this.user_input * 0.51 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '24'){
              this.answer = this.user_input * 0.53 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '25'){
              this.answer = this.user_input * 0.57 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '26'){
              this.answer = this.user_input * 0.71 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '27'){
              this.answer = this.user_input * 0.59 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '28'){
              this.answer = this.user_input * 0.56 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '29'){
              this.answer = this.user_input * 0.55 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '30'){
              this.answer = this.user_input * 0.27 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '31'){
              this.answer = this.user_input * 0.53 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '32'){
              this.answer = this.user_input * 0.25 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '33'){
              this.answer = this.user_input * 0.28 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '34'){
              this.answer = this.user_input * 0.15 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '35'){
              this.answer = this.user_input * 0.35 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '36'){
              this.answer = this.user_input * 0.26 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '37'){
              this.answer = this.user_input * 0.34 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '38'){
              this.answer = this.user_input * 0.27 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '39'){
              this.answer = this.user_input * 0.35 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '40'){
              this.answer = this.user_input * 0.35 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '41'){
              this.answer = this.user_input * 0.54 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '42'){
              this.answer = this.user_input * 0.37 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '43'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '44'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '45'){
              this.answer = this.user_input * 0.42 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '46'){
              this.answer = this.user_input * 0.43 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '47'){
              this.answer = this.user_input * 0.14 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '48'){
              this.answer = this.user_input * 0.25 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '49'){
              this.answer = this.user_input * 0.29 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '50'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '51'){
              this.answer = this.user_input * 0.31 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '52'){
              this.answer = this.user_input * 0.35 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '53'){
              this.answer = this.user_input * 0.19 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '54'){
              this.answer = this.user_input * 0.31 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '55'){
              this.answer = this.user_input * 0.35 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '56'){
              this.answer = this.user_input * 0.39 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '57'){
              this.answer = this.user_input * 0.58 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '58'){
              this.answer = this.user_input * 0.73 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '59'){
              this.answer = this.user_input * 0.52 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '60'){
              this.answer = this.user_input * 0.5 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '61'){
              this.answer = this.user_input * 0.24 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '62'){
              this.answer = this.user_input * 0.17 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '63'){
              this.answer = this.user_input * 0.66 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '64'){
              this.answer = this.user_input * 0.42 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '65'){
              this.answer = this.user_input * 0.32 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '66'){
              this.answer = this.user_input * 0.6 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '67'){
              this.answer = this.user_input * 0.39 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '68'){
              this.answer = this.user_input * 0.66 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '69'){
              this.answer = this.user_input * 0.35 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '70'){
              this.answer = this.user_input * 0.52 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '15' && this.select3 === '71'){
              this.answer = this.user_input * 0.58 + ' lb';
            }
            else if(this.select1 === '2' && this.select2 === '16'){
              this.answer = this.user_input * 0.22 + ' qt';
            }
            else if(this.select1 === '2' && this.select2 === '17'){
              this.answer = this.user_input * 0.26 + ' qt';
            }
            else if(this.select1 === '2' && this.select2 === '18'){
              this.answer = this.user_input * 16.91;
            }
            else if(this.select1 === '2' && this.select2 === '19'){
              this.answer = this.user_input * 16.67;
            }
            else if(this.select1 === '2' && this.select2 === '20'){
              this.answer = this.user_input * 14.08;
            }
            else if(this.select1 === '2' && this.select2 === '21'){
              this.answer = this.user_input * 50.72;
            }
            else if(this.select1 === '2' && this.select2 === '22'){
              this.answer = this.user_input * 50;
            }
            else if(this.select1 === '2' && this.select2 === '23'){
              this.answer = this.user_input * 42.23;
            }
            else if(this.select1 === '2' && this.select2 === '24'){
              this.answer = this.user_input * 8.45 + 'fl oz';
            }
            else if(this.select1 === '3' && this.select2 === '1'){
              this.answer = this.user_input * 1.2;
            }
            else if(this.select1 === '3' && this.select2 === '2'){
              this.answer = this.user_input * 1.14;
            }
            else if(this.select1 === '3' && this.select2 === '4'){
              this.answer = this.user_input * 2.84 + ' dL';
            }
            else if(this.select1 === '3' && this.select2 === '5'){
              this.answer = this.user_input * 10 + ' fl oz';
            }
            else if(this.select1 === '3' && this.select2 === '6'){
              this.answer = this.user_input * 0.06 + ' gal';
            }
            else if(this.select1 === '3' && this.select2 === '7'){
              this.answer = this.user_input * 0.08;
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '1'){
              this.answer = this.user_input * 284.13 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '2'){
              this.answer = this.user_input * 150.31 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '3'){
              this.answer = this.user_input * 115.36 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '4'){
              this.answer = this.user_input * 157.27 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '5'){
              this.answer = this.user_input * 136.95 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '6'){
              this.answer = this.user_input * 127.29 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '7'){
              this.answer = this.user_input * 135.81 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '8'){
              this.answer = this.user_input * 255.72 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '9'){
              this.answer = this.user_input * 195.77 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '10'){
              this.answer = this.user_input * 233.84 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '11'){
              this.answer = this.user_input * 241.23 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '12'){
              this.answer = this.user_input * 145.19 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '13'){
              this.answer = this.user_input * 273.05 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '14'){
              this.answer = this.user_input * 403.47 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '15'){
              this.answer = this.user_input * 375.05 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '16'){
              this.answer = this.user_input * 125.87 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '17'){
              this.answer = this.user_input * 272.48 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '18'){
              this.answer = this.user_input * 261.12 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '19'){
              this.answer = this.user_input * 276.46 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '20'){
              this.answer = this.user_input * 262.61 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '21'){
              this.answer = this.user_input * 261.4 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '22'){
              this.answer = this.user_input * 252.88 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '23'){
              this.answer = this.user_input * 262.4 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '24'){
              this.answer = this.user_input * 272.77 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '25'){
              this.answer = this.user_input * 294.08 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '26'){
              this.answer = this.user_input * 367.49 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '27'){
              this.answer = this.user_input * 302.63 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '28'){
              this.answer = this.user_input * 287.54 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '29'){
              this.answer = this.user_input * 282.43 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '30'){
              this.answer = this.user_input * 140.93 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '31'){
              this.answer = this.user_input * 272.77 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '32'){
              this.answer = this.user_input * 130.7 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '33'){
              this.answer = this.user_input * 142.07 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '34'){
              this.answer = this.user_input * 77.28 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '35'){
              this.answer = this.user_input * 182.13 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '36'){
              this.answer = this.user_input * 131.84 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '37'){
              this.answer = this.user_input * 176.16 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '38'){
              this.answer = this.user_input * 140.51 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '39'){
              this.answer = this.user_input * 182.13 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '40'){
              this.answer = this.user_input * 180.14 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '41'){
              this.answer = this.user_input * 276.22 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '42'){
              this.answer = this.user_input * 191.22 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '43'){
              this.answer = this.user_input * 204.86 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '44'){
              this.answer = this.user_input * 204.86 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '45'){
              this.answer = this.user_input * 218.5 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '46'){
              this.answer = this.user_input * 224.18 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '47'){
              this.answer = this.user_input * 72.74 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '48'){
              this.answer = this.user_input * 127.86 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '49'){
              this.answer = this.user_input * 150.02 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '50'){
              this.answer = this.user_input * 204.57 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '51'){
              this.answer = this.user_input * 159.11 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '52'){
              this.answer = this.user_input * 182.13 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '53'){
              this.answer = this.user_input * 100.01 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '54'){
              this.answer = this.user_input * 161.95 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '55'){
              this.answer = this.user_input * 182.7 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '56'){
              this.answer = this.user_input * 203.04 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '57'){
              this.answer = this.user_input * 301.18 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '58'){
              this.answer = this.user_input * 378.75 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '59'){
              this.answer = this.user_input * 269.01 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '60'){
              this.answer = this.user_input * 258.56 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '61'){
              this.answer = this.user_input * 122.74 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '62'){
              this.answer = this.user_input * 86.38 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '63'){
              this.answer = this.user_input * 340.96 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '64'){
              this.answer = this.user_input * 213.95 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '65'){
              this.answer = this.user_input * 163.94 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '66'){
              this.answer = this.user_input * 309.7 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '67'){
              this.answer = this.user_input * 200.31 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '68'){
              this.answer = this.user_input * 341.24 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '69'){
              this.answer = this.user_input * 181.84 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '70'){
              this.answer = this.user_input * 269.92 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '8' && this.select3 === '71'){
              this.answer = this.user_input * 301.18 + 'g';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '1'){
              this.answer = this.user_input * 0.28 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '2'){
              this.answer = this.user_input * 0.15 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '3'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '4'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '5'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '6'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '7'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '8'){
              this.answer = this.user_input * 0.26 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '9'){
              this.answer = this.user_input * 0.2 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '10'){
              this.answer = this.user_input * 0.23 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '11'){
              this.answer = this.user_input * 0.24 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '12'){
              this.answer = this.user_input * 0.15 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '13'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '14'){
              this.answer = this.user_input * 0.4 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '15'){
              this.answer = this.user_input * 0.38 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '16'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '17'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '18'){
              this.answer = this.user_input * 0.26 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '19'){
              this.answer = this.user_input * 0.28 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '20'){
              this.answer = this.user_input * 0.26 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '21'){
              this.answer = this.user_input * 0.26 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '22'){
              this.answer = this.user_input * 0.25 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '23'){
              this.answer = this.user_input * 0.26 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '24'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '25'){
              this.answer = this.user_input * 0.29 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '26'){
              this.answer = this.user_input * 0.37 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '27'){
              this.answer = this.user_input * 0.3 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '28'){
              this.answer = this.user_input * 0.29 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '29'){
              this.answer = this.user_input * 0.28 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '30'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '31'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '32'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '33'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '34'){
              this.answer = this.user_input * 0.08 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '35'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '36'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '37'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '38'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '39'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '40'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '41'){
              this.answer = this.user_input * 0.28 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '42'){
              this.answer = this.user_input * 0.19 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '43'){
              this.answer = this.user_input * 0.2 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '44'){
              this.answer = this.user_input * 0.2 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '45'){
              this.answer = this.user_input * 0.22 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '46'){
              this.answer = this.user_input * 0.22 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '47'){
              this.answer = this.user_input * 0.07 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '48'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '49'){
              this.answer = this.user_input * 0.15 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '50'){
              this.answer = this.user_input * 0.2 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '51'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '52'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '53'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '54'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '55'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '56'){
              this.answer = this.user_input * 0.2 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '57'){
              this.answer = this.user_input * 0.3 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '58'){
              this.answer = this.user_input * 0.38 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '59'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '60'){
              this.answer = this.user_input * 0.26 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '61'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '62'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '63'){
              this.answer = this.user_input * 0.34 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '64'){
              this.answer = this.user_input * 0.21 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '65'){
              this.answer = this.user_input * 0.16 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '66'){
              this.answer = this.user_input * 0.31 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '67'){
              this.answer = this.user_input * 0.2 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '68'){
              this.answer = this.user_input * 0.34 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '69'){
              this.answer = this.user_input * 0.18 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '70'){
              this.answer = this.user_input * 0.27 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '9' && this.select3 === '71'){
              this.answer = this.user_input * 0.3 + ' kg';
            }
            else if(this.select1 === '3' && this.select2 === '10'){
              this.answer = this.user_input * 0.28 + ' L';
            }
            else if(this.select1 === '3' && this.select2 === '11'){
              this.answer = this.user_input * 284.13 + ' mL';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '1'){
              this.answer = this.user_input * 10.02 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '2'){
              this.answer = this.user_input * 5.3 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '3'){
              this.answer = this.user_input * 4.07 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '4'){
              this.answer = this.user_input * 5.51 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '5'){
              this.answer = this.user_input * 4.83 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '6'){
              this.answer = this.user_input * 4.49 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '7'){
              this.answer = this.user_input * 4.79 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '8'){
              this.answer = this.user_input * 9.02 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '9'){
              this.answer = this.user_input * 6.91 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '10'){
              this.answer = this.user_input * 8.25 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '11'){
              this.answer = this.user_input * 8.51 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '12'){
              this.answer = this.user_input * 5.12 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '13'){
              this.answer = this.user_input * 9.63 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '14'){
              this.answer = this.user_input * 14.23 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '15'){
              this.answer = this.user_input * 13.23 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '16'){
              this.answer = this.user_input * 4.44 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '17'){
              this.answer = this.user_input * 9.61 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '18'){
              this.answer = this.user_input * 9.21 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '19'){
              this.answer = this.user_input * 9.75 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '20'){
              this.answer = this.user_input * 9.26 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '21'){
              this.answer = this.user_input * 9.22 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '22'){
              this.answer = this.user_input * 8.92 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '23'){
              this.answer = this.user_input * 9.22 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '24'){
              this.answer = this.user_input * 9.62 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '25'){
              this.answer = this.user_input * 10.37 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '26'){
              this.answer = this.user_input * 12.96 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '27'){
              this.answer = this.user_input * 10.67 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '28'){
              this.answer = this.user_input * 10.14 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '29'){
              this.answer = this.user_input * 9.96 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '30'){
              this.answer = this.user_input * 4.97 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '31'){
              this.answer = this.user_input * 9.62 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '32'){
              this.answer = this.user_input * 4.61 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '33'){
              this.answer = this.user_input * 5.01 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '34'){
              this.answer = this.user_input * 2.73 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '35'){
              this.answer = this.user_input * 6.42 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '36'){
              this.answer = this.user_input * 4.65 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '37'){
              this.answer = this.user_input * 6.21 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '38'){
              this.answer = this.user_input * 4.96 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '39'){
              this.answer = this.user_input * 6.42 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '40'){
              this.answer = this.user_input * 6.35 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '41'){
              this.answer = this.user_input * 9.74 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '42'){
              this.answer = this.user_input * 6.75 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '43'){
              this.answer = this.user_input * 7.23 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '44'){
              this.answer = this.user_input * 7.23 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '45'){
              this.answer = this.user_input * 7.71 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '46'){
              this.answer = this.user_input * 7.91 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '47'){
              this.answer = this.user_input * 2.57 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '48'){
              this.answer = this.user_input * 4.51 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '49'){
              this.answer = this.user_input * 5.29 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '50'){
              this.answer = this.user_input * 7.22 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '51'){
              this.answer = this.user_input * 5.61 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '52'){
              this.answer = this.user_input * 6.42 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '53'){
              this.answer = this.user_input * 3.53 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '54'){
              this.answer = this.user_input * 5.71 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '55'){
              this.answer = this.user_input * 6.44 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '56'){
              this.answer = this.user_input * 7.16 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '57'){
              this.answer = this.user_input * 10.62 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '58'){
              this.answer = this.user_input * 13.36 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '59'){
              this.answer = this.user_input * 9.49 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '60'){
              this.answer = this.user_input * 9.12 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '61'){
              this.answer = this.user_input * 4.33 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '62'){
              this.answer = this.user_input * 3.05 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '63'){
              this.answer = this.user_input * 12.03 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '64'){
              this.answer = this.user_input * 7.55 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '65'){
              this.answer = this.user_input * 5.78 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '66'){
              this.answer = this.user_input * 10.92 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '67'){
              this.answer = this.user_input * 7.07 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '68'){
              this.answer = this.user_input * 12.04 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '69'){
              this.answer = this.user_input * 6.41 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '70'){
              this.answer = this.user_input * 9.52 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '12' && this.select3 === '71'){
              this.answer = this.user_input * 10.62 + ' oz';
            }
            else if(this.select1 === '3' && this.select2 === '13'){
              this.answer = this.user_input * 0.5 + ' pt';
            }
            else if(this.select1 === '3' && this.select2 === '14'){
              this.answer = this.user_input * 0.6 + ' pt';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '1'){
              this.answer = this.user_input * 0.63 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '2'){
              this.answer = this.user_input * 0.33 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '3'){
              this.answer = this.user_input * 0.25 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '4'){
              this.answer = this.user_input * 0.34 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '5'){
              this.answer = this.user_input * 0.3 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '6'){
              this.answer = this.user_input * 0.28 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '7'){
              this.answer = this.user_input * 0.3 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '8'){
              this.answer = this.user_input * 0.56 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '9'){
              this.answer = this.user_input * 0.43 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '10'){
              this.answer = this.user_input * 0.52 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '11'){
              this.answer = this.user_input * 0.53 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '12'){
              this.answer = this.user_input * 0.32 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '13'){
              this.answer = this.user_input * 0.6 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '14'){
              this.answer = this.user_input * 0.89 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '15'){
              this.answer = this.user_input * 0.83 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '16'){
              this.answer = this.user_input * 0.28 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '17'){
              this.answer = this.user_input * 0.6 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '18'){
              this.answer = this.user_input * 0.58 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '19'){
              this.answer = this.user_input * 0.61 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '20'){
              this.answer = this.user_input * 0.58 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '21'){
              this.answer = this.user_input * 0.58 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '22'){
              this.answer = this.user_input * 0.56 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '23'){
              this.answer = this.user_input * 0.58 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '24'){
              this.answer = this.user_input * 0.6 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '25'){
              this.answer = this.user_input * 0.65 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '26'){
              this.answer = this.user_input * 0.81 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '27'){
              this.answer = this.user_input * 0.67 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '28'){
              this.answer = this.user_input * 0.63 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '29'){
              this.answer = this.user_input * 0.62 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '30'){
              this.answer = this.user_input * 0.31 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '31'){
              this.answer = this.user_input * 0.6 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '32'){
              this.answer = this.user_input * 0.29 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '33'){
              this.answer = this.user_input * 0.31 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '34'){
              this.answer = this.user_input * 0.17 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '35'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '36'){
              this.answer = this.user_input * 0.29 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '37'){
              this.answer = this.user_input * 0.39 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '38'){
              this.answer = this.user_input * 0.31 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '39'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '40'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '41'){
              this.answer = this.user_input * 0.61 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '42'){
              this.answer = this.user_input * 0.42 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '43'){
              this.answer = this.user_input * 0.45 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '44'){
              this.answer = this.user_input * 0.45 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '45'){
              this.answer = this.user_input * 0.48 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '46'){
              this.answer = this.user_input * 0.49 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '47'){
              this.answer = this.user_input * 0.16 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '48'){
              this.answer = this.user_input * 0.28 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '49'){
              this.answer = this.user_input * 0.33 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '50'){
              this.answer = this.user_input * 0.45 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '51'){
              this.answer = this.user_input * 0.35 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '52'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '53'){
              this.answer = this.user_input * 0.22 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '54'){
              this.answer = this.user_input * 0.36 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '55'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '56'){
              this.answer = this.user_input * 0.45 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '57'){
              this.answer = this.user_input * 0.66 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '58'){
              this.answer = this.user_input * 0.83 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '59'){
              this.answer = this.user_input * 0.59 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '60'){
              this.answer = this.user_input * 0.57 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '61'){
              this.answer = this.user_input * 0.27 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '62'){
              this.answer = this.user_input * 0.19 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '63'){
              this.answer = this.user_input * 0.75 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '64'){
              this.answer = this.user_input * 0.47 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '65'){
              this.answer = this.user_input * 0.36 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '66'){
              this.answer = this.user_input * 0.68 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '67'){
              this.answer = this.user_input * 0.44 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '68'){
              this.answer = this.user_input * 0.75 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '69'){
              this.answer = this.user_input * 0.4 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '70'){
              this.answer = this.user_input * 0.6 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '15' && this.select3 === '71'){
              this.answer = this.user_input * 0.66 + ' lb';
            }
            else if(this.select1 === '3' && this.select2 === '16'){
              this.answer = this.user_input * 0.25 + ' qt';
            }
            else if(this.select1 === '3' && this.select2 === '17'){
              this.answer = this.user_input * 0.3 + ' qt';
            }
            else if(this.select1 === '3' && this.select2 === '18'){
              this.answer = this.user_input * 19.12;
            }
            else if(this.select1 === '3' && this.select2 === '19'){
              this.answer = this.user_input * 18.94;
            }
            else if(this.select1 === '3' && this.select2 === '20'){
              this.answer = this.user_input * 16;
            }
            else if(this.select1 === '3' && this.select2 === '21'){
              this.answer = this.user_input * 57.65;
            }
            else if(this.select1 === '3' && this.select2 === '22'){
              this.answer = this.user_input * 56.83;
            }
            else if(this.select1 === '3' && this.select2 === '23'){
              this.answer = this.user_input * 48;
            }
            else if(this.select1 === '3' && this.select2 === '24'){
              this.answer = this.user_input * 9.61 + 'fl oz';
            }
            else if(this.select1 === '4' && this.select2 === '1'){
              this.answer = this.user_input * 0.42;
            }
            else if(this.select1 === '4' && this.select2 === '2'){
              this.answer = this.user_input * 0.4;
            }
            else if(this.select1 === '4' && this.select2 === '3'){
              this.answer = this.user_input * 0.35;
            }
            else if(this.select1 === '4' && this.select2 === '5'){
              this.answer = this.user_input * 3.52 + ' fl oz';
            }
            else if(this.select1 === '4' && this.select2 === '6'){
              this.answer = this.user_input * 0.02 + ' fl oz';
            }
            else if(this.select1 === '4' && this.select2 === '7'){
              this.answer = this.user_input * 0.03;
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '1'){
              this.answer = this.user_input * 100 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '2'){
              this.answer = this.user_input * 52.9 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '3'){
              this.answer = this.user_input * 40.6 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '4'){
              this.answer = this.user_input * 55 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '5'){
              this.answer = this.user_input * 48.2 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '6'){
              this.answer = this.user_input * 44.8 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '7'){
              this.answer = this.user_input * 47.8 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '8'){
              this.answer = this.user_input * 90 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '9'){
              this.answer = this.user_input * 68.9 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '10'){
              this.answer = this.user_input * 82.3 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '11'){
              this.answer = this.user_input * 84.9 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '12'){
              this.answer = this.user_input * 51.1 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '13'){
              this.answer = this.user_input * 96.1 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '14'){
              this.answer = this.user_input * 142 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '15'){
              this.answer = this.user_input * 132 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '16'){
              this.answer = this.user_input * 44.3 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '17'){
              this.answer = this.user_input * 95.9 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '18'){
              this.answer = this.user_input * 91.9 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '19'){
              this.answer = this.user_input * 97.3 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '20'){
              this.answer = this.user_input * 92.43 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '21'){
              this.answer = this.user_input * 92 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '22'){
              this.answer = this.user_input * 89 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '23'){
              this.answer = this.user_input * 92 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '24'){
              this.answer = this.user_input * 96 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '25'){
              this.answer = this.user_input * 103.5 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '26'){
              this.answer = this.user_input * 129.34 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '27'){
              this.answer = this.user_input * 106.51 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '28'){
              this.answer = this.user_input * 101.2 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '29'){
              this.answer = this.user_input * 99.4 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '30'){
              this.answer = this.user_input * 49.6 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '31'){
              this.answer = this.user_input * 96 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '32'){
              this.answer = this.user_input * 46 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '33'){
              this.answer = this.user_input * 50 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '34'){
              this.answer = this.user_input * 27.2 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '35'){
              this.answer = this.user_input * 64.1 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '36'){
              this.answer = this.user_input * 46.4 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '37'){
              this.answer = this.user_input * 62 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '38'){
              this.answer = this.user_input * 49.45 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '39'){
              this.answer = this.user_input * 64.1 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '40'){
              this.answer = this.user_input * 63.4 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '41'){
              this.answer = this.user_input * 97.22 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '42'){
              this.answer = this.user_input * 67.3 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '43'){
              this.answer = this.user_input * 72.1 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '44'){
              this.answer = this.user_input * 72.1 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '45'){
              this.answer = this.user_input * 76.9 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '46'){
              this.answer = this.user_input * 78.9 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '47'){
              this.answer = this.user_input * 25.6 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '48'){
              this.answer = this.user_input * 45 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '49'){
              this.answer = this.user_input * 52.8 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '50'){
              this.answer = this.user_input * 72 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '51'){
              this.answer = this.user_input * 56 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '52'){
              this.answer = this.user_input * 64.1 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '53'){
              this.answer = this.user_input * 35.2 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '54'){
              this.answer = this.user_input * 57 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '55'){
              this.answer = this.user_input * 64.3 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '56'){
              this.answer = this.user_input * 71.46 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '57'){
              this.answer = this.user_input * 106 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '58'){
              this.answer = this.user_input * 133.3 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '59'){
              this.answer = this.user_input * 94.68 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '60'){
              this.answer = this.user_input * 91 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '61'){
              this.answer = this.user_input * 43.2 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '62'){
              this.answer = this.user_input * 30.4 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '63'){
              this.answer = this.user_input * 120 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '64'){
              this.answer = this.user_input * 75.3 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '65'){
              this.answer = this.user_input * 57.7 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '66'){
              this.answer = this.user_input * 109 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '67'){
              this.answer = this.user_input * 70.5 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '68'){
              this.answer = this.user_input * 120.1 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '69'){
              this.answer = this.user_input * 64 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '70'){
              this.answer = this.user_input * 95 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '8' && this.select3 === '71'){
              this.answer = this.user_input * 106 + 'g';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '1'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '2'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '3'){
              this.answer = this.user_input * 0.04 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '4'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '5'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '6'){
              this.answer = this.user_input * 0.04 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '7'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '8'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '9'){
              this.answer = this.user_input * 0.07 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '10'){
              this.answer = this.user_input * 0.08 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '11'){
              this.answer = this.user_input * 0.08 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '12'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '13'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '14'){
              this.answer = this.user_input * 0.14 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '15'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '16'){
              this.answer = this.user_input * 0.04 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '17'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '18'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '19'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '20'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '21'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '22'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '23'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '24'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '25'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '26'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '27'){
              this.answer = this.user_input * 0.11 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '28'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '29'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '30'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '31'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '32'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '33'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '34'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '35'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '36'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '37'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '38'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '39'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '40'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '41'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '42'){
              this.answer = this.user_input * 0.07 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '43'){
              this.answer = this.user_input * 0.07 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '44'){
              this.answer = this.user_input * 0.07 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '45'){
              this.answer = this.user_input * 0.08 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '46'){
              this.answer = this.user_input * 0.08 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '47'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '48'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '49'){
              this.answer = this.user_input * 0.05 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '50'){
              this.answer = this.user_input * 0.07 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '51'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '52'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '53'){
              this.answer = this.user_input * 0.04 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '54'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '55'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '56'){
              this.answer = this.user_input * 0.07 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '57'){
              this.answer = this.user_input * 0.11 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '58'){
              this.answer = this.user_input * 0.13 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '59'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '60'){
              this.answer = this.user_input * 0.09 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '61'){
              this.answer = this.user_input * 0.04 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '62'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '63'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '64'){
              this.answer = this.user_input * 0.08 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '65'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '66'){
              this.answer = this.user_input * 0.11 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '67'){
              this.answer = this.user_input * 0.07 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '68'){
              this.answer = this.user_input * 0.12 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '69'){
              this.answer = this.user_input * 0.06 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '70'){
              this.answer = this.user_input * 0.1 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '9' && this.select3 === '71'){
              this.answer = this.user_input * 0.11 + ' kg';
            }
            else if(this.select1 === '4' && this.select2 === '10'){
              this.answer = this.user_input * 0.1 + ' L';
            }
            else if(this.select1 === '4' && this.select2 === '11'){
              this.answer = this.user_input * 100 + ' mL';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '1'){
              this.answer = this.user_input * 3.53 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '2'){
              this.answer = this.user_input * 1.87 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '3'){
              this.answer = this.user_input * 1.43 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '4'){
              this.answer = this.user_input * 1.94 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '5'){
              this.answer = this.user_input * 1.7 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '6'){
              this.answer = this.user_input * 1.58 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '7'){
              this.answer = this.user_input * 1.69 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '8'){
              this.answer = this.user_input * 3.17 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '9'){
              this.answer = this.user_input * 2.43 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '10'){
              this.answer = this.user_input * 2.9 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '11'){
              this.answer = this.user_input * 2.99 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '12'){
              this.answer = this.user_input * 1.8 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '13'){
              this.answer = this.user_input * 3.39 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '14'){
              this.answer = this.user_input * 5.01 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '15'){
              this.answer = this.user_input * 4.66 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '16'){
              this.answer = this.user_input * 1.56 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '17'){
              this.answer = this.user_input * 3.38 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '18'){
              this.answer = this.user_input * 3.24 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '19'){
              this.answer = this.user_input * 3.43 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '20'){
              this.answer = this.user_input * 3.26 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '21'){
              this.answer = this.user_input * 3.25 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '22'){
              this.answer = this.user_input * 3.14 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '23'){
              this.answer = this.user_input * 3.25 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '24'){
              this.answer = this.user_input * 3.39 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '25'){
              this.answer = this.user_input * 3.65 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '26'){
              this.answer = this.user_input * 4.56 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '27'){
              this.answer = this.user_input * 3.76 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '28'){
              this.answer = this.user_input * 3.57 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '29'){
              this.answer = this.user_input * 3.51 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '30'){
              this.answer = this.user_input * 1.75 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '31'){
              this.answer = this.user_input * 3.39 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '32'){
              this.answer = this.user_input * 1.62 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '33'){
              this.answer = this.user_input * 1.76 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '34'){
              this.answer = this.user_input * 0.96 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '35'){
              this.answer = this.user_input * 2.26 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '36'){
              this.answer = this.user_input * 1.64 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '37'){
              this.answer = this.user_input * 2.19 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '38'){
              this.answer = this.user_input * 1.74 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '39'){
              this.answer = this.user_input * 2.26 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '40'){
              this.answer = this.user_input * 2.24 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '41'){
              this.answer = this.user_input * 3.43 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '42'){
              this.answer = this.user_input * 2.37 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '43'){
              this.answer = this.user_input * 2.54 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '44'){
              this.answer = this.user_input * 2.54 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '45'){
              this.answer = this.user_input * 2.71 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '46'){
              this.answer = this.user_input * 2.78 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '47'){
              this.answer = this.user_input * 0.9 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '48'){
              this.answer = this.user_input * 1.59 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '49'){
              this.answer = this.user_input * 1.86 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '50'){
              this.answer = this.user_input * 2.54 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '51'){
              this.answer = this.user_input * 1.98 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '52'){
              this.answer = this.user_input * 2.26 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '53'){
              this.answer = this.user_input * 1.24 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '54'){
              this.answer = this.user_input * 2.01 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '55'){
              this.answer = this.user_input * 2.27 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '56'){
              this.answer = this.user_input * 2.52 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '57'){
              this.answer = this.user_input * 3.74 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '58'){
              this.answer = this.user_input * 4.7 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '59'){
              this.answer = this.user_input * 3.34 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '60'){
              this.answer = this.user_input * 3.21 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '61'){
              this.answer = this.user_input * 1.52 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '62'){
              this.answer = this.user_input * 1.07 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '63'){
              this.answer = this.user_input * 4.23 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '64'){
              this.answer = this.user_input * 2.66 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '65'){
              this.answer = this.user_input * 2.04 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '66'){
              this.answer = this.user_input * 3.84 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '67'){
              this.answer = this.user_input * 2.49 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '68'){
              this.answer = this.user_input * 4.24 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '69'){
              this.answer = this.user_input * 2.26 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '70'){
              this.answer = this.user_input * 3.35 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '12' && this.select3 === '71'){
              this.answer = this.user_input * 3.74 + ' oz';
            }
            else if(this.select1 === '4' && this.select2 === '13'){
              this.answer = this.user_input * 0.18 + ' pt';
            }
            else if(this.select1 === '4' && this.select2 === '14'){
              this.answer = this.user_input * 0.21 + ' pt';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '1'){
              this.answer = this.user_input * 0.22 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '2'){
              this.answer = this.user_input * 0.12 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '3'){
              this.answer = this.user_input * 0.09 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '4'){
              this.answer = this.user_input * 0.12 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '5'){
              this.answer = this.user_input * 0.11 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '6'){
              this.answer = this.user_input * 0.1 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '7'){
              this.answer = this.user_input * 0.11 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '8'){
              this.answer = this.user_input * 0.2 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '9'){
              this.answer = this.user_input * 0.15 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '10'){
              this.answer = this.user_input * 0.18 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '11'){
              this.answer = this.user_input * 0.19 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '12'){
              this.answer = this.user_input * 0.11 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '13'){
              this.answer = this.user_input * 0.21 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '14'){
              this.answer = this.user_input * 0.31 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '15'){
              this.answer = this.user_input * 0.29 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '16'){
              this.answer = this.user_input * 0.1 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '17'){
              this.answer = this.user_input * 0.21 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '18'){
              this.answer = this.user_input * 0.2 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '19'){
              this.answer = this.user_input * 0.21 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '20'){
              this.answer = this.user_input * 0.2 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '21'){
              this.answer = this.user_input * 0.2 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '22'){
              this.answer = this.user_input * 0.2 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '23'){
              this.answer = this.user_input * 0.2 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '24'){
              this.answer = this.user_input * 0.21 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '25'){
              this.answer = this.user_input * 0.23 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '26'){
              this.answer = this.user_input * 0.29 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '27'){
              this.answer = this.user_input * 0.23 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '28'){
              this.answer = this.user_input * 0.22 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '29'){
              this.answer = this.user_input * 0.22 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '30'){
              this.answer = this.user_input * 0.11 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '31'){
              this.answer = this.user_input * 0.21 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '32'){
              this.answer = this.user_input * 0.1 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '33'){
              this.answer = this.user_input * 0.11 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '34'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '35'){
              this.answer = this.user_input * 0.14 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '36'){
              this.answer = this.user_input * 0.1 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '37'){
              this.answer = this.user_input * 0.14 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '38'){
              this.answer = this.user_input * 0.11 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '39'){
              this.answer = this.user_input * 0.14 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '40'){
              this.answer = this.user_input * 0.14 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '41'){
              this.answer = this.user_input * 0.21 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '42'){
              this.answer = this.user_input * 0.15 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '43'){
              this.answer = this.user_input * 0.16 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '44'){
              this.answer = this.user_input * 0.16 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '45'){
              this.answer = this.user_input * 0.17 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '46'){
              this.answer = this.user_input * 0.17 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '47'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '48'){
              this.answer = this.user_input * 0.1 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '49'){
              this.answer = this.user_input * 0.12 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '50'){
              this.answer = this.user_input * 0.16 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '51'){
              this.answer = this.user_input * 0.12 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '52'){
              this.answer = this.user_input * 0.14 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '53'){
              this.answer = this.user_input * 0.08 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '54'){
              this.answer = this.user_input * 0.13 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '55'){
              this.answer = this.user_input * 0.14 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '56'){
              this.answer = this.user_input * 0.16 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '57'){
              this.answer = this.user_input * 0.23 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '58'){
              this.answer = this.user_input * 0.29 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '59'){
              this.answer = this.user_input * 0.21 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '60'){
              this.answer = this.user_input * 0.2 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '61'){
              this.answer = this.user_input * 0.1 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '62'){
              this.answer = this.user_input * 0.07 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '63'){
              this.answer = this.user_input * 0.26 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '64'){
              this.answer = this.user_input * 0.17 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '65'){
              this.answer = this.user_input * 0.13 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '66'){
              this.answer = this.user_input * 0.24 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '67'){
              this.answer = this.user_input * 0.16 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '68'){
              this.answer = this.user_input * 0.26 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '69'){
              this.answer = this.user_input * 0.14 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '70'){
              this.answer = this.user_input * 0.21 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '15' && this.select3 === '71'){
              this.answer = this.user_input * 0.23 + ' lb';
            }
            else if(this.select1 === '4' && this.select2 === '16'){
              this.answer = this.user_input * 0.09 + ' qt';
            }
            else if(this.select1 === '4' && this.select2 === '17'){
              this.answer = this.user_input * 0.11 + ' qt';
            }
            else if(this.select1 === '4' && this.select2 === '18'){
              this.answer = this.user_input * 6.76 + ' qt';
            }
            else if(this.select1 === '4' && this.select2 === '19'){
              this.answer = this.user_input * 6.67 + ' qt';
            }
            else if(this.select1 === '4' && this.select2 === '20'){
              this.answer = this.user_input * 5.63;
            }
            else if(this.select1 === '4' && this.select2 === '21'){
              this.answer = this.user_input * 20.29;
            }
            else if(this.select1 === '4' && this.select2 === '22'){
              this.answer = this.user_input * 20;
            }
            else if(this.select1 === '4' && this.select2 === '23'){
              this.answer = this.user_input * 16.89;
            }
            else if(this.select1 === '4' && this.select2 === '24'){
              this.answer = this.user_input * 3.38 + ' fl oz';
            }
            else if(this.select1 === '5' && this.select2 === '1'){
              this.answer = this.user_input * 0.12;
            }
            else if(this.select1 === '5' && this.select2 === '2'){
              this.answer = this.user_input * 0.11;
            }
            else if(this.select1 === '5' && this.select2 === '3'){
              this.answer = this.user_input * 0.1;
            }
            else if(this.select1 === '5' && this.select2 === '4'){
              this.answer = this.user_input * 0.28 + ' dL';
            }
            else if(this.select1 === '5' && this.select2 === '6'){
              this.answer = this.user_input * 0.01 + ' gal';
            }
            else if(this.select1 === '5' && this.select2 === '7'){
              this.answer = this.user_input * 0.01 + ' gal';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '1'){
              this.answer = this.user_input * 28.41 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '2'){
              this.answer = this.user_input * 15.03 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '3'){
              this.answer = this.user_input * 11.54 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '4'){
              this.answer = this.user_input * 15.63 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '5'){
              this.answer = this.user_input * 13.7 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '6'){
              this.answer = this.user_input * 12.73 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '7'){
              this.answer = this.user_input * 13.58 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '8'){
              this.answer = this.user_input * 25.57 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '9'){
              this.answer = this.user_input * 19.58 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '10'){
              this.answer = this.user_input * 23.38 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '11'){
              this.answer = this.user_input * 24.12 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '12'){
              this.answer = this.user_input * 14.52 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '13'){
              this.answer = this.user_input * 27.3 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '14'){
              this.answer = this.user_input * 40.35 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '15'){
              this.answer = this.user_input * 37.51 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '16'){
              this.answer = this.user_input * 12.59 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '17'){
              this.answer = this.user_input * 27.25 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '18'){
              this.answer = this.user_input * 26.11 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '19'){
              this.answer = this.user_input * 27.65 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '20'){
              this.answer = this.user_input * 26.26 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '21'){
              this.answer = this.user_input * 26.14 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '22'){
              this.answer = this.user_input * 25.29 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '23'){
              this.answer = this.user_input * 26.14 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '24'){
              this.answer = this.user_input * 27.28 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '25'){
              this.answer = this.user_input * 29.41 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '26'){
              this.answer = this.user_input * 36.75 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '27'){
              this.answer = this.user_input * 30.26 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '28'){
              this.answer = this.user_input * 28.75 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '29'){
              this.answer = this.user_input * 28.24 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '30'){
              this.answer = this.user_input * 14.09 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '31'){
              this.answer = this.user_input * 27.28+ 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '32'){
              this.answer = this.user_input * 13.07 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '33'){
              this.answer = this.user_input * 14.21 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '34'){
              this.answer = this.user_input * 7.73 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '35'){
              this.answer = this.user_input * 18.21 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '36'){
              this.answer = this.user_input * 13.18 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '37'){
              this.answer = this.user_input * 17.62 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '38'){
              this.answer = this.user_input * 14.05 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '39'){
              this.answer = this.user_input * 18.21 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '40'){
              this.answer = this.user_input * 18.01 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '41'){
              this.answer = this.user_input * 27.62 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '42'){
              this.answer = this.user_input * 19.12 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '43'){
              this.answer = this.user_input * 20.49 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '44'){
              this.answer = this.user_input * 20.49 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '45'){
              this.answer = this.user_input * 21.85 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '46'){
              this.answer = this.user_input * 22.42 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '47'){
              this.answer = this.user_input * 7.27 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '48'){
              this.answer = this.user_input * 12.79 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '49'){
              this.answer = this.user_input * 15 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '50'){
              this.answer = this.user_input * 20.46 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '51'){
              this.answer = this.user_input * 15.91 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '52'){
              this.answer = this.user_input * 18.21 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '53'){
              this.answer = this.user_input * 10 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '54'){
              this.answer = this.user_input * 16.2 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '55'){
              this.answer = this.user_input * 18.27 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '56'){
              this.answer = this.user_input * 20.3 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '57'){
              this.answer = this.user_input * 30.12 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '58'){
              this.answer = this.user_input * 37.87 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '59'){
              this.answer = this.user_input * 26.9 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '60'){
              this.answer = this.user_input * 25.86 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '61'){
              this.answer = this.user_input * 12.27 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '62'){
              this.answer = this.user_input * 8.64 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '63'){
              this.answer = this.user_input * 34.1 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '64'){
              this.answer = this.user_input * 21.4 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '65'){
              this.answer = this.user_input * 16.39 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '66'){
              this.answer = this.user_input * 30.97 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '67'){
              this.answer = this.user_input * 20.03 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '68'){
              this.answer = this.user_input * 34.12 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '69'){
              this.answer = this.user_input * 18.18 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '70'){
              this.answer = this.user_input * 26.99 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '8' && this.select3 === '71'){
              this.answer = this.user_input * 30.12 + 'g';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '1'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '2'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '3'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '4'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '5'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '6'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '7'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '8'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '9'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '10'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '11'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '12'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '13'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '14'){
              this.answer = this.user_input * 0.04 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '15'){
              this.answer = this.user_input * 0.04 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '16'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '17'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '18'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '19'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '20'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '21'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '22'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '23'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '24'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '25'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '26'){
              this.answer = this.user_input * 0.04 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '27'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '28'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '29'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '30'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '31'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '32'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '33'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '34'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '35'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '36'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '37'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '38'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '39'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '40'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '41'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '42'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '43'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '44'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '45'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '46'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '47'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '48'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '49'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '50'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '51'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '52'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '53'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '54'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '55'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '56'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '57'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '58'){
              this.answer = this.user_input * 0.04 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '59'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '60'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '61'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '62'){
              this.answer = this.user_input * 0.01 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '63'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '64'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '65'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '66'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '67'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '68'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '69'){
              this.answer = this.user_input * 0.02 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '70'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '9' && this.select3 === '71'){
              this.answer = this.user_input * 0.03 + ' kg';
            }
            else if(this.select1 === '5' && this.select2 === '10'){
              this.answer = this.user_input * 0.03 + ' L';
            }
            else if(this.select1 === '5' && this.select2 === '11'){
              this.answer = this.user_input * 28.41 + ' ML';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '1'){
              this.answer = this.user_input * 1 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '2'){
              this.answer = this.user_input * 0.53 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '3'){
              this.answer = this.user_input * 0.41 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '4'){
              this.answer = this.user_input * 0.55 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '5'){
              this.answer = this.user_input * 0.48 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '6'){
              this.answer = this.user_input * 0.45 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '7'){
              this.answer = this.user_input * 0.48 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '8'){
              this.answer = this.user_input * 0.9 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '9'){
              this.answer = this.user_input * 0.69 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '10'){
              this.answer = this.user_input * 0.82 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '11'){
              this.answer = this.user_input * 0.85 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '12'){
              this.answer = this.user_input * 0.51 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '13'){
              this.answer = this.user_input * 0.96 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '14'){
              this.answer = this.user_input * 1.42 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '15'){
              this.answer = this.user_input * 1.32 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '16'){
              this.answer = this.user_input * 0.44 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '17'){
              this.answer = this.user_input * 0.96 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '18'){
              this.answer = this.user_input * 0.92 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '19'){
              this.answer = this.user_input * 0.98 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '20'){
              this.answer = this.user_input * 0.93 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '21'){
              this.answer = this.user_input * 0.92 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '22'){
              this.answer = this.user_input * 0.89 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '23'){
              this.answer = this.user_input * 0.92 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '24'){
              this.answer = this.user_input * 0.96 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '25'){
              this.answer = this.user_input * 1.04 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '26'){
              this.answer = this.user_input * 1.3 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '27'){
              this.answer = this.user_input * 1.07 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '28'){
              this.answer = this.user_input * 1.01 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '29'){
              this.answer = this.user_input * 1 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '30'){
              this.answer = this.user_input * 0.5 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '31'){
              this.answer = this.user_input * 0.96 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '32'){
              this.answer = this.user_input * 0.46 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '33'){
              this.answer = this.user_input * 0.5 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '34'){
              this.answer = this.user_input * 0.27 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '35'){
              this.answer = this.user_input * 0.64 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '36'){
              this.answer = this.user_input * 0.47 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '37'){
              this.answer = this.user_input * 0.62 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '38'){
              this.answer = this.user_input * 0.5 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '39'){
              this.answer = this.user_input * 0.64 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '40'){
              this.answer = this.user_input * 0.64 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '41'){
              this.answer = this.user_input * 0.97 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '42'){
              this.answer = this.user_input * 0.67 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '43'){
              this.answer = this.user_input * 0.72 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '44'){
              this.answer = this.user_input * 0.72 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '45'){
              this.answer = this.user_input * 0.77 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '46'){
              this.answer = this.user_input * 0.79 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '47'){
              this.answer = this.user_input * 0.26 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '48'){
              this.answer = this.user_input * 0.45 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '49'){
              this.answer = this.user_input * 0.53 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '50'){
              this.answer = this.user_input * 0.72 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '51'){
              this.answer = this.user_input * 0.56 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '52'){
              this.answer = this.user_input * 0.64 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '53'){
              this.answer = this.user_input * 0.35 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '54'){
              this.answer = this.user_input * 0.57 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '55'){
              this.answer = this.user_input * 0.64 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '56'){
              this.answer = this.user_input * 0.72 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '57'){
              this.answer = this.user_input * 1.06 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '58'){
              this.answer = this.user_input * 1.34 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '59'){
              this.answer = this.user_input * 0.95 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '60'){
              this.answer = this.user_input * 0.91 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '61'){
              this.answer = this.user_input * 0.43 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '62'){
              this.answer = this.user_input * 0.3 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '63'){
              this.answer = this.user_input * 1.2 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '64'){
              this.answer = this.user_input * 0.75 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '65'){
              this.answer = this.user_input * 0.58 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '66'){
              this.answer = this.user_input * 1.09 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '67'){
              this.answer = this.user_input * 0.71 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '68'){
              this.answer = this.user_input * 1.2 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '69'){
              this.answer = this.user_input * 0.64 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '70'){
              this.answer = this.user_input * 0.95 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '12' && this.select3 === '71'){
              this.answer = this.user_input * 1.06 + ' oz';
            }
            else if(this.select1 === '5' && this.select2 === '13'){
              this.answer = this.user_input * 0.05 + ' pt';
            }
            else if(this.select1 === '5' && this.select2 === '14'){
              this.answer = this.user_input * 0.06 + ' pt';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '1'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '2'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '3'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '4'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '5'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '6'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '7'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '8'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '9'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '10'){
              this.answer = this.user_input * 0.05 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '11'){
              this.answer = this.user_input * 0.05 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '12'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '13'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '14'){
              this.answer = this.user_input * 0.09 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '15'){
              this.answer = this.user_input * 0.08 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '16'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '17'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '18'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '19'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '20'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '21'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '22'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '23'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '24'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '25'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '26'){
              this.answer = this.user_input * 0.08 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '27'){
              this.answer = this.user_input * 0.07 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '28'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '29'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '30'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '31'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '32'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '33'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '34'){
              this.answer = this.user_input * 0.02 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '35'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '36'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '37'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '38'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '39'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '40'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '41'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '42'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '43'){
              this.answer = this.user_input * 0.05 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '44'){
              this.answer = this.user_input * 0.05 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '45'){
              this.answer = this.user_input * 0.05 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '46'){
              this.answer = this.user_input * 0.05 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '47'){
              this.answer = this.user_input * 0.02 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '48'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '49'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '50'){
              this.answer = this.user_input * 0.05 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '51'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '52'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '53'){
              this.answer = this.user_input * 0.02 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '54'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '55'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '56'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '57'){
              this.answer = this.user_input * 0.07 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '58'){
              this.answer = this.user_input * 0.08 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '59'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '60'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '61'){
              this.answer = this.user_input * 0.03 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '62'){
              this.answer = this.user_input * 0.02 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '63'){
              this.answer = this.user_input * 0.08 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '64'){
              this.answer = this.user_input * 0.05 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '65'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '66'){
              this.answer = this.user_input * 0.07 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '67'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '68'){
              this.answer = this.user_input * 0.08 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '69'){
              this.answer = this.user_input * 0.04 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '70'){
              this.answer = this.user_input * 0.06 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '15' && this.select3 === '71'){
              this.answer = this.user_input * 0.07 + ' lb';
            }
            else if(this.select1 === '5' && this.select2 === '16'){
              this.answer = this.user_input * 0.02 + ' qt';
            }
            else if(this.select1 === '5' && this.select2 === '17'){
              this.answer = this.user_input * 0.03 + ' qt';
            }
            else if(this.select1 === '5' && this.select2 === '18'){
              this.answer = this.user_input * 1.92;
            }
            else if(this.select1 === '5' && this.select2 === '19'){
              this.answer = this.user_input * 1.89;
            }
            else if(this.select1 === '5' && this.select2 === '20'){
              this.answer = this.user_input * 1.6;
            }
            else if(this.select1 === '5' && this.select2 === '21'){
              this.answer = this.user_input * 5.76;
            }
            else if(this.select1 === '5' && this.select2 === '22'){
              this.answer = this.user_input * 5.68;
            }
            else if(this.select1 === '5' && this.select2 === '23'){
              this.answer = this.user_input * 4.8;
            }
            else if(this.select1 === '5' && this.select2 === '24'){
              this.answer = this.user_input * 0.96 + ' fl oz';
            }
            else if(this.select1 === '6' && this.select2 === '1'){
              this.answer = this.user_input * 19.22;
            }
            else if(this.select1 === '6' && this.select2 === '2'){
              this.answer = this.user_input * 18.18;
            }
            else if(this.select1 === '6' && this.select2 === '3'){
              this.answer = this.user_input * 16;
            }
            else if(this.select1 === '6' && this.select2 === '4'){
              this.answer = this.user_input * 45.46 + ' dL';
            }
            else if(this.select1 === '6' && this.select2 === '5'){
              this.answer = this.user_input * 160 + ' fl oz';
            }
            else if(this.select1 === '6' && this.select2 === '7'){
              this.answer = this.user_input * 1.2;
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '1'){
              this.answer = this.user_input * 4546.09 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '2'){
              this.answer = this.user_input * 2404.88 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '3'){
              this.answer = this.user_input * 1845.71 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '4'){
              this.answer = this.user_input * 2500.35 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '5'){
              this.answer = this.user_input * 2191.22 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '6'){
              this.answer = this.user_input * 2036.65 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '7'){
              this.answer = this.user_input * 2173.03 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '8'){
              this.answer = this.user_input * 4091.48 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '9'){
              this.answer = this.user_input * 3132.26 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '10'){
              this.answer = this.user_input * 3741.43 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '11'){
              this.answer = this.user_input * 3859.63 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '12'){
              this.answer = this.user_input * 2323.05 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '13'){
              this.answer = this.user_input * 4368.79 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '14'){
              this.answer = this.user_input * 6455.45 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '15'){
              this.answer = this.user_input * 6000.84 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '16'){
              this.answer = this.user_input * 2013.92 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '17'){
              this.answer = this.user_input * 4359.7 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '18'){
              this.answer = this.user_input * 4177.86 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '19'){
              this.answer = this.user_input * 4423.35 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '20'){
              this.answer = this.user_input * 4201.81 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '21'){
              this.answer = this.user_input * 4182.4 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '22'){
              this.answer = this.user_input * 4046.02 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '23'){
              this.answer = this.user_input * 4182.4 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '24'){
              this.answer = this.user_input * 4364.25 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '25'){
              this.answer = this.user_input * 4705.2 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '26'){
              this.answer = this.user_input * 5879.91 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '27'){
              this.answer = this.user_input * 4842.04 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '28'){
              this.answer = this.user_input * 4600.64 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '29'){
              this.answer = this.user_input * 4518.81 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '30'){
              this.answer = this.user_input * 2254.86 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '31'){
              this.answer = this.user_input * 4364.25 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '32'){
              this.answer = this.user_input * 2091.2 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '33'){
              this.answer = this.user_input * 2273.05 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '34'){
              this.answer = this.user_input * 1236.54 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '35'){
              this.answer = this.user_input * 2914.04 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '36'){
              this.answer = this.user_input * 2109.39 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '37'){
              this.answer = this.user_input * 2818.58 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '38'){
              this.answer = this.user_input * 2248.18 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '39'){
              this.answer = this.user_input * 2914.04 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '40'){
              this.answer = this.user_input * 2882.27 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '41'){
              this.answer = this.user_input * 4419.48 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '42'){
              this.answer = this.user_input * 3059.52 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '43'){
              this.answer = this.user_input * 3277.73 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '44'){
              this.answer = this.user_input * 3277.73 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '45'){
              this.answer = this.user_input * 3495.94 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '46'){
              this.answer = this.user_input * 3586.87 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '47'){
              this.answer = this.user_input * 1163.8 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '48'){
              this.answer = this.user_input * 2045.74 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '49'){
              this.answer = this.user_input * 2400.34 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '50'){
              this.answer = this.user_input * 3273.19 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '51'){
              this.answer = this.user_input * 2545.81 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '52'){
              this.answer = this.user_input * 2914.04 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '53'){
              this.answer = this.user_input * 1600.22 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '54'){
              this.answer = this.user_input * 2591.27 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '55'){
              this.answer = this.user_input * 2923.14 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '56'){
              this.answer = this.user_input * 3248.64 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '57'){
              this.answer = this.user_input * 4818.86 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '58'){
              this.answer = this.user_input * 6059.94 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '59'){
              this.answer = this.user_input * 4304.19 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '60'){
              this.answer = this.user_input * 4136.94 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '61'){
              this.answer = this.user_input * 1963.91 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '62'){
              this.answer = this.user_input * 1382.01 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '63'){
              this.answer = this.user_input * 5455.31 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '64'){
              this.answer = this.user_input * 3423.21 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '65'){
              this.answer = this.user_input * 2623.09 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '66'){
              this.answer = this.user_input * 4955.24 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '67'){
              this.answer = this.user_input * 3204.99 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '68'){
              this.answer = this.user_input * 5459.85 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '69'){
              this.answer = this.user_input * 2909.5 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '70'){
              this.answer = this.user_input * 4318.79 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '8' && this.select3 === '71'){
              this.answer = this.user_input * 4818.86 + 'g';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '1'){
              this.answer = this.user_input * 4.55 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '2'){
              this.answer = this.user_input * 2.4 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '3'){
              this.answer = this.user_input * 1.85 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '4'){
              this.answer = this.user_input * 2.5 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '5'){
              this.answer = this.user_input * 2.19 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '6'){
              this.answer = this.user_input * 2.04 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '7'){
              this.answer = this.user_input * 2.17 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '8'){
              this.answer = this.user_input * 4.09 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '9'){
              this.answer = this.user_input * 3.13 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '10'){
              this.answer = this.user_input * 3.74 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '11'){
              this.answer = this.user_input * 3.86 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '12'){
              this.answer = this.user_input * 2.32 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '13'){
              this.answer = this.user_input * 4.37 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '14'){
              this.answer = this.user_input * 6.46 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '15'){
              this.answer = this.user_input * 6 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '16'){
              this.answer = this.user_input * 2.01 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '17'){
              this.answer = this.user_input * 4.36 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '18'){
              this.answer = this.user_input * 4.18 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '19'){
              this.answer = this.user_input * 4.42 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '20'){
              this.answer = this.user_input * 4.2 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '21'){
              this.answer = this.user_input * 4.18 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '22'){
              this.answer = this.user_input * 4.05 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '23'){
              this.answer = this.user_input * 4.18 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '24'){
              this.answer = this.user_input * 4.36 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '25'){
              this.answer = this.user_input * 4.71 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '26'){
              this.answer = this.user_input * 5.88 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '27'){
              this.answer = this.user_input * 4.84 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '28'){
              this.answer = this.user_input * 4.6 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '29'){
              this.answer = this.user_input * 4.52 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '30'){
              this.answer = this.user_input * 2.25 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '31'){
              this.answer = this.user_input * 4.36 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '32'){
              this.answer = this.user_input * 2.09 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '33'){
              this.answer = this.user_input * 2.27 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '34'){
              this.answer = this.user_input * 1.24 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '35'){
              this.answer = this.user_input * 2.91 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '36'){
              this.answer = this.user_input * 2.11 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '37'){
              this.answer = this.user_input * 2.82 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '38'){
              this.answer = this.user_input * 2.25 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '39'){
              this.answer = this.user_input * 2.91 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '40'){
              this.answer = this.user_input * 2.88 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '41'){
              this.answer = this.user_input * 4.42 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '42'){
              this.answer = this.user_input * 3.06 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '43'){
              this.answer = this.user_input * 3.28 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '44'){
              this.answer = this.user_input * 3.28 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '45'){
              this.answer = this.user_input * 3.5 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '46'){
              this.answer = this.user_input * 3.59 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '47'){
              this.answer = this.user_input * 1.16 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '48'){
              this.answer = this.user_input * 2.05 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '49'){
              this.answer = this.user_input * 2.4 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '50'){
              this.answer = this.user_input * 3.27 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '51'){
              this.answer = this.user_input * 2.55 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '52'){
              this.answer = this.user_input * 2.91 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '53'){
              this.answer = this.user_input * 1.6 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '54'){
              this.answer = this.user_input * 2.59 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '55'){
              this.answer = this.user_input * 2.92 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '56'){
              this.answer = this.user_input * 3.25 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '57'){
              this.answer = this.user_input * 4.82 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '58'){
              this.answer = this.user_input * 6.06 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '59'){
              this.answer = this.user_input * 4.3 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '60'){
              this.answer = this.user_input * 4.14 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '61'){
              this.answer = this.user_input * 1.96 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '62'){
              this.answer = this.user_input * 1.38 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '63'){
              this.answer = this.user_input * 5.46 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '64'){
              this.answer = this.user_input * 3.42 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '65'){
              this.answer = this.user_input * 2.62 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '66'){
              this.answer = this.user_input * 4.96 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '67'){
              this.answer = this.user_input * 3.2 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '68'){
              this.answer = this.user_input * 5.46 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '69'){
              this.answer = this.user_input * 2.91 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '70'){
              this.answer = this.user_input * 4.32 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '9' && this.select3 === '71'){
              this.answer = this.user_input * 4.82 + ' kg';
            }
            else if(this.select1 === '6' && this.select2 === '10'){
              this.answer = this.user_input * 4.55 + ' L';
            }
            else if(this.select1 === '6' && this.select2 === '11'){
              this.answer = this.user_input * 4546.09 + ' mL';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '1'){
              this.answer = this.user_input * 160.36 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '2'){
              this.answer = this.user_input * 84.83 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '3'){
              this.answer = this.user_input * 65.11 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '4'){
              this.answer = this.user_input * 88.2 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '5'){
              this.answer = this.user_input * 77.29 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '6'){
              this.answer = this.user_input * 71.84 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '7'){
              this.answer = this.user_input * 76.65 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '8'){
              this.answer = this.user_input * 144.32 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '9'){
              this.answer = this.user_input * 110.49 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '10'){
              this.answer = this.user_input * 131.98 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '11'){
              this.answer = this.user_input * 136.14 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '12'){
              this.answer = this.user_input * 81.94 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '13'){
              this.answer = this.user_input * 154.1 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '14'){
              this.answer = this.user_input * 227.71 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '15'){
              this.answer = this.user_input * 211.67 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '16'){
              this.answer = this.user_input * 71.04 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '17'){
              this.answer = this.user_input * 153.78 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '18'){
              this.answer = this.user_input * 147.37 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '19'){
              this.answer = this.user_input * 156.03 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '20'){
              this.answer = this.user_input * 148.21 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '21'){
              this.answer = this.user_input * 147.53 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '22'){
              this.answer = this.user_input * 142.72 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '23'){
              this.answer = this.user_input * 147.53 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '24'){
              this.answer = this.user_input * 153.94 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '25'){
              this.answer = this.user_input * 165.97 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '26'){
              this.answer = this.user_input * 207.41 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '27'){
              this.answer = this.user_input * 170.8 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '28'){
              this.answer = this.user_input * 162.28 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '29'){
              this.answer = this.user_input * 159.4 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '30'){
              this.answer = this.user_input * 79.54 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '31'){
              this.answer = this.user_input * 153.94 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '32'){
              this.answer = this.user_input * 73.76 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '33'){
              this.answer = this.user_input * 80.18 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '34'){
              this.answer = this.user_input * 43.62 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '35'){
              this.answer = this.user_input * 102.79 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '36'){
              this.answer = this.user_input * 74.41 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '37'){
              this.answer = this.user_input * 99.42 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '38'){
              this.answer = this.user_input * 79.3 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '39'){
              this.answer = this.user_input * 102.79 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '40'){
              this.answer = this.user_input * 101.67 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '41'){
              this.answer = this.user_input * 155.89 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '42'){
              this.answer = this.user_input * 107.92 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '43'){
              this.answer = this.user_input * 115.62 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '44'){
              this.answer = this.user_input * 115.62 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '45'){
              this.answer = this.user_input * 123.32 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '46'){
              this.answer = this.user_input * 126.52 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '47'){
              this.answer = this.user_input * 41.05 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '48'){
              this.answer = this.user_input * 72.16 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '49'){
              this.answer = this.user_input * 84.67 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '50'){
              this.answer = this.user_input * 115.46 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '51'){
              this.answer = this.user_input * 89.8 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '52'){
              this.answer = this.user_input * 102.79 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '53'){
              this.answer = this.user_input * 56.45 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '54'){
              this.answer = this.user_input * 91.4 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '55'){
              this.answer = this.user_input * 103.11 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '56'){
              this.answer = this.user_input * 114.59 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '57'){
              this.answer = this.user_input * 169.98 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '58'){
              this.answer = this.user_input * 213.76 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '59'){
              this.answer = this.user_input * 151.83 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '60'){
              this.answer = this.user_input * 145.93 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '61'){
              this.answer = this.user_input * 69.27 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '62'){
              this.answer = this.user_input * 48.75 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '63'){
              this.answer = this.user_input * 192.43 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '64'){
              this.answer = this.user_input * 120.75 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '65'){
              this.answer = this.user_input * 92.53 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '66'){
              this.answer = this.user_input * 174.79 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '67'){
              this.answer = this.user_input * 113.05 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '68'){
              this.answer = this.user_input * 192.59 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '69'){
              this.answer = this.user_input * 102.63 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '70'){
              this.answer = this.user_input * 152.34 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '12' && this.select3 === '71'){
              this.answer = this.user_input * 169.98 + ' oz';
            }
            else if(this.select1 === '6' && this.select2 === '13'){
              this.answer = this.user_input * 8 + ' pt';
            }
            else if(this.select1 === '6' && this.select2 === '14'){
              this.answer = this.user_input * 9.61 + ' pt';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '1'){
              this.answer = this.user_input * 10.02 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '2'){
              this.answer = this.user_input * 5.3 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '3'){
              this.answer = this.user_input * 4.07 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '4'){
              this.answer = this.user_input * 5.51 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '5'){
              this.answer = this.user_input * 4.83 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '6'){
              this.answer = this.user_input * 4.49 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '7'){
              this.answer = this.user_input * 4.79 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '8'){
              this.answer = this.user_input * 9.02 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '9'){
              this.answer = this.user_input * 6.91 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '10'){
              this.answer = this.user_input * 8.25 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '11'){
              this.answer = this.user_input * 8.51 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '12'){
              this.answer = this.user_input * 5.12 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '13'){
              this.answer = this.user_input * 9.63 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '14'){
              this.answer = this.user_input * 14.23 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '15'){
              this.answer = this.user_input * 13.23 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '16'){
              this.answer = this.user_input * 4.44 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '17'){
              this.answer = this.user_input * 9.61 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '18'){
              this.answer = this.user_input * 9.21 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '19'){
              this.answer = this.user_input * 9.75 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '20'){
              this.answer = this.user_input * 9.26 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '21'){
              this.answer = this.user_input * 9.22 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '22'){
              this.answer = this.user_input * 8.92 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '23'){
              this.answer = this.user_input * 9.22 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '24'){
              this.answer = this.user_input * 9.62 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '25'){
              this.answer = this.user_input * 10.37 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '26'){
              this.answer = this.user_input * 12.96 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '27'){
              this.answer = this.user_input * 10.67 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '28'){
              this.answer = this.user_input * 10.14 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '29'){
              this.answer = this.user_input * 9.96 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '30'){
              this.answer = this.user_input * 4.97 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '31'){
              this.answer = this.user_input * 9.62 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '32'){
              this.answer = this.user_input * 4.61 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '33'){
              this.answer = this.user_input * 5.01 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '34'){
              this.answer = this.user_input * 2.73 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '35'){
              this.answer = this.user_input * 6.42 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '36'){
              this.answer = this.user_input * 4.65 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '37'){
              this.answer = this.user_input * 6.21 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '38'){
              this.answer = this.user_input * 4.96 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '39'){
              this.answer = this.user_input * 6.42 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '40'){
              this.answer = this.user_input * 6.35 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '41'){
              this.answer = this.user_input * 9.74 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '42'){
              this.answer = this.user_input * 6.75 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '43'){
              this.answer = this.user_input * 7.23 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '44'){
              this.answer = this.user_input * 7.23 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '45'){
              this.answer = this.user_input * 7.71 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '46'){
              this.answer = this.user_input * 7.91 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '47'){
              this.answer = this.user_input * 2.57 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '48'){
              this.answer = this.user_input * 4.51 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '49'){
              this.answer = this.user_input * 5.29 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '50'){
              this.answer = this.user_input * 7.22 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '51'){
              this.answer = this.user_input * 5.61 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '52'){
              this.answer = this.user_input * 6.42 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '53'){
              this.answer = this.user_input * 3.53 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '54'){
              this.answer = this.user_input * 5.71 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '55'){
              this.answer = this.user_input * 6.44 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '56'){
              this.answer = this.user_input * 7.16 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '57'){
              this.answer = this.user_input * 10.62 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '58'){
              this.answer = this.user_input * 13.36 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '59'){
              this.answer = this.user_input * 9.49 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '60'){
              this.answer = this.user_input * 9.12 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '61'){
              this.answer = this.user_input * 4.33 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '62'){
              this.answer = this.user_input * 3.05 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '63'){
              this.answer = this.user_input * 12.03 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '64'){
              this.answer = this.user_input * 7.55 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '65'){
              this.answer = this.user_input * 5.78 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '66'){
              this.answer = this.user_input * 10.92 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '67'){
              this.answer = this.user_input * 7.07 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '68'){
              this.answer = this.user_input * 12.04 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '69'){
              this.answer = this.user_input * 6.41 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '70'){
              this.answer = this.user_input * 9.52 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '15' && this.select3 === '71'){
              this.answer = this.user_input * 10.62 + ' lb';
            }
            else if(this.select1 === '6' && this.select2 === '16'){
              this.answer = this.user_input * 4 + ' qt';
            }
            else if(this.select1 === '6' && this.select2 === '17'){
              this.answer = this.user_input * 4.8 + ' qt';
            }
            else if(this.select1 === '6' && this.select2 === '18'){
              this.answer = this.user_input * 307.44;
            }
            else if(this.select1 === '6' && this.select2 === '19'){
              this.answer = this.user_input * 303.07;
            }
            else if(this.select1 === '6' && this.select2 === '20'){
              this.answer = this.user_input * 256;
            }
            else if(this.select1 === '6' && this.select2 === '21'){
              this.answer = this.user_input * 922.33;
            }
            else if(this.select1 === '6' && this.select2 === '22'){
              this.answer = this.user_input * 909.22;
            }
            else if(this.select1 === '6' && this.select2 === '23'){
              this.answer = this.user_input * 768;
            }
            else if(this.select1 === '6' && this.select2 === '24'){
              this.answer = this.user_input * 153.72 + ' fl oz';
            }
            else if(this.select1 === '7' && this.select2 === '1'){
              this.answer = this.user_input * 16;
            }
            else if(this.select1 === '7' && this.select2 === '2'){
              this.answer = this.user_input * 15.14;
            }
            else if(this.select1 === '7' && this.select2 === '3'){
              this.answer = this.user_input * 13.32;
            }
            else if(this.select1 === '7' && this.select2 === '4'){
              this.answer = this.user_input * 37.85 + ' dL';
            }
            else if(this.select1 === '7' && this.select2 === '5'){
              this.answer = this.user_input * 133.23 + ' fl oz';
            }
            else if(this.select1 === '7' && this.select2 === '6'){
              this.answer = this.user_input * 128 + ' fl oz';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '1'){
              this.answer = this.user_input * 3785.41 + ' g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '2'){
              this.answer = this.user_input * 2002.48 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '3'){
              this.answer = this.user_input * 1536.88 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '4'){
              this.answer = this.user_input * 2081.98 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '5'){
              this.answer = this.user_input *  + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '6'){
              this.answer = this.user_input * 2036.65 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '7'){
              this.answer = this.user_input * 2173.03 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '8'){
              this.answer = this.user_input * 4091.48 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '9'){
              this.answer = this.user_input * 3132.26 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '10'){
              this.answer = this.user_input * 3741.43 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '11'){
              this.answer = this.user_input * 3859.63 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '12'){
              this.answer = this.user_input * 2323.05 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '13'){
              this.answer = this.user_input * 4368.79 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '14'){
              this.answer = this.user_input * 6455.45 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '15'){
              this.answer = this.user_input * 6000.84 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '16'){
              this.answer = this.user_input * 2013.92 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '17'){
              this.answer = this.user_input * 4359.7 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '18'){
              this.answer = this.user_input * 4177.86 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '19'){
              this.answer = this.user_input * 4423.35 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '20'){
              this.answer = this.user_input * 4201.81 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '21'){
              this.answer = this.user_input * 4182.4 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '22'){
              this.answer = this.user_input * 4046.02 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '23'){
              this.answer = this.user_input * 4182.4 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '24'){
              this.answer = this.user_input * 4364.25 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '25'){
              this.answer = this.user_input * 4705.2 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '26'){
              this.answer = this.user_input * 5879.91 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '27'){
              this.answer = this.user_input * 4842.04 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '28'){
              this.answer = this.user_input * 4600.64 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '29'){
              this.answer = this.user_input * 4518.81 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '30'){
              this.answer = this.user_input * 2254.86 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '31'){
              this.answer = this.user_input * 4364.25 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '32'){
              this.answer = this.user_input * 2091.2 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '33'){
              this.answer = this.user_input * 2273.05 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '34'){
              this.answer = this.user_input * 1236.54 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '35'){
              this.answer = this.user_input * 2914.04 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '36'){
              this.answer = this.user_input * 2109.39 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '37'){
              this.answer = this.user_input * 2818.58 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '38'){
              this.answer = this.user_input * 2248.18 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '39'){
              this.answer = this.user_input * 2914.04 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '40'){
              this.answer = this.user_input * 2882.27 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '41'){
              this.answer = this.user_input * 4419.48 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '42'){
              this.answer = this.user_input * 3059.52 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '43'){
              this.answer = this.user_input * 3277.73 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '44'){
              this.answer = this.user_input * 3277.73 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '45'){
              this.answer = this.user_input * 3495.94 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '46'){
              this.answer = this.user_input * 3586.87 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '47'){
              this.answer = this.user_input * 1163.8 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '48'){
              this.answer = this.user_input * 2045.74 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '49'){
              this.answer = this.user_input * 2400.34 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '50'){
              this.answer = this.user_input * 3273.19 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '51'){
              this.answer = this.user_input * 2545.81 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '52'){
              this.answer = this.user_input * 2914.04 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '53'){
              this.answer = this.user_input * 1600.22 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '54'){
              this.answer = this.user_input * 2591.27 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '55'){
              this.answer = this.user_input * 2923.14 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '56'){
              this.answer = this.user_input * 3248.64 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '57'){
              this.answer = this.user_input * 4818.86 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '58'){
              this.answer = this.user_input * 6059.94 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '59'){
              this.answer = this.user_input * 4304.19 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '60'){
              this.answer = this.user_input * 4136.94 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '61'){
              this.answer = this.user_input * 1963.91 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '62'){
              this.answer = this.user_input * 1382.01 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '63'){
              this.answer = this.user_input * 5455.31 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '64'){
              this.answer = this.user_input * 3423.21 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '65'){
              this.answer = this.user_input * 2623.09 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '66'){
              this.answer = this.user_input * 4955.24 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '67'){
              this.answer = this.user_input * 3204.99 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '68'){
              this.answer = this.user_input * 5459.85 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '69'){
              this.answer = this.user_input * 2909.5 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '70'){
              this.answer = this.user_input * 4318.79 + 'g';
            }
            else if(this.select1 === '7' && this.select2 === '8' && this.select3 === '71'){
              this.answer = this.user_input * 4818.86 + 'g';
            }
            else if(this.select1 === this.select2){
              this.answer = this.user_input;
            }
            else{
              alert(this.select1 + ' ' + this.select2);
            }
          }
    }
  }
}
</script>
<style media="screen" scoped>
body,h1,h2,h3,h4,h5,h6 {font-family: "Raleway", Arial, Helvetica, sans-serif}
</style>
