<template>
  <el-form :model="form" :inline="true" ref="form" label-width="110px">
    <el-row class="row-index">
      <el-col :span="2" class="left-col bold"> 生活方式</el-col>
      <el-col :span="21" class="right-col">
        <!-- 体育锻炼 -->
        <el-row class="border_bottom" align="middle"  type="flex">
          <el-col :span="2" class="flex_center bold">体育锻炼</el-col>
          <el-col :span="21" class="border_left">

            <el-row class="border_bottom">
              <el-form-item label="锻炼频率" prop="shfs_tydl_dlpl">
                <el-radio-group v-model="form.shfs_tydl_dlpl">
                  <el-radio
                    v-for="label in dlpl"
                    :key="label"
                    :label="label "
                    >{{ label }}</el-radio
                  >
                </el-radio-group>
              </el-form-item>
            </el-row>

            <el-row class="border_bottom">
              <el-col :span="12">
                <el-form-item label="每次锻炼时间" prop="shfs_tydl_mcdlsj">
                  <el-input
                    v-model="form.shfs_tydl_mcdlsj"
                    placeholder="请输入内容"
                    size="small"
                  ></el-input>
                </el-form-item>
              </el-col>
              <el-col :span="12" class="border_left">
                <el-form-item label="每次锻炼时间" prop="shfs_tydl_jcdlsj">
                  <el-input
                    v-model="form.shfs_tydl_jcdlsj"
                    placeholder="请输入内容"
                    size="small"
                  ></el-input>
                </el-form-item>
              </el-col>
            </el-row>

            <el-row>
              <el-form-item label="锻炼方式" prop="shfs_tydl_dlfs">
                <el-radio-group v-model="form.shfs_tydl_dlfs">
                  <el-radio
                    v-for="label in dlfs"
                    :key="label"
                    :label="label "
                    >{{ label }}</el-radio
                  >
                  <template v-if="form.shfs_tydl_dlfs === '其他'">
                    <span style="font-size: 12px"></span><el-input v-model="form.shfs_tydl_dlfs_qt" placeholder="请输入内容" size="small" style="width: 200px; display: inline-block"></el-input>
                  </template>
                </el-radio-group>
              </el-form-item>
            </el-row>

          </el-col>
        </el-row>

        <!-- 饮食习惯 -->
        <el-row class="border_bottom" align="middle"  type="flex">
          <el-col :span="2" class="flex_center bold" type="flex">饮食习惯</el-col>
          <el-col :span="21" class="border_left">
              <el-form-item prop="shfs_ysxg" label="饮食习惯">
                <el-radio-group v-model="form.shfs_ysxg">
                  <el-radio
                    v-for="label in ysxg"
                    :key="label"
                    :label="label "
                    >{{ label }}</el-radio
                  >
                </el-radio-group>
              </el-form-item>
          </el-col>
        </el-row>

        <!-- 吸烟情况 -->
        <el-row class="border_bottom" align="middle"  type="flex">
          <el-col :span="2" class="flex_center bold" type="flex">吸烟情况</el-col>
          <el-col :span="21" class="border_left">
            <el-row class="border_bottom">
              <el-form-item label="吸烟状况" prop="shfs_xyqk_xyzk">
                <el-radio-group v-model="form.shfs_xyqk_xyzk">
                  <el-radio
                    v-for="label in xyqk"
                    :key="label"
                    :label="label "
                    >{{ label }}</el-radio
                  >
                </el-radio-group>
              </el-form-item>
            </el-row>

            <el-row class="border_bottom">
              <el-form-item label="日吸烟量" prop="shfs_xyqk_rxyl">
                <span style="font-size: 12px">平均 </span>
                <el-input v-model="form.shfs_xyqk_rxyl" placeholder="请输入内容"
                 size="small" style="width: 100px; display: inline-block"></el-input>
                <span style="font-size: 12px"> 支</span>
              </el-form-item>
            </el-row>


            <el-row class="">
              <el-col :span="12">
                <el-form-item label="开始吸烟年龄" prop="shfs_xyqk_ksxynl">
                  <span style="font-size: 12px"> </span>
                  <el-input v-model="form.shfs_xyqk_ksxynl" placeholder="请输入内容"
                  size="small" style="width: 100px; display: inline-block"></el-input>
                  <span style="font-size: 12px"> 岁</span>
                </el-form-item>
              </el-col>
              <el-col :span="12" class="border_left">
                <el-form-item label="戒烟年龄" prop="shfs_xyqk_jynl">
                  <span style="font-size: 12px"></span>
                  <el-input v-model="form.shfs_xyqk_jynl" placeholder="请输入内容"
                  size="small" style="width: 100px; display: inline-block"></el-input>
                  <span style="font-size: 12px"> 岁</span>
                </el-form-item>
              </el-col>
            </el-row>

          </el-col>
        </el-row>

        <!-- 饮酒情况 -->
        <el-row class="border_bottom" align="middle"  type="flex">
          <el-col :span="2" class="flex_center bold" type="flex">饮酒情况</el-col>
          <el-col :span="21" class="border_left">
            <el-row class="border_bottom">
              <el-form-item label="饮酒频率" prop="shfs_yjqk_yjpl">
                <el-radio-group v-model="form.shfs_yjqk_yjpl">
                  <el-radio
                    v-for="label in yjpl"
                    :key="label "
                    :label="label "
                    >{{ label }}</el-radio
                  >
                </el-radio-group>
              </el-form-item>
            </el-row>

            <el-row class="border_bottom">
              <el-form-item label="日饮酒量" prop="shfs_yjqk_ryjl">
                <span style="font-size: 12px">平均 </span>
                <el-input v-model="form.shfs_yjqk_ryjl" placeholder="请输入内容"
                 size="small" style="width: 100px; display: inline-block"></el-input>
                <span style="font-size: 12px"> 两</span>
              </el-form-item>
            </el-row>


            <el-row class="border_bottom">
              <el-form-item label="是否戒酒" prop="shfs_yjqk_sfjj">
                <el-radio-group v-model="form.shfs_yjqk_sfjj">
                  <el-radio
                    v-for="label in sfjj"
                    :key="label "
                    :label="label "
                    >{{ label }}</el-radio
                  >
                  <template v-if="form.shfs_yjqk_sfjj === '已戒酒'">
                    <span style="font-size: 12px">，戒酒年龄 </span><el-input v-model="form.shfs_yjqk_jjnl" placeholder="请输入内容" size="small" style="width: 200px; display: inline-block"></el-input>
                  </template>
                </el-radio-group>
              </el-form-item>
            </el-row>

            <el-row class="border_bottom">
              <el-col :span="12">
                <el-form-item label="开始饮酒年龄" prop="shfs_yjqk_ksyjnl">
                  <span style="font-size: 12px"> </span>
                  <el-input v-model="form.shfs_yjqk_ksyjnl" placeholder="请输入内容"
                  size="small" style="width: 100px; display: inline-block"></el-input>
                  <span style="font-size: 12px"> 岁</span>
                </el-form-item>
              </el-col>
              <el-col :span="12" class="border_left">
                <el-form-item label="近一年内是否曾醉酒" prop="shfs_yjqk_jynnsfczj" label-width="150px">
                  <el-radio-group v-model="form.shfs_yjqk_jynnsfczj">
                    <el-radio label="是" ></el-radio>
                    <el-radio label="否" ></el-radio>
                  </el-radio-group>
                </el-form-item>
              </el-col>
            </el-row>

            <el-row class="">
              <el-form-item label="饮酒种类" prop="shfs_yjqk_yjzl">
                <el-checkbox-group v-model="form.shfs_yjqk_yjzl">
                  <el-checkbox
                    v-for="label in yjzl"
                    :key="label "
                    :label="label "
                    >{{ label }}</el-checkbox>
                  <template v-if="form.shfs_yjqk_yjzl.indexOf('其他') !== -1">
                    <span style="font-size: 12px"> </span><el-input v-model="form.shfs_yjqk_yjzl_qt" placeholder="请输入内容" size="small" style="width: 200px; display: inline-block"></el-input>
                  </template>
                </el-checkbox-group>
              </el-form-item>
            </el-row>
          </el-col>
        </el-row>

        <!-- 职业病危害因素接触史 -->
        <el-row class="" align="middle"  type="flex">
          <el-col :span="2" class="flex_center bold" type="flex">职业病危害因素接触史</el-col>
          <el-col :span="21" class="border_left">
            <el-row class="border_bottom"  align="middle"  type="flex">
              <el-col :span="7">
                <el-form-item prop="shfs_zybwhysjcs_yw" label="是否有接触史">
                  <el-radio-group v-model="form.shfs_zybwhysjcs_yw">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
                </el-form-item>
              </el-col>
              <el-col :span="16" class="flex_align_center">
                <span>(</span>
                <el-form-item prop="shfs_zybwhysjcs_gz" label="工种" label-width="40px">
                  <el-input v-model="form.shfs_zybwhysjcs_gz" placeholder="请输入内容" size="small"
                  style="width: 200px"></el-input>
                </el-form-item>
                <el-form-item prop="shfs_zybwhysjcs_cysjn" label="从业时间年"  label-width="100px">
                  <el-input v-model="form.shfs_zybwhysjcs_cysjn" placeholder="请输入内容" size="small"
                  style="width: 200px"></el-input>
                </el-form-item>
                <span>)</span>
              </el-col>
            </el-row>

            <el-row class="border_bottom"  align="middle"  type="flex">
              <el-form-item prop="shfs_zybwhysjcs_fc" label="粉 尘" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_fc">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_fcffcs" label="防护措施" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_fcffcs">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_fcffcsms" label-width="0" inline>
                <el-input v-model="form.shfs_zybwhysjcs_fcffcsms" placeholder="请输入内容" size="small"
                style="width: 400px"></el-input>
              </el-form-item>
            </el-row>

            <el-row class="border_bottom"  align="middle"  type="flex">
              <el-form-item prop="shfs_zybwhysjcs_fswz" label="放射物质" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_fswz">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_fswzffcs" label="防护措施" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_fswzffcs">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_fswzffcsms" label-width="0" inline>
                <el-input v-model="form.shfs_zybwhysjcs_fswzffcsms" placeholder="请输入内容" size="small"
                style="width: 400px"></el-input>
              </el-form-item>
            </el-row>

            <el-row class="border_bottom"  align="middle"  type="flex">
              <el-form-item prop="shfs_zybwhysjcs_wlys" label="物理因素" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_wlys">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_wlysffcs" label="防护措施" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_wlysffcs">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_wlysffcsms" label-width="0" inline>
                <el-input v-model="form.shfs_zybwhysjcs_wlysffcsms" placeholder="请输入内容" size="small"
                style="width: 400px"></el-input>
              </el-form-item>
            </el-row>

            <el-row class="border_bottom"  align="middle"  type="flex">
              <el-form-item prop="shfs_zybwhysjcs_hxwz" label="化学物质" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_hxwz">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_hxwzffcs" label="防护措施" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_hxwzffcs">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_hxwzffcsms" label-width="0" inline>
                <el-input v-model="form.shfs_zybwhysjcs_hxwzffcsms" placeholder="请输入内容" size="small"
                style="width: 400px"></el-input>
              </el-form-item>
            </el-row>

            <el-row class=""  align="middle"  type="flex">
              <el-form-item prop="shfs_zybwhysjcs_qt" label="化学物质" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_qt">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_qtffcs" label="防护措施" inline>
                  <el-radio-group v-model="form.shfs_zybwhysjcs_qtffcs">
                    <el-radio label="无">无</el-radio>
                    <el-radio label="有">有</el-radio>
                  </el-radio-group>
              </el-form-item>
              <el-form-item prop="shfs_zybwhysjcs_qtffcsms" label-width="0" inline>
                <el-input v-model="form.shfs_zybwhysjcs_qtffcsms" placeholder="请输入内容" size="small"
                style="width: 400px"></el-input>
              </el-form-item>
            </el-row>
          </el-col>
        </el-row>

      </el-col>
    </el-row>
  </el-form>
