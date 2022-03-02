<template>
  <!-- <div class="container mx-auto px-5 py-5">
    <div class="grid">
      <h1>This is an about page</h1>
      <button class="col-span-2">sadsasd</button>
      <button
        class=" bg-yellow-600 px-2 py-1 rounded-lg shadow-lg"
        @click="addData()"
      >
        เพิ่มข้อมูล
      </button>
      <button class="text-green-500" @click="readData()">อ่านข้อมูล</button>

      {{ csDoc }}
      Name <input  v-model="name" class="gap-8 bg-red" />
    </div>
  </div> -->
  <div class="container mx-auto px-5 py-2">
    <div class="text-5xl px-3 font-bold text-blue-900 my-5">
      Covid <span class="text-pink-700"> Registration</span>
    </div>
    <div class="grid grid-cols-12">
      <div class="container mx-auto col-span-5 px-10 pb-5">
        <label
          for="small-input"
          class="text-lg font-medium text-gray-900 dark:text-gray-300"
          >Name</label
        >

        <input
          id="small-input"
          type="text"
          class="block p-1 w-full text-blue-900 focus:bg-red-100 bg-red-50 rounded-lg border-2 border-yellow-500 sm:text-xs focus:outline-none"
        />
      </div>
      <div class="container mx-auto col-span-5 px-10 pb-5">
        <label
          for="small-input"
          class="text-lg font-medium text-gray-900 dark:text-gray-300"
          >Last Name</label
        >
        <input
          id="small-input"
          type="text"
          class="block p-1 w-full text-blue-900 focus:bg-red-100 bg-red-50 rounded-lg border-2 border-yellow-500 sm:text-xs focus:outline-none"
        />
      </div>
      <div class="container mx-auto col-span-2 px-10 pb-5">
        <label
          for="small-input"
          class="text-lg font-medium text-gray-900 dark:text-gray-300"
          >Age</label
        >
        <input
          id="small-input"
          type="text"
          class="block p-1 w-full text-blue-900 focus:bg-red-100 bg-red-50 rounded-lg border-2 border-yellow-500 sm:text-xs focus:outline-none"
        />
      </div>
      <div>
        <div class="relative">
          <div
            class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none"
          >
            <svg
              class="w-5 h-5 text-gray-500 dark:text-gray-400"
              fill="currentColor"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M6 2a1 1 0 00-1 1v1H4a2 2 0 00-2 2v10a2 2 0 002 2h12a2 2 0 002-2V6a2 2 0 00-2-2h-1V3a1 1 0 10-2 0v1H7V3a1 1 0 00-1-1zm0 5a1 1 0 000 2h8a1 1 0 100-2H6z"
                clip-rule="evenodd"
              ></path>
            </svg>
          </div>
          <input
            datepicker
            datepicker-autohide
            type="text"
            class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
            placeholder="Select date"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { addDoc, collection, getDocs } from 'firebase/firestore'
import db from '../plugin/index.js'

export default {
  data() {
    return {
      csDoc: [],
      name: '',
    }
  },
  methods: {
    async addData() {
      try {
        const docRef = await addDoc(collection(db, 'csmju'), {
          first: this.name,
          middle: 'แซ่เอี้ยว',
          born: 1912,
        })
        console.log('Document written with ID: ', docRef.id)
      } catch (e) {
        console.error('Error adding document: ', e)
      }
    },
    async readData() {
      this.csDoc = []
      const querySnapshot = await getDocs(collection(db, 'csmju'))
      querySnapshot.forEach((doc) => {
        console.log(`${doc.id} => ${doc.data()}`)
        this.csDoc.push({ id: doc.id, data: doc.data() })
      })
    },
  },
}
</script>

<style></style>
