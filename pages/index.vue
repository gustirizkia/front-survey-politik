<template>
  <div>
    <Bottombar />
    <div class="bg-gray-400">
      <div class="md:w-1/3 bg-white min-h-screen md:mx-auto px-3 pt-3">
        <div class="">
          <img
            src="https://images.unsplash.com/photo-1664574652984-5b5f769bef07?ixlib=rb-1.2.1&ixid=MnwxMjA3fDF8MHxlZGl0b3JpYWwtZmVlZHwxMDB8fHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60"
            alt=""
            class="w-12 h-12 object-cover rounded-full"
          />
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
}
</script>
