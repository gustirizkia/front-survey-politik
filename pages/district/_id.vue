<template>
  <div class="bg-blue-50 min-h-screen pb-20">
    <div
      class="rounded-t-none rounded-b-3xl pb-20 bg-indigo-700 px-4 py-4 text-white flex items-center justify-between"
    >
      <div @click="$router.back()" class="flex items-center">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          fill="currentColor"
          class="w-6 h-6"
        >
          <path
            fill-rule="evenodd"
            d="M7.72 12.53a.75.75 0 010-1.06l7.5-7.5a.75.75 0 111.06 1.06L9.31 12l6.97 6.97a.75.75 0 11-1.06 1.06l-7.5-7.5z"
            clip-rule="evenodd"
          />
        </svg>
        <div class="text-white ml-2">Back</div>
      </div>
      <div class="">
        <svg
          width="19"
          height="21"
          viewBox="0 0 19 21"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M17.6365 14.4989C17.5586 14.4052 17.4822 14.3114 17.4072 14.2209C16.376 12.9736 15.7521 12.2208 15.7521 8.68969C15.7521 6.86156 15.3147 5.36156 14.4527 4.23656C13.8171 3.40547 12.9579 2.775 11.8254 2.30906C11.8108 2.30096 11.7978 2.29032 11.7869 2.27766C11.3796 0.913594 10.2649 0 9.00771 0C7.75052 0 6.6363 0.913594 6.22896 2.27625C6.21809 2.28845 6.20525 2.29875 6.19099 2.30672C3.54818 3.39469 2.2638 5.48203 2.2638 8.68828C2.2638 12.2208 1.64083 12.9736 0.608645 14.2195C0.533645 14.31 0.457239 14.4019 0.379427 14.4975C0.178427 14.7399 0.0510772 15.0348 0.0124486 15.3473C-0.0261799 15.6598 0.0255296 15.9769 0.161458 16.2609C0.450677 16.8703 1.06708 17.2486 1.77068 17.2486H16.2499C16.9502 17.2486 17.5624 16.8708 17.8526 16.2642C17.9891 15.9801 18.0413 15.6628 18.003 15.3499C17.9647 15.037 17.8375 14.7417 17.6365 14.4989ZM9.00771 21C9.68507 20.9995 10.3497 20.8156 10.931 20.4679C11.5123 20.1202 11.9887 19.6217 12.3096 19.0252C12.3247 18.9966 12.3322 18.9646 12.3313 18.9322C12.3304 18.8999 12.3211 18.8684 12.3044 18.8407C12.2877 18.813 12.2641 18.7901 12.2359 18.7742C12.2078 18.7583 12.176 18.75 12.1436 18.75H5.87271C5.84033 18.7499 5.80847 18.7582 5.78024 18.774C5.75201 18.7899 5.72836 18.8128 5.71161 18.8405C5.69485 18.8682 5.68556 18.8997 5.68463 18.9321C5.6837 18.9645 5.69117 18.9965 5.7063 19.0252C6.02718 19.6216 6.50348 20.1201 7.08471 20.4678C7.66594 20.8155 8.33043 20.9994 9.00771 21Z"
            fill="white"
          />
        </svg>
      </div>
    </div>
    <div class="px-4 -mt-16">
      <div class="bg-white rounded-lg p-4">
        <div class="text-lg font-semibold mb-4">
          Statistik {{ $route.query.q }}
        </div>

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
