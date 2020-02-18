<template>
  <!-- <q-page class="column items-center q-pa-sm"> -->
  <q-page class="column flex-center">
    <!--
    <img alt="Quasar logo" src="~assets/quasar-logo-full.svg">
    -->
    <q-btn label="Dried Boerewors" color="primary" text-color="secondary" class="q-pa-sm" :to="{ path: 'driedboerewors' }"/>
    <br />
    <q-btn label="Biltong" color="primary" text-color="secondary" class="q-pa-sm" :to="'biltong'"/>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex'
}
</script>
