<template>
  <div class='panel'>
    <div class="row text-center justify-content align-items flex-center q-mt-md">
      <q-input 
        v-model="text"
        label="Tracking Number" rounded outlined  class='input q-ma-sm col-md-7' color="orange-5">
        <template v-slot:prepend>
          <q-icon name="search" />
        </template>
        <template v-slot:append>
          <q-icon name="close" @click="text = ''" class="cursor-pointer" />
        </template>   
      </q-input>      
      <q-btn rounded class='col-md-2 q-ma-sm q-pa-sm' color='orange' label='Pesquisar' icon='search' />
      <q-btn rounded class='col-md-2 q-ma-sm q-pa-sm' color='blue' label='Adicionar' icon='fa-solid fa-plus-circle' />
    </div>
    <div class="row text-center justify-content align-items flex-center q-mt-md">

    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      text: ''
    }
  }
}
</script>


<style scoped>
@media (min-width: 900px) {
  .panel {
    width: 98%;
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
  }
}

</style>