<template>
  <el-form :model="form" ref="form" label-width="110px">
    <el-row class="row-index">
      <el-col :span="2" class="left-col bold"> 生活方面</el-col>
      <el-col :span="18" class="right-col">
        <el-row>
          <el-col :span="24">
            <el-form-item label="健康指导处方" prop="jkzdCf">
              <el-input v-model="form.jkzdCf" size="small"></el-input>
            </el-form-item>
          </el-col>
        </el-row>
        <el-row>
          <el-col :span="12">
            <el-form-item label="进餐" prop="shfmJc">
              <el-input v-model="form.shfmJc" size="small"></el-input>
            </el-form-item>
          </el-col>
          <el-col :span="12">
            <el-form-item label="梳洗" prop="shfmSx">
              <el-input v-model="form.shfmSx" size="small"></el-input>
            </el-form-item>
          </el-col>
        </el-row>
        <el-row>
          <el-col :span="12">
            <el-form-item label="穿衣" prop="shfmCy">
              <el-input v-model="form.shfmCy" size="small"></el-input>
            </el-form-item>
          </el-col>
          <el-col :span="12">
            <el-form-item label="如厕" prop="shfmRc">
              <el-input v-model="form.shfmRc" size="small"></el-input>
            </el-form-item>
          </el-col>
        </el-row>
        <el-row>
          <el-col :span="12">
            <el-form-item label="活动" prop="shfmHd">
              <el-input v-model="form.shfmHd" size="small"></el-input>
            </el-form-item>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
  </el-form>
</template>

<script>
// import * from ''
export default {
  name: "",
  components: {},
  props: {},
  data() {
    return {
      form: {
        jkzdCf: "",
        shfmJc: "",
        shfmSx:"",
        shfmCy: "",
        shfmRc: "",
        shfmHd: "",
      }
    };
  },
  computed: {},
  watch: {},
  mounted() {},
  methods: {},
};
</script>

<style lang="scss">
</style>
