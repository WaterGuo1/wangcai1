<template>
  <div>
    {{value}}
    <label class="formItem">
      
      <span class="name">{{this.fieldName}}</span>
      <input type="text"
       v-model="value"
      :placeholder="this.placeholder">
    </label>
  </div>
</template>

<script lang="ts">

 import Vue from 'vue';
 import { Component,Prop,Watch } from 'vue-property-decorator';
 @Component
 export default class FormItem extends Vue{
value= '';

@Prop({required:true}) fieldName!:string;
@Prop() placeholder?: string;

@Watch('value')
onValueChanged(value:string){
  this.$emit('update:value',value)
}

 }
</script>

<style lang="scss" scoped>
  .formItem {
    background:white;
    font-size: 14px;
    padding-left: 16px;
    display: flex;
    align-items: center;
    .name {
      padding-right: 16px;
    }
    input {
      height: 40px;
      flex-grow: 1;
      background: transparent;
      border: none;
      padding-right: 16px;
    }
  }
</style>