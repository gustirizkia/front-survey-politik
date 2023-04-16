<template>
  <div class="bg-blue-50 min-h-screen pb-20">
    <Bottombar />
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
        <div class="text-white ml-2">Pengaturan akun</div>
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
      <div class="bg-white p-4 rounded-lg">
        <div class="mb-5 flex justify-center">
          <div class="relative inline-block mx-auto">
            <img
              src="https://images.unsplash.com/photo-1681579682482-fb007782d779?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1113&q=80"
              class="w-24 h-24 mx-auto object-cover rounded-full"
              alt=""
            />
            <div
              class="bg-gray-200 text-gray-500 h-10 w-10 flex flex-col items-center justify-center rounded-full absolute bottom-0 -right-2"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 24 24"
                fill="currentColor"
                class="w-6 h-6"
              >
                <path d="M12 9a3.75 3.75 0 100 7.5A3.75 3.75 0 0012 9z" />
                <path
                  fill-rule="evenodd"
                  d="M9.344 3.071a49.52 49.52 0 015.312 0c.967.052 1.83.585 2.332 1.39l.821 1.317c.24.383.645.643 1.11.71.386.054.77.113 1.152.177 1.432.239 2.429 1.493 2.429 2.909V18a3 3 0 01-3 3h-15a3 3 0 01-3-3V9.574c0-1.416.997-2.67 2.429-2.909.382-.064.766-.123 1.151-.178a1.56 1.56 0 001.11-.71l.822-1.315a2.942 2.942 0 012.332-1.39zM6.75 12.75a5.25 5.25 0 1110.5 0 5.25 5.25 0 01-10.5 0zm12-1.5a.75.75 0 100-1.5.75.75 0 000 1.5z"
                  clip-rule="evenodd"
                />
              </svg>
            </div>
          </div>
        </div>
        <div class="mb-5">
          <label for="name" class="font-medium">Nama</label>
          <input
            type="text"
            class="border rounded-lg p-2 w-full mt-3"
            placeholder="Nama"
            value="Yoga Wahyudi"
          />
        </div>
        <div class="mb-5">
          <label for="name" class="font-medium">Email</label>
          <input
            type="text"
            class="border rounded-lg p-2 w-full mt-3"
            placeholder="Nama"
            value="Yoga Wahyudi"
          />
        </div>
        <div class="mb-5">
          <label for="name" class="font-medium">Nomor WhatsApp</label>
          <input
            type="number"
            class="border rounded-lg p-2 w-full mt-3"
            placeholder="Nama"
            value="08991169449"
          />
        </div>
        <div class="mb-5">
          <label for="name" class="font-medium">Password</label>
          <input
            type="text"
            class="border rounded-lg p-2 w-full mt-3"
            placeholder="Nama"
            value="Yoga Wahyudi"
          />
        </div>
        <div class="mb-5">
          <label for="name" class="font-medium">Konfirmasi Password Baru</label>
          <input
            type="text"
            class="border rounded-lg p-2 w-full mt-3"
            placeholder="Nama"
            value="Yoga Wahyudi"
          />
        </div>
        <div
          class="bg-indigo-700 py-3 text-white font-medium text-center rounded-lg"
        >
          Simpan
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {}
</script>
