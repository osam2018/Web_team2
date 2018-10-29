<template>
        <div class="result_page">
            <h1>백테스트 결과</h1>
            <div></div>
            <LineChart />
        </div>
</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import LineChart from "./LineChart.vue"

    @Component({
        components: {
            LineChart
        },
    })
    export default class Result extends Vue {

    }
</script>

<style scoped>
    .result_page{
        width: 60%;
        margin-left: 10%;
        margin-right: 10%;
        padding: 5%;
		height:10px;
    }
</style>
