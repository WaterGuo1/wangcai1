
<template>
  <Layout>
    <div>
      <icon name="left"/>
      <span>
        编辑标签
      </span>
    </div>
    <FormItem field-name="标签名" placeholder="请输入标签名"/>
    <Button>删除标签</Button>
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
</style>