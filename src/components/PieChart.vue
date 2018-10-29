<script>
    import { Pie, mixins } from 'vue-chartjs'

    export default {
        name: "PieChart",
        extends: Pie,
        mixins: [mixins.reactiveProp],

        props: ['chartData', 'options'],
        mounted() {
            this.renderChart(this.chartData, this.options);
        }
    }
</script>

<style scoped>

</style>
