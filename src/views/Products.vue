<template>
  <div class="container">
    <h1>Products</h1>
    <div class="row">
      <div class="col-md12">
        <div class="text-muted" v-if="loading"></div>
        <div class="row">
          <div class="col-md-4" v-for="produk in products" :key="produk.id">
            <div class="card mb-4">
              <div class="card-header">
                <img :src="produk.foto" width="100%" class="img-thumb">
              </div>
              <div class="card-body">
                <h4>{{ produk.nama }}</h4>
                <h4>Rp{{ produk.harga }}</h4>
                <a v-if="produk.stok > 0" :href="produk.link_eksternal" class="btn btn-danger btn-block">beli</a>
                <a v-else href = "#" class="disable btn btn-dark btn-block" >Stok habis!!</a>
              </div>
            </div>
          </div>
        </div>
      </div>
   </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      products: "",
      loading: true,
    };
  },
  mounted() {
    this.getProduk();
  },
  methods: {
    async getProduk() {
      let { data, error } = await this.$supabase.from("tb_produk").select();
      if (data) this.products = data;
      if (error) console.error(error);
    },
  },
};
</script>

<style lang="scss" scoped></style>
