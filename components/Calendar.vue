<template>
     <div id="wrapper">
         <ejs-daterangepicker id="daterangepicker" :placeholder="waterMarkText" :min="minDate" :max="maxDate"></ejs-daterangepicker>
    </div>
</template>
<script>
import Vue from 'vue';
import { DateRangePickerPlugin } from '@syncfusion/ej2-vue-calendars';

Vue.use(DateRangePickerPlugin);

export default {
   data () {
     return {
         waterMark : 'Select a Range'
        }
    },
    methods: {
        disableDate: function(args) {
            if (args.date.getDay() === 0 || args.date.getDay() === 6) {
             args.isDisabled = true;
            }
        }
    }

}
</script>
<style>
#wrapper {
  max-width: 246px;
  margin: 30px auto;
  padding-top: 15px;
}
</style>