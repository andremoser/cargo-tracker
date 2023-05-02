<template>
  <q-layout view="hHh lpR fFf">
    <div class='bg' />
    <q-header reveal class="bg-grey-1 text-white" style="opacity: 0.9">
      <q-toolbar>
        <q-toolbar-title class='text-left q-ml-sm q-mr-none'>
          <h5 class='q-mt-md q-mb-md text-weight-medium'><span class='text-blue'>Cargo</span><span class='text-orange'>Tracker</span></h5>
        </q-toolbar-title>
        <q-toolbar-title class='text-right q-ma-md'>
          <q-avatar color='grey'>
            <q-icon name='fa-solid fa-user' />
          </q-avatar>
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container >
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>

<style>
@media (min-width: 1000px) {
  .bg {
    top: 0;
    left: 0;
    position: fixed;
    background: url('/1.svg');
    background-size: 100%;
    object-fit: contain;
    height: 100%;
    width: 100%;
  }
}
@media (max-width: 999px) {
  .bg {
    top: 0px;
    left: 0;
    position: fixed;
    background: url('/1.svg');
    background-size: 230%;
    object-fit: contain;
    height: 150%;
    width: 100%;
  }
}

</style>
