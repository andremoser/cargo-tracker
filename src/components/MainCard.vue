<template>
  <div class='row justify-center' >
    <q-card rounded  class='q-pa-xl q-ma-md card'>
      <q-card-section class='text-center text-h4'>
        <h4 class='q-pa-none q-ma-none text-weight-medium'><span class='text-blue'>Cargo</span><span class='text-orange'>Tracker</span></h4>
      </q-card-section>
      <q-card-section class='q-pt-md q-pb-md'>
          <q-input 
            v-model="text"
            label="Código de Rastreio" rounded outlined  class='input' color="orange-5">
            <template v-slot:prepend>
              <q-icon name="search" />
            </template>
            <template v-slot:append>
              <q-icon name="close" @click="text = ''" class="cursor-pointer" />
            </template>   
          </q-input>
      </q-card-section>
      <q-card-section class='text-center q-pa-none'>
        <q-btn label='Pesquisar' icon='search' class='center input text-weight-bold' color='orange-5' padding='md' rounded @click.native='showLoading()'/>
      </q-card-section>
      <MainCardResults v-if="results" />
    </q-card>
  </div>
</template>

<script>
import { Loading } from 'quasar';
import MainCardResults from 'src/components/MainCardResults.vue';

export default {
  components: {
    MainCardResults
  },
  data () {
    return {
      text: "",
      results: false
    }
  },
  methods: {
    showLoading: function () {
      Loading.show({
        message: ''
      });
      this.hideLoading();
    },
    hideLoading: function () {
      setTimeout (() => { Loading.hide(); this.results = true }, 4000);
    } 
  }
}
</script>

<style>
@media (max-width: 768px) {
  .card {
    opacity: 0.97; 
    height: 80vh;
    width: 380px;
    text-align: center;
    margin: auto;
    overflow: auto;
  }
  .input {
    width: 260px;
    text-align: center;
  }
}
@media (min-width: 769px) {
  .card {
    opacity: 0.97; 
    width: 100%;
    text-align: center;
    margin: auto;
  }
  .input {
    width: 480px;
    text-align: center;
  }
}

</style>
