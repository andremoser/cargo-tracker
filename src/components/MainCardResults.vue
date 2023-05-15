<template>
  <div class='full-width q-pa-lg rounded'>
    <Transition>
      <div>
        <q-card v-for="item in items" :key="item.id" class='q-mb-sm q-pl-none q-pr-none q-pt-sm q-pb-sm card-hover' >
          <q-card-section class='flex flex-center row'>
            <div class='col-3 col-sm-2'>
              <img :src="item.logo" class='img-logo' />     
            </div>
            <span class='col-9 col-sm-10'>
              <span class='text-orange text-bold text-h7'>
                {{ item.route }}
              </span>
              &nbsp;<img :src="item.type" class='img-modal-type'/>
              <br />
              {{ item.message }}
            </span>
            <!-- <img :src="item.type" class='col-2 col-sm-2 img-logo' /> -->
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
        type: 'ship.svg',
        route: 'CNTXG > SGSIN'
      }, {
        id: 2,
        logo: 'logos/msc.svg',
        message: 'Mensagem',
        type: 'ship.svg',
        route: 'CNTXG > SGSIN'
      }]

    }
  }
}
</script>

<style scoped>
.card .img-logo {
  width: 40px;
  height: 40px;
}

.img-modal-type {
  width: 25px;
  height: 25px;
  top: 5px;
}

.card-hover:hover {
  outline: solid 2px orange;
  cursor: pointer;
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
