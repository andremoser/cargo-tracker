<template>
  <div class='panel'>
    <div class="row text-center justify-content align-items flex-center q-mt-md">  
      <q-btn rounded class='col-md-2 q-ma-sm q-pa-sm' color='blue' label='Adicionar' icon='fa-solid fa-plus-circle' @click='dialogNew = true' />
    </div>
      <q-card class='q-ml-md q-mr-md q-mt-lg q-mb-sm card' flat bordered rounded>
        <q-card-section class='flex full-width row'>
          <div class="col-1 col-sm-1 text-weight-medium">
            Operador
          </div>
          <div class="col-1 col-sm-1 text-weight-medium">
            Tipo
          </div>
          <div class="col-1 col-sm-1 text-weight-medium">
            Rastreador
          </div>
          <div class="col-1 col-sm-1 text-weight-medium text-center">
            Origem
          </div>
          <div class="col-1 col-sm-1 text-weight-medium">
            &nbsp;
          </div>
          <div class="col-1 col-sm-1 text-weight-medium text-center">
            Destino
          </div>
          <div class="col-1 col-sm-1 text-weight-medium text-center">
            Tempo Corrido
          </div>
          <div class="col-2 col-sm-2 text-weight-medium text-center">
            Data Atualização
          </div>
          <div class="col-1 col-sm-1 text-weight-medium text-center">
            Serviço
          </div>
          <div class="col-1 col-sm-1 text-weight-medium text-center ">
            Matrícula / Nome
          </div>

          <!-- <div v-for='text in texts' :key='text' class="col-1 col-sm-1 text-weight-medium">
            <span v-html="text" />
          </div> -->

        </q-card-section>
      </q-card>
      <q-card flat bordered v-for="item in items" :key="item.id" class='q-mr-md q-ml-md q-mb-sm card cursor-pointer card-hover' @click='dialogDetails = true' >
        <q-card-section class='flex row' >
          <div class='col-1 col-sm-1 logo'>
            <img :src="item.logo" class='img-logo' />     
          </div>
          <div class="col-1 col-sm-1">
            <img :src="item.type" class='img-modal-type' style='margin-bottom: -6px' />
          </div>
          <div class="col-1 col-sm-1 q-mr-lg q-ml-none">
            {{ item.tracker }}
          </div>
          <div class='col-1 col-sm-1 text-left'>
            {{ item.original_from }}
          </div>  
          <div class="col-1 col-sm-1">
            <p class='text-orange text-h4 text-bold text-center q-pr-xl'>></p>
          </div>
          <div class='col-1 col-sm-1 text-left'>
            {{ item.original_to }}
          </div> 
          <div class='col-1 col-sm-1 text-left'>
            {{ item.days }} dias
          </div> 
          <div class='col-2 col-sm-2 text-left'>
            {{ item.update_date }}
          </div> 
          <div class='col-1 col-sm-1 text-left'>
            {{ item.service }}
          </div> 
          <div class='col-1 col-sm-1 text-left'>
            {{ item.registration }}
          </div>

          <!-- <span>
            <span class='text-orange text-bold text-h7'>
              {{ item.route }}
            </span>
            <br /><br />
            <span class='text-grey-10'>
              Em Trânsito<br />
              <img :src="item.type" class='img-modal-type' style='margin-bottom: -6px' />
              {{ item.from }} - {{ item.to }}<br />
              <q-icon name='fa-solid fa-calendar-alt' />&nbsp;Chegada em {{ item.message }}
            </span>
          </span> -->
          <!-- <img :src="item.type" class='col-2 col-sm-2 img-logo' /> -->
        </q-card-section>
      </q-card>

    <q-dialog v-model="dialogNew">
      <q-card style="min-width: 380px">
        <q-card-section>
          <q-btn icon="close" flat round dense v-close-popup />
          <div class="text-h6 q-ml-sm q-mt-sm">Adicionar Rastreador</div>
        </q-card-section>

        <q-card-section class="q-pt-none">
          <q-input 
            v-model="tracker"
            label="Código de Rastreio" rounded outlined  class='input' color="orange-5">
            <template v-slot:prepend>
              <q-icon name="search" />
            </template>
            <template v-slot:append>
              <q-icon name="close" @click="tracker = ''" class="cursor-pointer" />
            </template>   
          </q-input>        
        </q-card-section>

        <q-card-actions align="right" class="text-blue q-ma-lg text-center">
          <q-btn class='q-pa-sm' v-close-popup @click="tracker = ''"  rounded color='green' label='Confirmar' icon='fa-solid fa-plus-circle' />
