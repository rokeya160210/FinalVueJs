<template>
  <div class="wrapper">
    
    
    
    <h2>Price Picker Slider : {{ slider2 }}</h2>
    <custom-slider min="0" max="1000" step="50" v-model="slider2"/>
  </div>
</template>

<script>
import CustomSlider from "vue-custom-range-slider";
import "vue-custom-range-slider/dist/vue-custom-range-slider.css";

export default {
    components:{CustomSlider},
  data() {
    return {
      slider: "a",
      slider2: "100",
      sliderValues: [
        {
          label: "Not at all",
          value: "0"
        },
        {
          label: "A tiny bit",
          value: "100"
        },
        {
          label: "Its ok",
          value: "c"
        },
        {
          label: "Its very good",
          value: "d"
        },
        {
          label: "Its AMAZING!",
          value: "e"
        }
      ]
    };
  }
};
</script>

<style>
.wrapper {
  padding: 50px;
  font-family: "Courier New", Courier, monospace;
}
</style>