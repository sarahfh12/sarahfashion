<template>
  <div class="row">
    <div class="col-md-12">
      <h1>Contact</h1>
      <peta />
    </div>
    <div class="col-md-12">
      <FormContact />
    </div>
  </div>
</template>

<script>
import peta from '../components/Peta.vue'
import FormContact from '../components/FormContact.vue'
export default{
    components: {
      peta,
      FormContact,
    }
  }
</script>

