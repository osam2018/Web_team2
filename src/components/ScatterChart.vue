<script>
    import { Scatter } from 'vue-chartjs'

    export default {
        name: "ScatterChart",
        extends: Scatter,
        mounted () {
            this.renderChart({
                datasets: [{
                    label: '삼성전자 & 하이닉스',
                    // xAxisID: '삼성전자',
                    fill: false,
                    borderColor: '#f87979',
                    backgroundColor: '#f87979',
                    data: [{
                        x: -2,
                        y: 4
                    }, {
                        x: -1,
                        y: 1
                    }, {
                        x: 0,
                        y: 0
                    }, {
                        x: 1,
                        y: 1
                    }, {
                        x: 2,
                        y: 4
                    }]
                }]
            }, {responsive: true, maintainAspectRatio: false})
        }
    }
</script>

<style scoped>

</style>