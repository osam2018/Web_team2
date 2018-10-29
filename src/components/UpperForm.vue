<template>
    <div>
        <div class="form">
            <el-form ref="form" :model="form" label-width="120px" v-loading="loading">
                <el-form-item label="투자 기간">
                    <el-date-picker v-model="form.date_range" type="daterange" align="right" start-placeholder="Start Date" end-placeholder="End Date" default-value="2018-09-01">
                    </el-date-picker>
                </el-form-item>
                <el-form-item label="리밸런싱">
                    <el-select v-model="form.rebalance_type" placeholder="please select your rebalance type">
                        <el-option label="매일" value="day"></el-option>
                        <el-option label="매주" value="week"></el-option>
                        <el-option label="매월" value="month"></el-option>
                        <el-option label="매년" value="year"></el-option>
                    </el-select>
                </el-form-item>
                <el-form-item label="벤치마크 지수">
                    <el-select v-model="form.benchmark_index" placeholder="벤치마크 지수">
                        <el-option label="코스피" value="shanghai"></el-option>
                        <el-option label="코스닥" value="beijing"></el-option>
                    </el-select>
                </el-form-item>
            </el-form>
        </div>
    </div>
</template>

<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';

    @Component({
        components: {
        },
        props:{
            form: Object,
        }
    })
    export default class UpperForm extends Vue {

        private loading:boolean = false;


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
</style>
