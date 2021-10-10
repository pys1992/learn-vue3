<template>
    <div id="charts">
        <Doughnut></Doughnut>
        <Line></Line>
        <Count></Count>
    </div>
</template>

<script>
import Doughnut from './components/Doughnut.vue'
import Line from './components/Line.vue'
import Count from './components/ProductCountBarChart.vue'

export default {
    components: {
        Doughnut,
        Line,
        Count
    },
}

</script>
