<template>
    <div>
        <!--<el-row :gutter="20">-->
            <!--<el-col :span="17" :offset="3">-->
                <!--<div class="">-->
                    <!--<UpperForm />-->
                <!--</div>-->
            <!--</el-col>-->
            <!--&lt;!&ndash;<LowerForm />&ndash;&gt;-->
        <!--</el-row>-->

        <!--<el-row :gutter="20">-->
            <!--<LowerForm />-->
        <!--</el-row>-->

        <Form />

    </div>
</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import Form from './Form.vue'
    import UpperForm from './UpperForm.vue'
    import LowerForm from './LowerForm.vue'
    import PieChart from "./PieChart.vue"


    @Component({
        components: {
            Form,
            UpperForm,
            LowerForm,
            PieChart
        },
    })
    export default class AssetAllocationPage extends Vue {

    }
</script>

<style scoped>
    .el-row {
        margin-bottom: 20px;
    &:last-child {
         margin-bottom: 0;
     }
    }
    .el-col {
        border-radius: 4px;
    }
    .bg-purple-dark {
        background: #99a9bf;
    }
    .bg-purple {
        background: #d3dce6;
    }
    .bg-purple-light {
        background: #e5e9f2;
    }
    .grid-content {
        border-radius: 4px;
        min-height: 36px;
    }
    .row-bg {
        padding: 10px 0;
        background-color: #f9fafc;
    }
</style>
