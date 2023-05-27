<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-white text-grey-10" bordered>
        <q-toolbar>
          <q-btn
            to="/camera"
            flat
            round
            dense
            class="large-screen-only q-mr-sm"
            size="18px"
            icon="eva-camera-outline" />
          <q-separator vertical inset spaced class="large-screen-only"/>
          <q-toolbar-title class="text-bold text-grand-hotel">Quasargram</q-toolbar-title>
          <q-btn
            to="/"
            flat
            round
            dense
            class="large-screen-only"
            size="18px"
            icon="eva-home-outline" />
        </q-toolbar>
      </q-header>

      <q-footer
        class="bg-white small-screen-only"
        bordered
        active-color="primary"
        indicator-color="transparent">
          <q-tabs class="text-grey-10">
            <q-route-tab to="/" name="mails" icon="eva-home-outline"/>
            <q-route-tab to="/camera" name="movies" icon="eva-camera-outline"/>
          </q-tabs>
      </q-footer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  components: {},

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>

<style lang="scss">
  .q-toolbar{
    @media (min-width: $breakpoint-sm-min){
      height: 77px;
    }
  }
  .q-toolbar__title{
    font-size: 30px;
    margin-top: 10;
    @media (max-width: $breakpoint-xs-max){
      text-align: center;
    }
  }
  .q-toolbar .q-btn {
    margin-top: 5px;
    padding: 10px;
  }
  .q-footer .q-tab__icon{
      font-size: 30px
  }
</style>
