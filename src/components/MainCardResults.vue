<template>
  <div class='full-width q-pa-lg rounded card'>
    <Transition>
      <div>
        <q-card v-for="item in items" :key="item.id" class='q-mb-sm q-pl-none q-pr-none q-pt-sm q-pb-sm card-hover'  >
          <q-card-section class='flex flex-center flex-wrap row'>
            <div class='col-3 col-sm-2 logo'>
              <img :src="item.logo" class='img-logo' />     
            </div>
            <span class='col-9 col-sm-10'>
              <span class='text-orange text-bold text-h7'>
                {{ item.route }}
              </span>
              <!-- &nbsp; -->
              <br /><br />
              <span class='text-grey-10'>
                Em Trânsito<br />
                <img :src="item.type" class='img-modal-type' style='margin-bottom: -6px' />
                {{ item.from }} - {{ item.to }}<br />
                <q-icon name='fa-solid fa-calendar-alt' />&nbsp;Chegada em {{ item.message }}
              </span>
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
        message: '30/05/2023 14:30',
        from: 'Ningbo',
        to: 'Sines',
        type: 'ship.svg',
        route: 'CNTXG > SGSIN'
      }, {
        id: 2,
        logo: 'logos/msc.svg',
        message: '30/05/2023 14:30',
        from: 'Ningbo',
        to: 'Sines',
        type: 'ship.svg',
        route: 'CNTXG > SGSIN'
      }]

    }
  }
}
</script>

<style scoped>
@media (max-width: 768px) {
  .logo {
    display: grid;
    width: 100%;
    justify-content: center;
    margin-bottom: 24px;
  }
}
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
