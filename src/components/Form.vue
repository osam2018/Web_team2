<template>
    <div class="form">
        <el-form ref="form" :model="form" label-width="120px" v-loading="loading">

            <el-row :gutter="20">
                <el-col :span="17" :offset="3">
                    <div class="">
                        <UpperForm :form="form"/>
                    </div>
                </el-col>
            </el-row>

            <el-row :gutter="20">
                <LowerForm @InputConfirm="handleInputConfirm_from_child"
                           @SliderChange="handleSliderChange"
                           @Close="handleClose"
                           :form="form" :assets="assets" :dynamicTags="dynamicTags"/>
            </el-row>

            <el-form-item>
                <el-button type="primary" @click.once="onSubmit">Run</el-button>
            </el-form-item>
        </el-form>

        <el-progress v-show="show_progress_bar" :text-inside="true" :stroke-width="18" :percentage="progress" :status="status"></el-progress>

        <div v-bind:is="component">

        </div>

        <!--<ScatterChart />-->

    </div>
</template>



<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';
    import Result from './Result.vue'
    import PieChart from "./PieChart.vue"
    import ScatterChart from "./ScatterChart.vue"
    import LowerForm from "./LowerForm.vue"
    import UpperForm from "./UpperForm.vue"

    @Component({
        components: {
            'result': Result,
            PieChart,
            ScatterChart,
            LowerForm,
            UpperForm
        },
    })
    export default class Form extends Vue {
        private form:object = {
            date_range: '',
            date1: '',
            date2: '',
            delivery: false,
            type:[],
            rebalance_type: '',
            benchmark_index:''
        };

        private component:any = '';
        private show_progress_bar:boolean = false;

        private assets:any[] = [{'name':'현금', 'weight':100, 'slider_disable':false}];
        private dynamicTags:string[] = ['현금'];
        private inputVisible:boolean = false;
        private loading:boolean = false;
        private inputValue:string = '';
        private progress:number= 0;
        private status:string= '';

        handleInputConfirm_from_child(arg:any){
            this.handleInputConfirm(arg)
        }

        handleSliderChange(arg:any){
            this.handleChange(arg);
        }

        created(){
            this.assets = [...this.assets
            ];
            this.equalize_weight()
        }


        onSubmit() {
            console.log('submit!');
            this.loading = true;
            setTimeout(this.after_loading, 1500);
            this.run_progress_bar();
        }

        after_loading(){
            this.loading = false;
        }

        handleClose(tag:any) {
            this.dynamicTags.splice(this.dynamicTags.indexOf(tag), 1);
            this.assets.splice(this.assets.findIndex(e => e.name == tag), 1);
            this.equalize_weight()
        }

        showInput() {
            this.inputVisible = true;
            this.$nextTick(function () {
                // this.$refs.saveTagInput.$refs.input.focus();
            })
        }

        handleInputConfirm(arg:any) {
            console.log(arg)
            let inputValue = arg;
            if (inputValue) {
                this.dynamicTags.push(inputValue);
                this.assets.push({'name':inputValue, 'weight':0, 'slider_disable':false});
                this.equalize_weight()
            }
        }

        handleChange(asset:any){
            const name = asset.name;
            const total_weight = 100;
            const disable_weight = asset.weight;
            const num_of_asset = this.assets.length;

            let not_disable_weight = total_weight - disable_weight;
            let equal_weight = Math.floor(not_disable_weight / (num_of_asset -1));

            for(let item of this.assets){
                if(item.name != name){
                    item.weight = equal_weight
                }
            }

            let assigned_weight = 0;
            for(let item of this.assets){
                assigned_weight += item.weight
            }

            let remain = total_weight - assigned_weight;

            this.assets[0].weight += remain;
        }

        run_progress_bar(){
            this.show_progress_bar = true;
            let test = setInterval(()=>{
                this.progress += 1;
                if(this.progress == 100)
                {
                    clearInterval(test);
                    this.status = 'success';
                    this.component = 'result';
                }
                }, 15);
        }

        fix_slider(index:any){
            console.log("click");
            // this.assets[index].slider_disable = true
        }

        equalize_weight(){

            const total_weight = 100;
            let disable_weight = 0;
            let not_disable_weight = total_weight - disable_weight;

            let num_of_asset = this.assets.length;
            let equal_weight = Math.floor(not_disable_weight / num_of_asset);


            for (let item of this.assets) {
                item.weight = equal_weight;
            }

            let assigned_weight = 0;
            for(let item of this.assets){
                assigned_weight += item.weight
            }

            let remain = total_weight - assigned_weight;

            this.assets[0].weight += remain;

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
        margin-left: 13%;
        margin-top: 0;
		margin-bottom: 0;
    }

</style>
