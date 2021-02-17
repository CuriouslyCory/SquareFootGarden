<template>
    <div class="row bed-wrapper">
        <div class="col-12">
            {{bedId}}
        </div>
        <div class="container">
            <div class="row" v-for="ny in bedSize.y" v-bind:key="ny">
                <div class="col sqft" v-for="nx in bedSize.x" v-bind:key="nx + ny">
                    {{nx}},{{ny}}
                    {{cellVal(nx, ny)}}
                </div>
            </div>
        </div>
    </div>
</template>
<script lang="ts">
import Vue, { PropOptions } from 'vue'

interface Plot {
    loc: PlotLocation,
    name: String
}

interface PlotLocation{
    x: Number,
    y: Number
}

export default Vue.extend({
    props: {
        bedId: {
            type: String,
            required: true
        },
        bedSize: {
            type: Object,
            required: true
        },
        plots: {
            type: Array,
            required: true
        } as PropOptions<Plot[]>
    },

    methods: {
        cellVal(nx: Number, ny: Number): String {
            let aPlot = this.plots.filter(content => content.loc.x == nx && content.loc.y == ny);
            return !!aPlot[0] ? aPlot[0].name : '';
        }
    }
})
</script>
<style lang="sass">
.bed-wrapper
    border: solid 1px gray

.sqft
    border: solid 1px gray
    min-height: 5rem
</style>
