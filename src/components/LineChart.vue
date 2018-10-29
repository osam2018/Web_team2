<script>
    import { Line } from 'vue-chartjs'

    export default {
        name: "LineChart",
        extends: Line,
        mounted () {
            this.renderChart({
                labels: ['2018.09.01', '2018.09.11', '2018.09.21', '2018.10.01', '2018.10.11', '2018.10.21', '2018.11.01', '2018.11.11', '2018.11.21', '2018.12.01', '2018.12.11', '2018.12.21'],
                datasets: [
                    {
                        label: 'Your Portfolio',
                        borderColor: "blue",
                        fill: false,
                        data: [0, -1, 3, -1, 1, 2, 4, 6, 4, 5, 7, 5]
                    },
                    {
                        label: '코스피',
                        borderColor: "red",
                        fill: false,
                        data: [0, -2, -3, 0, -3, -2, -5, -7, -5, -6, -5, -2]
                    }
                ]
            })
        }
    }
</script>

<style scoped>

</style>