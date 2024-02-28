<template>
  <el-form :model="form" ref="form" label-width="0">
    <el-row class="row-index">
      <el-col :span="2" class="left-col bold">危险因素控制</el-col>
      <el-col :span="18" class="right-col">
        <el-form-item label="" prop="jkzd">
          <el-checkbox-group v-model="form.wxyskz_zt">
            <el-col v-for="item in jrList" :key="item" :span="12">
              <el-checkbox :label="item">
                <span v-if="item == '减体重'">
                  减体重, (目标
                  <el-input v-model="form.wxyskz_jtzmbb" size="small" type="text" class="w200px"></el-input>
                  kg)
                </span>
                <span v-if="item == '建议接种疫苗'">
                  建议接种疫苗：<el-input v-model="form.wxyskz_jyjzym" size="small" type="text" class="w200px"></el-input>
                </span>
                <span v-if="item == '其他'">
                  其他：<el-input size="small" v-model="form.wxyskz_qt"  type="text" class="w200px"></el-input>
                </span>
              </el-checkbox>
            </el-col>
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
      jrList: [
        "戒烟",
        "健康饮酒",
        "饮食",
        "锻炼",
        "减体重",
        "建议接种疫苗",
        "其他",
        "减腰围",
      ],
      form: {
        wxyskz_zt: [],
        wxyskz_jtzmbb: '',
        wxyskz_jyjzym: '',
        wxyskz_qt: '',
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
