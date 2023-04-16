<template>
  <div>
    <div class="md:w-1/2 mx-auto bg-blue-50 pb-20 min-h-screen">
      <Topbar />
      <div class="-mt-16">
        <div class="bg-white">
          <img src="~/assets/images/chart2.png" class="" />
        </div>
      </div>

      <div class="bg-white p-4 mt-3">
        <div class="" v-for="item in kabupatens" :key="item.id">
          <div class="my-3">
            <div class="border p-2 rounded-lg">
              <div class="font-medium">{{ item.nama }}</div>
              <div class="flex justify-between mt-3">
                <div class="">
                  <div class="text-sm text-gray-500">Dukungan</div>
                  <div class="font-medium text-green-500">{{ item.id }}</div>
                </div>
                <div class="">
                  <div class="text-sm text-gray-500">Suara abu-abu</div>
                  <div class="font-medium text-gray-500 text-center">200</div>
                </div>
                <div class="">
                  <div class="text-sm text-gray-500">Total</div>
                  <div class="font-medium text-gray-500 text-right">700</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="">
        <Bottombar />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      kabupatens: [],
    }
  },
  methods: {
    async fetchKabupaten() {
      await this.$axios
        .get(
          'https://dev.farizdotid.com/api/daerahindonesia/kota?id_provinsi=32'
        )
        .then((res) => {
          this.kabupatens = res.data.kota_kabupaten
        })
    },
  },
  mounted() {
    this.fetchKabupaten()
  },
}
</script>
