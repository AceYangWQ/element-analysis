<template>
  <div id="app">
    <router-view/>
<!--     <ElAlert title="这是一个alert" show-icon description="this is description">1</ElAlert>
    <el-button type="primary" icon="edit" :disabled="true" @click="clickbtn">按钮</el-button>

    <label>
      <input type="radio" name="" id="" value="1" v-model="a">测试label</label>
    <label>
      <input type="radio" name="" id="" value="2" v-model="a">2222222222</label> -->

    <!-- <el-checkbox-group v-model="checkList"> -->
      <!-- <el-checkbox v-model="a" label="aaa" true-label="trueA" false-label="falseA"></el-checkbox> -->
      <!-- <el-checkbox true-label="trueB" false-lable="falseB"></el-checkbox> -->
      <!-- <el-checkbox true-label="trueC" false-lable="falseC"></el-checkbox> -->
      <!-- <el-checkbox true-label="true禁用" false-lable="false禁用" disabled></el-checkbox> -->
      <!-- <el-checkbox label="选中且禁用" true-label="true选中且禁用" false-lable="false选中且禁用"  disabled></el-checkbox> -->
    <!-- </el-checkbox-group> -->


<!--     <label><input type="checkbox" value="1" v-model="testcheckbox">11111111</label>
    <label><input type="checkbox" value="2" v-model="testcheckbox">1111</label>
    <label><input type="checkbox" value="3444" v-model="testcheckbox">1111111111</label>

    <input type="text" v-model="theInputValue">
    <input type="text" :value="theInputValue" @input="handleInput"> -->
    <test-model v-model="value"></test-model>
    <el-upload
  class="upload-demo"
  action="https://jsonplaceholder.typicode.com/posts/"
  :on-preview="handlePreview"
  :on-remove="handleRemove"
  :file-list="fileList">
  <el-button size="small" type="primary">点击上传</el-button>
  <div slot="tip" class="el-upload__tip">只能上传jpg/png文件，且不超过500kb</div>
</el-upload>


  </div>

</template>

<script>
import testModel from './components/model.vue'
export default {
  name: 'app',
  data(){
    return {
      checkList:[],
      a:'',
      selfModel:'',
      theInputValue:1,
      preValue:1,
      value:true,
      fileList: [{name: 'food.jpeg', url: 'https://fuss10.elemecdn.com/3/63/4e7f3a15429bfda99bce42a18cdd1jpeg.jpeg?imageMogr2/thumbnail/360x360/format/webp/quality/100'}, {name: 'food2.jpeg', url: 'https://fuss10.elemecdn.com/3/63/4e7f3a15429bfda99bce42a18cdd1jpeg.jpeg?imageMogr2/thumbnail/360x360/format/webp/quality/100'}]
    }
  },
  components:{testModel},


  created(){
    // this.$alert(2);
  },
  methods:{
    clickbtn(){
      alert(1);
    },
    handleInput(event){
      this.theInputValue = event.target.value;
    }
  },
  watch: {
    a(value) {
        console.log(value);
      },
      theInputValue(val){
        console.log(val);
      }
    },
    computed:{
      testcheckbox: {
        get() {
// debugger;
          // return this.value;
          // return this.selfModel;
          return [1,2]
        },
        set(value) {
          debugger;
          // console.log('set');
          // this.value = value;
          // this.$emit('input', value);
          // this.selfModel = value;

        }
      }

    },
}
</script>

<style>
/*import 'element-ui.css';*/
@import './element-ui/lib/theme-default/index.css';
/*@import '../../node_modules/swiper/dist/css/swiper.min.css';*/
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>