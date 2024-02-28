<template>
  <el-form :model="form" ref="form" label-width="0">
    <el-row class="row-index">
      <el-col :span="2" class="left-col bold">健康指导</el-col>
      <el-col :span="18" class="right-col">
        <el-form-item label="" prop="jkzd_zt">
          <el-checkbox-group v-model="form.jkzd_zt">
            <el-checkbox
              v-for="item in jrList"
              :key="item"
              :label="item"
            ></el-checkbox>
              <span v-if="form.jkzd_zt.indexOf('其他') !== -1 ">
                其他：<el-input size="small" v-model="form.jkpj_qt"  type="text" class="w200px"></el-input>
              </span>
          </el-checkbox-group>
        </el-form-item>
      </el-col>
    </el-row>
  </el-form>
</template>

<script>
export default {
  name: "",
  components: {},
  props: {},
  data() {
    return {
      jrList: ["纳入慢性病患者健康管理", "建议复查", "建议转诊", "其他"],
      form: {
        jkzd_zt: [],
        jkpj_qt: '',
      },
    };
  },
  computed: {},
  watch: {},
  mounted() {},
  methods: {},
};
</script>

<style lang="scss"></style>
