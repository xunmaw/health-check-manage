<template>
  <el-form :model="form" ref="form" label-width="0">
    <el-row class="row-index">
      <el-col :span="2" class="left-col bold">现存主要<br/>健康问题</el-col>
      <el-col :span="21" class="right-col">
        <el-row class="border_bottom" align="middle" type="flex">
          <el-col :span="2" class="bold flex_center">脑血管疾病</el-col>
          <el-col :span="21" class="p-20 border_left">
            <el-checkbox-group v-model="form.xczyjkwt_nxgjb">
              <el-checkbox label="未发现">未发现</el-checkbox>
              <el-checkbox label="缺血性卒中">缺血性卒中</el-checkbox>
              <el-checkbox label="脑出血">脑出血</el-checkbox>
              <el-checkbox label="蛛网膜下腔出血">蛛网膜下腔出血</el-checkbox>
              <el-checkbox label="短暂性脑块血发作"
                >短暂性脑块血发作</el-checkbox
              >
              <el-checkbox label="其他">
                其他：<el-input v-model="form.xczyjkwt_nxgjb_qt" type="text" />
              </el-checkbox>
            </el-checkbox-group>
          </el-col>
        </el-row>

        <el-row class="border_bottom" align="middle" type="flex">
          <el-col :span="2" class="bold flex_center">肾脏疾病</el-col>
          <el-col :span="21" class="p-20 border_left">
            <el-checkbox-group v-model="form.xczyjkwt_szjb">
              <el-checkbox label="未发现">未发现</el-checkbox>
              <el-checkbox label="糖尿病肾病">糖尿病肾病</el-checkbox>
              <el-checkbox label="肾功能衰竭">肾功能衰竭</el-checkbox>
              <el-checkbox label="急性肾炎">急性肾炎</el-checkbox>
              <el-checkbox label="慢性肾炎">慢性肾炎</el-checkbox>
              <el-checkbox label="其他">
                其他：<el-input v-model="form.xczyjkwt_szjb_qt" type="text" />
              </el-checkbox>
            </el-checkbox-group>
          </el-col>
        </el-row>

        <el-row class="border_bottom" align="middle" type="flex">
          <el-col :span="2" class="bold flex_center">心脏疾病</el-col>
          <el-col :span="21" class="p-20 border_left">
            <el-checkbox-group v-model="form.xczyjkwt_xzjb">
              <el-checkbox label="未发现">未发现</el-checkbox>
              <el-checkbox label="心肌梗死">心肌梗死</el-checkbox>
              <el-checkbox label="心绞痛">心绞痛</el-checkbox>
              <el-checkbox label="冠状动脉血运重建"
                >冠状动脉血运重建</el-checkbox
              >
              <el-checkbox label="充血性心力衰竭">充血性心力衰竭</el-checkbox>
              <el-checkbox label="心前区疼痛">心前区疼痛</el-checkbox>
              <el-checkbox label="其他">
                其他：<el-input v-model="form.xczyjkwt_xzjb_qt" type="text" />
              </el-checkbox>
            </el-checkbox-group>
          </el-col>
        </el-row>

        <el-row class="border_bottom" align="middle" type="flex">
          <el-col :span="2" class="bold flex_center">血管疾病</el-col>
          <el-col :span="21" class="p-20 border_left">
            <el-checkbox-group v-model="form.xczyjkwt_xgjb">
              <el-checkbox label="未发现">未发现</el-checkbox>
              <el-checkbox label="夹层动脉瘤">夹层动脉瘤</el-checkbox>
              <el-checkbox label="动脉闭塞性疾病">动脉闭塞性疾病</el-checkbox>
              <el-checkbox label="其他">
                其他：<el-input v-model="form.xczyjkwt_xgjb_qt" type="text" />
              </el-checkbox>
            </el-checkbox-group>
          </el-col>
        </el-row>

        <el-row class="border_bottom" align="middle" type="flex">
          <el-col :span="2" class="bold flex_center">眼部疾病</el-col>
          <el-col :span="21" class="p-20 border_left">
            <el-checkbox-group v-model="form.xczyjkwt_ybjb">
              <el-checkbox label="未发现">未发现</el-checkbox>
              <el-checkbox label="视网膜出血或渗出"
                >视网膜出血或渗出</el-checkbox
              >
              <el-checkbox label="视乳头水肿">视乳头水肿</el-checkbox>
              <el-checkbox label="白内障">白内障</el-checkbox>
              <el-checkbox label="其他">
                其他：<el-input v-model="form.xczyjkwt_ybjb_qt" type="text" />
              </el-checkbox>
            </el-checkbox-group>
          </el-col>
        </el-row>

        <el-row class="border_bottom" align="middle" type="flex">
          <el-col :span="2" class="bold flex_center">神经系统疾病</el-col>
          <el-col :span="21" class="p-20 border_left">
            <el-checkbox-group v-model="form.xczyjkwt_sjxtjb">
              <el-checkbox label="未发现">未发现</el-checkbox>
              <el-checkbox label="有">
                有：<el-input v-model="form.xczyjkwt_sjxtjb_qt" type="text" />
              </el-checkbox>
            </el-checkbox-group>
          </el-col>
        </el-row>

        <el-row class="" align="middle" type="flex">
          <el-col :span="2" class="bold flex_center">其他系统疾病</el-col>
          <el-col :span="21" class="p-20 border_left">
            <el-checkbox-group v-model="form.xczyjkwt_qtxtjb">
              <el-checkbox label="未发现">未发现</el-checkbox>
              <el-checkbox label="有">
                有：<el-input v-model="form.xczyjkwt_qtxtjb_qt" type="text" />
              </el-checkbox>
            </el-checkbox-group>
          </el-col>
        </el-row>
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
      form: {
        xczyjkwt_nxgjb: [],
        xczyjkwt_nxgjb_qt: "",
        xczyjkwt_szjb: [],
        xczyjkwt_szjb_qt: "",
        xczyjkwt_xzjb: [],
        xczyjkwt_xzjb_qt: "",
        xczyjkwt_xgjb: [],
        xczyjkwt_xgjb_qt: "",
        xczyjkwt_ybjb: [],
        xczyjkwt_ybjb_qt: "",
        xczyjkwt_sjxtjb: [],
        xczyjkwt_sjxtjb_qt: "",
        xczyjkwt_qtxtjb: [],
        xczyjkwt_qtxtjb_qt: "",
      },
    };
  },
  computed: {},
  watch: {},
  mounted() {},
  methods: {},
};
</script>

<style>
.p-20 {
  padding: 20px;
}
</style>
