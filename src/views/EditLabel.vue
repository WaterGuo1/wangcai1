
<template>
  <Layout>
    <div class="navBar">
      <icon class="leftIcon" name="left"/>
      <span class="title">
        编辑标签
      </span>
      <span class="rightIcon"></span>
    </div>
    <div class="form-wrapper">
    <FormItem field-name="标签名" placeholder="请输入标签名"/>

    </div>
    <div class="button-wrapper">
          <Button>删除标签</Button>

    </div>
  </Layout>
</template>
<script lang= "ts">
import Vue from "vue";
import { Component } from "vue-property-decorator";
import { model as tagListModel } from "@/models/tagListModel";
import icon from '@/components/icon.vue';
import FormItem from '../components/Money/FormItem.vue';
import Button from '../components/Money/Button.vue';


@Component({
  components: {icon,FormItem,Button}
})
export default class EditLabel extends Vue {
  created() {
    const id = this.$route.params.id;
    tagListModel.fetch();
    const tags = tagListModel.data;
    const tag = tags.filter((t) => t.id === id)[0];
          

    if (tag) {
      console.log(tag);
      console.log(1);
    } else {
      this.$router.replace("/404");
    }
  }
}
</script>

 

 <style lang= "scss" scoped>
.navBar{
   text-align: center;
   font-size: 16px;
   padding: 12px 16px;
   background:white;
   display: flex;
   align-items: center;
   justify-content: space-between;
   > .title{


   }
   >.leftIcon{
    width: 24px;
    height: 24px;


   }>.rightIcon{

    width: 24px;
    height: 24px;


   }
   
}
.form-wrapper{
  background:white;
  margin-top: 8px;
}
.button-wrapper{
   text-align: center;
   padding: 16px;
   margin-top: 28px;;

}
 
</style>