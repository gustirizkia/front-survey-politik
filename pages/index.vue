<template>
  <div>
    <Bottombar />
    <div class="bg-gray-400">
      <div class="md:w-1/3 bg-white min-h-screen md:mx-auto px-3 pt-3 pb-20">
        <div class="flex">
          <img
            src="https://images.unsplash.com/photo-1664574652984-5b5f769bef07?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHwxMDB8fHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60"
            alt=""
            class="w-12 h-12 object-cover rounded-lg"
          />
          <div class="text-gray-700 font-semibold ml-3 text-xl my-auto">
            Gusti
          </div>
        </div>
        <!-- banner image -->
        <div class="mt-10">
          <img
            src="~/assets/banner-home-mobile.jpg"
            class="rounded-xl"
            alt=""
          />
        </div>
        <!-- end banner -->

        <!-- artikel -->
        <div class="mt-10">
          <div class="flex justify-between">
            <div class="text-xl font-semibold text-gray-800">
              Artikel Terbaru
            </div>
            <nuxt-link to="" class="text-green-700 font-semibold text-lg">
              Lihat semua
            </nuxt-link>
          </div>

          <div class="mt-4">
            <div
              class="border rounded-lg flex mb-4"
              v-for="(item, index) in artikels"
              :key="index"
            >
              <img
                :src="item.thumbnail"
                class="w-16 object-cover rounded-l-lg"
                alt=""
              />
              <div class="p-4">
                {{ item.title }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bottombar from '../components/bottombar.vue'
export default {
  name: 'IndexPage',
  components: { Bottombar },
  data() {
    return {
      artikels: [],
    }
  },
  mounted() {
    this.getArtikel()
  },
  methods: {
    async getArtikel() {
      let response = await this.$axios
        .$get('https://api-berita-indonesia.vercel.app/antara/terbaru/')
        .then((res) => {
          this.artikels = res.data.posts
        })
    },
  },
}
</script>
