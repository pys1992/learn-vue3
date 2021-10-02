<template>
    <div id="charts">
        <Doughnut></Doughnut>
        <Line></Line>
    </div>
</template>

<script>
import Doughnut from './components/Doughnut.vue'
import Line from './components/Line.vue'

export default {
    components: {
        Doughnut,
        Line,
    },
}

</script>
