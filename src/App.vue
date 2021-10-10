<template>
    <div style="display: flex;">
        <div style="width: 200px;background-color: red">
            <Sidebar></Sidebar>
        </div>
        <div id="charts">
            <Doughnut></Doughnut>
            <Line></Line>
            <Count></Count>
        </div>
    </div>
</template>

<script>
import Doughnut from './components/Doughnut.vue'
import Line from './components/Line.vue'
import Count from './components/ProductCountBarChart.vue'
import Sidebar from './components/Sidebar.vue'

export default {
    components: {
        Doughnut,
        Line,
        Count,
        Sidebar
    },
}

</script>
