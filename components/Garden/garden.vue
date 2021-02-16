<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-12"><h2>{{name}}</h2></div>
        </div>
        <garden-bed v-for="bed in beds" :key="bed.id" :bed-id="bed.id" :bed-size="bed.size" :plots="bed.plots" />
    </div>
</template>
<script lang="ts">
export default {
    props: {
        name: {
            type: String,
            required: false
        },
        beds: {
            type: Array,
            required: true
        }
    }
}
</script>