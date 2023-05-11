<template>
  <q-layout view="hHh lpR lFf">
    <div class='bg' />
    <q-header reveal class="bg-grey-1 text-white" style="opacity: 0.9">
      <q-toolbar>
        <q-btn class='text-blue q-mr-none' dense flat round icon="menu" @click="toggleLeftDrawer" />

        <q-toolbar-title class='text-left q-ml-none q-mr-none'>
          <h5 class='q-mt-md q-mb-md text-weight-medium'><span class='text-blue'>Cargo</span><span class='text-orange'>Tracker</span></h5>
        </q-toolbar-title>
        <q-toolbar-title class='text-right q-ma-md'>
          <q-avatar>
            <img src="/profile-pic.png" />
          </q-avatar>
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer  v-model="leftDrawerOpen" side="left">
      <div class="bg-blue full-height full-width row">
        <ul class='text-white text-h6 cursor-pointer'>
          <li @click="leftDrawerOpen = false; $router.push('/')">Home</li>
          <li @click="leftDrawerOpen = false; $router.push('/dashboard')">My Trackings</li>
        </ul>
      </div>

    </q-drawer>

    <q-page-container >
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>

export default {
  data () {
    return {
      leftDrawerOpen: false,
    }
  },
  methods: {
    toggleLeftDrawer: function () {
      this.leftDrawerOpen ? this.leftDrawerOpen = false : this.leftDrawerOpen = true;
    }
  }
}
</script>

<style>
li:hover {
  color: orange;
}
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