</template>

<script>
import { ShengHuoFangShi, boolean } from "@/utils/dict";

export default {
  name: "",
  components: {},
  props: {},
  data() {
    return {
      form: {
        shfs_tydl_dlpl: "", // 生活方式-体育锻炼-锻炼频率
        shfs_tydl_mcdlsj: "", // 每次锻炼时间
        shfs_tydl_jcdlsj: "", // 坚持锻炼时间
        shfs_tydl_dlfs: "", // 锻炼方式
        shfs_tydl_dlfs_qt: "", // 锻炼方式-其他
        shfs_ysxg: "", // 饮食习惯
        shfs_xyqk_xyzk: "", // 吸烟状况
        shfs_xyqk_rxyl: "", // 日吸烟量
        shfs_xyqk_ksxynl: "", // 开始吸烟年龄
        shfs_xyqk_jynl: "", // 戒烟年龄

        shfs_yjqk_yjpl: "", // 饮酒频率
        shfs_yjqk_ryjl: "", // 日饮酒量
        shfs_yjqk_sfjj: "", // 是否戒酒
        shfs_yjqk_jjnl: "", // 戒酒年龄
        shfs_yjqk_ksyjnl: "", // 开始饮酒年龄
        shfs_yjqk_jynnsfczj: "", // 近一年内是否曾醉酒
        shfs_yjqk_yjzl: [], // 饮酒种类
        shfs_yjqk_yjzl_qt: "", // 饮酒种类-其他

        shfs_zybwhysjcs_yw: "", // 有无",
        shfs_zybwhysjcs_gz: "", // 工种",
        shfs_zybwhysjcs_cysjn: "", // 从业时间年",
        shfs_zybwhysjcs_fc: "", // 粉尘",
        shfs_zybwhysjcs_fcffcs: "", // 粉尘防范措施",
        shfs_zybwhysjcs_fcffcsms: "", // 粉尘防范措施描述",
        shfs_zybwhysjcs_fswz: "", // 放射物质",
        shfs_zybwhysjcs_fswzffcs: "", // 放射物质防范措施",
        shfs_zybwhysjcs_fswzffcsms: "", // 放射物质防范措施描述",
        shfs_zybwhysjcs_wlys: "", // 物理因素",
        shfs_zybwhysjcs_wlysffcs: "", // 物理因素防范措施",
        shfs_zybwhysjcs_wlysffcsms: "", // 物理因素防范措施描述",
        shfs_zybwhysjcs_hxwz: "", // 化学物质",
        shfs_zybwhysjcs_hxwzffcs: "", // 化学物质防范措施",
        shfs_zybwhysjcs_hxwzffcsms: "", // 化学物质防范措施描述",
        shfs_zybwhysjcs_qt: "", // 其他",
        shfs_zybwhysjcs_qtffcs: "", // 其他防范措施",
        shfs_zybwhysjcs_qtffcsms: "", // 其他防范措施描述",
      },
      dlpl: ShengHuoFangShi.dlpl, //锻练频率
      dlfs: ShengHuoFangShi.dlfs, // 锻炼方式
      ysxg: ShengHuoFangShi.ysxg, // 饮食习惯
      xyqk: ShengHuoFangShi.xyqk, // 吸烟状况
      yjpl: ShengHuoFangShi.yjpl, // 吸烟状况
      sfjj: ShengHuoFangShi.sfjj, // 是否戒酒
      yjzl: ShengHuoFangShi.yjzl, // 是否戒酒
      boolean
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
