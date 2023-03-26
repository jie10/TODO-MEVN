<script setup>
import { ref } from 'vue'
import { createApp } from 'vue'
const isShowModal = ref(false)

const toggleModal = () => {
  isShowModal.value = !isShowModal.value
}



createApp({
  data() {
    return {
      firstName: '',
      lastName: '',
      email:''
    }
  },
  methods:{
    showDeleteModal: false,
    closeModal: false
  }
}).mount('#app')
</script>

<template>
<div>
<div class=" h-screen w-screen flex justify-center items-center">
  <form class="bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 w-3/6 h-3/5 justify-items-center" action="#" method="POST">
    <div class="shadow sm:rounded-md">
      <div class=" px-4 py-5 sm:p-6">
        <div class="grid grid-cols-3 gap-6">
       
              
          <div class="col-span-3">
          <h1 class="text-4xl">CLIENT'S TODO-LIST</h1>
          </div>
           
          <div class="flex">
          <div class="col-span-3 sm:col-span-3 lg:col-span-2 ml-8">
            <label for="fname" class="block text-sm font-medium leading-6 text-gray-900">First Name</label>
            <input type="text" name="fname" id="fname"   class="mt-2 block  rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
          </div>

          <div class="col-span-3 sm:col-span-3 lg:col-span-2 ml-8">
            <label for="lname" class="block text-sm font-medium leading-6 text-gray-900">Last Name</label>
            <input type="text" name="lname" id="lname" autocomplete="address-level1" class="mt-2 block  rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
          </div>

          <div class=" ml-8 col-span-3 sm:col-span-3 lg:col-span-2 ">
            <label for="email" class="block text-sm font-medium leading-6 text-gray-900">Email</label>
            <input type="text" name="email" id="email" autocomplete="postal-code" class="mt-2 block  rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
          </div>
        </div>

        <div class=" px-8 py-3 text-right ml-64 mb-12 mt-4">
          <button type="button" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800" 
           v-on:click="toggleModal">Add</button>
        </div>

    </div>


    <div class="mt-10" >
    <t8ble class="table-auto">
      <thead>
        <tr>
          <th>First Name</th>
          <th>Last Name</th>
          <th>Email</th>
          <th>Edit</th>
          <th>Delete</th>
        </tr>
      </thead>


      <tbody >
        <tr >
          <td>{{ firstName }}</td>
          <td>{{ lastName }}</td>
          <td>{{ edit }}</td>
          <td><button type="button" class="text-white"><svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 26 26" stroke-width="1.5" stroke="green" class="w-8 h-8"   v-on:click="toggleModal">
            <path stroke-linecap="round" stroke-linejoin="round" d="M16.862 4.487l1.687-1.688a1.875 1.875 0 112.652 2.652L10.582 16.07a4.5 4.5 0 01-1.897 1.13L6 18l.8-2.685a4.5 4.5 0 011.13-1.897l8.932-8.931zm0 0L19.5 7.125M18 14v4.75A2.25 2.25 0 0115.75 21H5.25A2.25 2.25 0 013 18.75V8.25A2.25 2.25 0 015.25 6H10" />
          </svg>
          
        
          </button></td>
          <td> <button type="button" class="text-white" ><svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="red" class="w-8 h-8" >
            <path stroke-linecap="round" stroke-linejoin="round" d="M14.74 9l-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 01-2.244 2.077H8.084a2.25 2.25 0 01-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 00-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 013.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 00-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 00-7.5 0" />
          </svg>
          </button></td>
        </tr>
      </tbody>
    </t8ble>
    </div>
  </div>
    </div>
  </form>


  <!-- add user -->
  <div class="modal-content">
    <button type="button" class="close " v-on:click="showDeleteModal = false"></button>
    <span aria-hidden="true" class="close-button" @click="closeModal">&times;</span>
<div  class="overlay  border-solid border-2  border-indigo-600 rounded-lg ml-20 mt-18 py-5 px-20 " v-if="isShowModal">
  <form class="  w-1/3 h-1/5 justify-items-center" action="#" method="POST">
    <div class="flex-row-reverse">
      <div class=" ml-8 mt-5">
        <label for="fname" class="block text-sm font-medium leading-6 text-violet-700">First Name</label>
        <input type="text" name="fname" id="fname"   class="mt-2 block  rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>

      <div class="col-span-3 sm:col-span-3 lg:col-span-2 ml-8 mt-5">
        <label for="lname" class="block text-sm font-medium leading-6 text-violet-700">Last Name</label>
        <input type="text" name="lname" id="lname" autocomplete="address-level1" class="mt-2 block  rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>

      <div class=" ml-8 col-span-3 sm:col-span-3 lg:col-span-2 mt-5 ">
        <label for="email" class="block text-sm font-medium leading-6 text-violet-700">Email</label>
        <input type="text" name="email" id="email" autocomplete="postal-code" class="mt-2 block  rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6" />
      </div>
      <div class=" px-8 py-3 text-right ml-12  mb-12 mt-4">
        <button type="button" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800"  v-on:click="toggleModal">Edit</button>
      </div>
    </div>

  </form>
</div>
</div>

</div>
</div>

</template>

<style scoped>
.overlay{
  position: fixed;
  background-color: rgba(0, 0, 0, 0.5);
}
</style>
