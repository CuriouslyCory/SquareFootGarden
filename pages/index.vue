<template>
  <div>
    <div class="container header">
      <div class="row">
        <div class="col-12">
          <h1>My Gardens</h1>
        </div>
      </div>
    </div>
    <garden v-for="garden in gardens" :key="garden.id" :name="garden.name" :beds="garden.beds"/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: '',
  props: {},
  data () {
    return {
      gardens: [
        {
          id: 1,
          name: 'West Garden',
          beds: [
            {
              id: 'bed-1',
              size: {x: 8, y: 2},
              plots: [
                {
                  loc: {x: 1, y: 1},
                  name: 'Lettuce Bib'
                },
                {
                  loc: {x: 1, y: 2},
                  name: 'Hot Pepper'
                },
                {
                  loc: {x: 2, y: 1},
                  name: 'Lettuce'
                },
                {
                  loc: {x: 2, y: 2},
                  name: 'Hot Pepper'
                },
                {
                  loc: {x: 3, y: 2},
                  name: 'Mustard'
                },
                {
                  loc: {x: 4, y: 2},
                  name: 'Celery'
                },
                {
                  loc: {x: 5, y: 2},
                  name: 'Beans'
                },
                {
                  loc: {x: 6, y: 2},
                  name: 'Beans'
                },
                {
                  loc: {x: 3, y: 1},
                  name: 'Radish'
                },
                {
                  loc: {x: 4, y: 1},
                  name: 'Turnip'
                },
                {
                  loc: {x: 5, y: 1},
                  name: 'Kale'
                }
              ]
            },
            {
              id: 'bed-2',
              size: {x: 8, y: 2},
              plots: []
            }
          ]
        }
      ]
    }
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
