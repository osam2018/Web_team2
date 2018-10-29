<template>
    <el-row :gutter="20">
        <el-col :span="12" :offset="3">
            <LowerLeftForm @value_change="renderChartData"
                           @InputConfirm="handleInputConfirm"
                           @SliderChange="handleSliderChange"
                           @Close="handleClose"
                           :form="form" :assets="assets" :dynamicTags="dynamicTags" />
        </el-col>
        <el-col :span="5">
            <PieChart :chartData="chartData" :options="options" />
        </el-col>
    </el-row>
</template>



<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';
    import PieChart from "./PieChart.vue"
    import LowerLeftForm from "./LowerLeftForm.vue"

    @Component({
        components: {
            PieChart,
            LowerLeftForm
        },
    })
    export default class LowerForm extends Vue {
        @Prop()
        public form!:object;

        @Prop()
        public assets!:any[];

        @Prop()
        public dynamicTags!:string[];

        private chartData:object = {
            labels: this.assets.map(e => e.name),
            datasets: [
                {
                    label: '',
                    backgroundColor: ['#002761', '#003d97', '#0054d2', '#1a75ff', '#609fff', '#97c0ff', '#d0e3ff'],
                    data: this.assets.map(e => e.weight)
                }
            ]
        };
        private options:object = {
            legend: {
                display: false
            }
        };

        handleInputConfirm(arg:any){
            // console.log("LowerForm : " + arg);
            this.$emit('InputConfirm', arg)
        }

        handleSliderChange(arg:any){
            this.$emit('SliderChange', arg)
        }

        handleClose(arg:any){
            this.$emit('Close', arg)
        }

        renderChartData(){
            this.chartData = {
                labels: this.assets.map(e => e.name),
                datasets: [
                    {
                        label: '',
                        backgroundColor: ['#002761', '#003d97', '#0054d2', '#1a75ff', '#609fff', '#97c0ff', '#d0e3ff'],
                        data: this.assets.map(e => e.weight)
                    }
                ]
            }
        }

    }
</script>


<style scoped>
    .el-tag + .el-tag {
        margin-left: 10px;
    }
    .button-new-tag {
        margin-left: 10px;
        height: 32px;
        line-height: 30px;
        padding-top: 0;
        padding-bottom: 0;
    }
    .input-new-tag {
        width: 90px;
        margin-left: 10px;
        vertical-align: bottom;
    }

    .el-form-item__label{
        text-align: left;
    }

    .el-progress{
        width: 50%;
        margin: 10%;
        margin-top: 0;
    }

    .el-form-item__content{

    }

</style>
