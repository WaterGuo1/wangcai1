<template>
  <Layout> 编辑标签 </Layout>
</template>

 <script lang= "ts">
import Vue from "vue";
import { Component } from "vue-property-decorator";
import { model as tagListModel } from "@/models/tagListModel";
// import path from "path";

@Component
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