<template>
  <div class="bg-gray-200 min-h-screen">
    <div class="md:w-1/2 mx-auto bg-blue-50 pb-20 min-h-screen">
      <Topbar />

      <div class="px-4 -mt-16">
        <div class="rounded-lg bg-white p-4">
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

      <div class="bg-white mt-2 p-4">
        <div class="mb-3">
          <div class="flex justify-between">
            <div class="font-medium">Hasil dukungan</div>
            <div class="text-indigo-700">Lihat semua</div>
          </div>
          <div class="mt-3 overflow-x-auto flex pb-1">
            <div class="" v-for="item in kabupatens" :key="item.id">
              <div class="shadow-md rounded-lg bg-white whitespace-nowrap mr-3">
                <div
                  class="rounded-t-lg rounded-b-none bg-indigo-700 p-2 text-white"
                >
                  {{ item.nama }}
                </div>
                <div class="p-2">
                  <div class="text-gray-800 text-xl font-medium">
                    {{ item.id }}
                  </div>
                  <div class="text-right text-xs font-normal text-indigo-700">
                    Detail
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="mb-3">
          <div class="flex justify-between">
            <div class="font-medium">Suara abu-abu</div>
            <div class="text-indigo-700">Lihat semua</div>
          </div>
          <div class="mt-3 overflow-x-auto flex pb-1">
            <div class="" v-for="item in kabupatens" :key="item.id">
              <div class="shadow-md rounded-lg bg-white mr-3">
                <div
                  class="rounded-t-lg rounded-b-none bg-gray-500 p-2 text-white whitespace-nowrap"
                >
                  {{ item.nama }}
                </div>
                <div class="p-2">
                  <div class="text-gray-800 text-xl font-medium">
                    {{ item.id }}
                  </div>
                  <div class="text-right text-xs font-normal text-gray-700">
                    Detail
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="mb-3">
          <div class="flex justify-between">
            <div class="font-medium">Tidak memihak</div>
            <div class="text-indigo-700">Lihat semua</div>
          </div>
          <div class="mt-3 overflow-x-auto flex pb-1">
            <div class="" v-for="item in kabupatens" :key="item.id">
              <div class="shadow-md rounded-lg bg-white mr-3">
                <div
                  class="rounded-t-lg rounded-b-none text-sm bg-red-500 p-2 text-white whitespace-nowrap"
                >
                  {{ item.nama }}
                </div>
                <div class="p-2">
                  <div class="text-red-800 text-xl font-medium">
                    {{ item.id }}
                  </div>
                  <div class="text-right text-xs font-normal text-red-700">
                    Detail
                  </div>
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
        <div class="" v-for="item in kabupatens" :key="item.id">
          <div class="my-3">
            <nuxt-link :to="'district/' + item.id + '?q=' + item.nama">
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
          'http://dev.farizdotid.com/api/daerahindonesia/kota?id_provinsi=32'
        )
        .then((res) => {
          let tempArray = res.data.kota_kabupaten
          this.kabupatens = tempArray
          // tempArray.forEach((element) => {
          //   let nama = element.nama.split(' ')
          //   nama = nama.slice(1, nama.length)
          //   let tempData = {
          //     nama: nama.join(' '),
          //     id: element.id,
          //     id_provinsi: element.id_provinsi,
          //   }

          //   this.kabupatens.push(tempData)
          // })
        })
    },
  },
  mounted() {
    this.fetchKabupaten()
  },
}
</script>
