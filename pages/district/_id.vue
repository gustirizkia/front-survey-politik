<template>
  <div class="bg-blue-50 min-h-screen pb-20">
    <Topbar />
    <div class="px-4 -mt-16">
      <div class="bg-white rounded-lg p-4">
        <div class="text-lg font-semibold">Statistik {{ $route.query.q }}</div>

        <div class="flex justify-between">
          <div class="">
            <div class="">
              <div class="text-left text-xs font-normal text-neutral-500">
                Jumlah Relawan
              </div>
              <div class="text-left text-xl font-semibold text-indigo-700">
                900
              </div>
            </div>
            <div class="mt-6">
              <div class="text-left text-xs font-normal text-neutral-500">
                Jumlah Dukungan
              </div>
              <div class="text-left text-xl font-semibold text-indigo-700">
                1000
              </div>
            </div>
          </div>
          <div class="">
            <div class="">
              <div class="text-right text-xs font-normal text-neutral-500">
                Target Dukungan
              </div>
              <div class="text-right text-xl font-semibold text-indigo-700">
                800
              </div>
            </div>
            <div class="mt-6">
              <div class="text-right text-xs font-normal text-neutral-500">
                Jumlah Dukungan
              </div>
              <div class="text-right text-xl font-semibold text-indigo-700">
                80%
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="mt-3 bg-white p-4">
      <div class="flex justify-between mb-6">
        <div class="font-medium">Kinerja relawan</div>
        <div class="text-indigo-700">Lihat semua</div>
      </div>
      <div class="" v-for="item in response.kecamatan" :key="item.id">
        <div class="my-3">
          <nuxt-link :to="'district/' + item.id">
            <div class="border p-2 rounded-lg">
              <div class="font-medium">{{ item.nama }}</div>
              <div class="flex justify-between mt-3">
                <div class="">
                  <div class="text-sm text-gray-500">Dukungan suara</div>
                  <div class="font-medium text-green-500">{{ item.id }}</div>
                </div>
                <div class="">
                  <div class="text-sm text-gray-500">Suara abu-abu</div>
                  <div class="font-medium text-gray-500 text-center">200</div>
                </div>
                <div class="">
                  <div class="text-sm text-gray-500">Tidak memihak</div>
                  <div class="font-medium text-gray-500 text-right">100</div>
                </div>
              </div>
            </div>
          </nuxt-link>
        </div>
      </div>
    </div>

    <Bottombar />
  </div>
</template>
<script>
export default {
  data() {
    return {}
  },
  mounted() {},
  async asyncData({ params, $axios }) {
    console.log('params.id', params.id)
    let response = await $axios.$get(
      `https://dev.farizdotid.com/api/daerahindonesia/kecamatan?id_kota=${params.id}`
    )
    return { response }
  },
}
</script>
