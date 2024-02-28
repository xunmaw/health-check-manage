<template>
  <el-form :model="form" ref="form" label-width="60px">
    <el-row class="row-index">
      <el-col :span="2" class="left-col bold">健康评价</el-col>
      <el-col :span="18" class="right-col">
        <el-row>
          <el-col :span="20">
            <el-form-item label-width="0" label="" prop="jkpj_sfyc">
              <el-radio-group v-model="form.jkpj_sfyc">
                <el-radio label="体检无异常">体检无异常</el-radio>
                <el-radio label="有异常">有异常</el-radio>
              </el-radio-group>
            </el-form-item>
          </el-col>
          <el-col :span="4" style="text-align: right">
            <el-button
              class="mr16 ml16 mt8"
              type="primary"
              round
              icon="el-icon-s-opportunity"
              @click="calculate"
              >智能计算</el-button
            >
          </el-col>
        </el-row>
        <el-form-item label="异常1" prop="jkpj_yc1">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc1"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常2" prop="jkpj_yc2">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc2"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常3" prop="jkpj_yc3">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc3"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常4" prop="jkpj_yc4">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc4"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常5" prop="jkpj_yc5">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc5"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常6" prop="jkpj_yc6">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc6"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常7" prop="jkpj_yc7">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc7"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常8" prop="jkpj_yc8">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc8"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常9" prop="jkpj_yc9">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc9"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常10" prop="jkpj_yc10">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc10"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常11" prop="jkpj_yc11">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc11"
          ></el-input>
        </el-form-item>
        <el-form-item label="异常12" prop="jkpj_yc12">
          <el-input
            type="text"
            :disabled="form.jkpj_sfyc == '体检无异常'"
            v-model="form.jkpj_yc12"
          ></el-input>
        </el-form-item>
      </el-col>
    </el-row>
  </el-form>
</template>

<script>
import { getAbnormalInfo } from "@/http/detail";
import { _toCamel } from "@/utils/index";
import { Array_Prefix } from "@/constant";

export default {
  name: "",
  components: {},
  props: {
    getAllFormData: {
      type: Function,
      default: () => {
        return {};
      },
    },
  },
  data() {
    return {
      form: {
        jkpj_sfyc: "",
        jkpj_yc1: "",
        jkpj_yc2: "",
        jkpj_yc3: "",
        jkpj_yc4: "",
        jkpj_yc5: "",
        jkpj_yc6: "",
        jkpj_yc7: "",
        jkpj_yc8: "",
        jkpj_yc9: "",
        jkpj_yc10: "",
        jkpj_yc11: "",
        jkpj_yc12: "",
      },
      other: "",
      zhengzhuang: [],
    };
  },
  computed: {},
  watch: {},
  mounted() {},
  methods: {
    calculate() {
      this.$confirm("此操作将覆盖已填写的异常内容, 是否继续?", "提示", {
        confirmButtonText: "确定",
        cancelButtonText: "取消",
        type: "warning",
      }).then(() => {
        this.submitCalculate();
      });
    },
    async submitCalculate() {
      this.loading = true;
      const res = await getAbnormalInfo(this.getAllFormData());
      this.loading = false;
      if (res.success) {
        console.log(res, Array_Prefix);
        const result = res.result;
        for (const _key in this.form) {
          const key = _toCamel(_key);
          const value = result[key];
          this.form[_key] = value ? value.replace(Array_Prefix, "") : value;
        }
      }
    },
  },
};
</script>

<style lang="scss"></style>
