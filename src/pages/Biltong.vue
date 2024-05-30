<template>
  <q-page class="column items-center q-pa-sm">
    Biltong
    <q-input style="width:150px" suffix="grams" class="q-pb-sm" type="number" filled label="Meat" v-model="total"/>
    <q-input style="width:150px" suffix="grams" readonly class="q-pb-sm" filled label="Cure#2" v-model="cure"/>
    <q-input readonly class="q-pb-sm" filled style="width:150px" suffix="grams" label="Salt" v-model="salt"/>
    <q-input readonly class="q-pb-sm" filled label="BlackPepper" style="width:150px" suffix="grams" v-model="pepper"/>
    <q-input readonly class="q-pb-sm" filled label="Coriander" style="width:150px" suffix="grams" v-model="coriander"/>
    <q-input readonly class="q-pb-sm" filled label="Sugar" style="width:150px" suffix="grams" v-model="sugar"/>
    <q-input readonly class="q-pb-sm" filled label="Worcester" style="width:150px" suffix="grams" v-model="worcester"/>
    <q-input readonly class="q-pb-sm" filled label="Vinegar" style="width:150px" suffix="grams" v-model="vinegar"/>
  </q-page>
</template>

<script>
import _ from 'lodash'

export default {
  name: 'PageIndex',
  data () {
    return {
      meat: '',
      fat: '',
      total: ''
    }
  },
  computed: {
    cure () {
      return _.round((this.total * 0.0025), 2)
    },
    salt () {
      return _.round((this.total * 0.0275), 2)
    },
    pepper () {
      return _.round((this.total * 0.0015), 2)
    },
    coriander () {
      return _.round((this.total * 0.0075), 2)
    },
    sugar () {
      return _.round((this.total * 0.0125), 2)
    },
    worcester () {
      return _.round((this.total * 0.025), 2)
    },
    vinegar () {
      return _.round((this.total * 0.1), 2)
    }
  },
  methods: {
    updateTotal (val) {
      console.log('total', val)
      this.fat = _.round((val * (1 / 11)), 2)
      this.meat = _.round((val * (10 / 11)), 2)
    },
    updateFat (val) {
      console.log('total', val)
      this.meat = _.round((val * 10), 2)
      this.total = _.round((Number(val) + Number(this.meat)), 2)
    },
    updateMeat (val) {
      console.log('total', val)
      this.fat = _.round((val * 0.1), 2)
      this.total = _.round((Number(val) + Number(this.fat)), 2)
    }
  },
  mounted () {
  }
}
</script>