<!-- 
          <q-btn flat label="Cancelar" v-close-popup @click="tracker = ''" />
          <q-btn flat label="Adicionar" v-close-popup @click="tracker = ''" /> -->
        </q-card-actions>
      </q-card>
    </q-dialog>

    <q-dialog v-model="dialogDetails">
      <q-card class="my-card q-pa-md" style='min-width: 500px'>
        <q-card-section>
          <q-btn icon="close" flat round dense v-close-popup />
          <q-timeline color="orange">
            <q-timeline-entry heading >
              TR12345678910
            </q-timeline-entry>

            <q-timeline-entry
              title="Tianjin Gang (CNTXG)"
              subtitle="26/04/2023 15:12"
              icon="fa-solid fa-truck-loading"
            >
              <div>
                Saída da Carga<br />
                Albatros<br />
                Monaco Maersk/320W
              </div>
            </q-timeline-entry>

            <q-timeline-entry
              title="Ningbo"
              subtitle="28/04/2023 19:28"
              icon="fa-solid fa-ship"
            >
              <div>
                Gangji Terminal<br />
                Lion Service<br />
                MSC Apolline/FL321W
              </div>
            </q-timeline-entry>

            <q-timeline-entry
              title="Sines"
              subtitle="02/05/2023 17:28"
              icon="fa-solid fa-ship"
            >
              <div>
                Sines Container Terminal<br />
                NWC to Saec
              </div>
            </q-timeline-entry>


          </q-timeline>

        </q-card-section>
        <q-card-section class='text-center'>
          <q-btn rounded class='col-md-2 q-ma-sm q-pa-sm' color='red-10' label='Remover' icon='fa-solid fa-times-circle' />
        </q-card-section>
      </q-card>
    </q-dialog>
  </div>
</template>

<script>

export default {
  data () {
    return {
      dialogNew: false,
      dialogDetails: false,
      tracker: '',
      text: '',      
      items: [{
        id: 1,
        tracker: 'TR12345678910',
        registration: 'Monaco Maersk/320W',
        logo: '/logos/maersk.svg',
        service: 'Albatros',
        message: '30/05/2023 14:30',
        update_date: '15/05/2023 21:47',
        original_from: 'Tianjin Gang (CNTXG)',
        original_to: 'Paranaguá (SGSIN)',
        days: '47',
        from: 'Ningbo',
        to: 'Sines',
        type: 'ship.svg',
        route: 'CNTXG > SGSIN'
      }, {
        id: 2,
        logo: 'logos/msc.svg',
        tracker: 'TR12345678910',
        registration: 'Monaco Maersk/320W',
        service: 'Albatros',
        days: '47',
        message: '30/05/2023 14:30',
        update_date: '15/05/2023 21:47',
        original_from: 'Tianjin Gang (CNTXG)',
        original_to: 'Paranaguá (SGSIN)',
        from: 'Ningbo',
        to: 'Sines',
        type: 'ship.svg',
        route: 'CNTXG > SGSIN'
      }]
    }
  }, 
  mounted () {
    this.createData();
  },
  methods: {
    createData: function () {
      let data = {};
      for (let i = 2; i < 7; i++) {
        if (i % 2) {
          data = {
            id: i,
            logo: 'logos/msc.svg',
            tracker: 'TR12345678910',
            registration: 'Monaco Maersk/320W',
            service: 'Albatros',
            days: '47',
            message: '30/05/2023 14:30',
            update_date: '15/05/2023 21:47',
            original_from: 'Tianjin Gang (CNTXG)',
            original_to: 'Paranaguá (SGSIN)',
            from: 'Ningbo',
            to: 'Sines',
            type: 'ship.svg',
            route: 'CNTXG > SGSIN'
          }
        }
        else {
          data = {
            id: i,
            logo: 'logos/maersk.svg',
            tracker: 'TR12345678910',
            registration: 'Monaco Maersk/320W',
            service: 'Albatros',
            days: '47',
            message: '30/05/2023 14:30',
            update_date: '15/05/2023 21:47',
            original_from: 'Tianjin Gang (CNTXG)',
            original_to: 'Paranaguá (SGSIN)',
            from: 'Ningbo',
            to: 'Sines',
            type: 'ship.svg',
            route: 'CNTXG > SGSIN'
          }
        }

        this.items.push (data);
        data = {};
      }
    }
  }
}
</script>


<style scoped>
.card-hover:hover {
  outline: solid 2px orange;
}
@media (min-width: 900px) {
  .panel {
    width: 98%;
    max-width: 1400px;
    height: 90vh;
    background: rgba(255,255,255,0.9);
    position: fixed;
    display: block;
    margin: auto;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    margin-top: 35px;
    border-radius: 5px;
    overflow: auto;
  }
}
.card .img-logo {
  width: 40px;
  height: 40px;
}

.img-modal-type {
  width: 40px;
  height: 40px;
  top: 5px;
}

</style>