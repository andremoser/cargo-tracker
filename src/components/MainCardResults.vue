<template>
  <div class='full-width q-pa-lg rounded'>
    <Transition>
      <div>
        <q-card v-for="item in items" :key="item.id" class='q-mb-sm q-pl-none q-pr-none q-pt-sm q-pb-sm bg-blue-2' flat >
          <q-card-section class='flex flex-center row'>
            <img :src="item.logo" class='col-2 col-sm-2'/>          
            <span class='col-7 col-sm-7'>{{ item.message }}</span>
            <img :src="item.type" class='col-2 col-sm-2' />
          </q-card-section>
        </q-card>
      </div>
    </Transition>
  </div>  
</template>

<script>
export default {
  data () {
    return {
      items: [{
        id: 1,
        logo: '/logos/maersk.svg',
        message: 'Mensagem',
        type: 'ship.svg'
      }, {
        id: 2,
        logo: 'logos/msc.svg',
        message: 'Mensagem',
        type: 'ship.svg'
      }]

    }
  }
}
</script>

<style scoped>
.card img {
  width: 40px;
  height: 40px;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

</style>
