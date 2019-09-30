<template>
  <input type="text" class="box" :value="value" @input="updateValue($event.target.value)">
</template>

<script>
    export default {
        props:['value'],
        methods:{
            updateValue(value){
                this.$emit('input',value);
            }
        }
    }
</script>

<style scoped>
  input {
    border-radius: 0px !important;
    border: none;
    width: 70px!important;
    height: 70px!important;
    text-align: center;
  }
</style>
