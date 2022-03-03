<template>
  <div class="container mx-auto px-5 py-2">
    <div class=" text-5xl px-3 font-bold text-blue-900 my-5">
      Covid <span class="text-pink-700"> Registration</span>
    </div>
    <form ref="aaaa" @submit.prevent="addData">
      <div class="grid grid-cols-12 px-10">
        <div class="container mx-auto col-span-5 px-5 pb-5">
          <label
            for="small-input"
            class="text-lg font-medium text-gray-900 dark:text-gray-300"
            >Name</label
          >

          <input
            v-model="fname"
            type="text"
            class="block p-2.5 w-full text-blue-900     bg-gray-50 rounded-lg border-2 border-yellow-500 sm:text-xs focus:outline-none"
            placeholder="Your name"
            required
          />
        </div>
        <div class="col-span-5 pb-5">
          <label
            for="small-input"
            class="text-lg font-medium text-gray-900 dark:text-gray-300"
            >Last Name</label
          >
          <input
            v-model="lname"
            type="text"
            class="block p-2.5 w-full text-blue-900     bg-gray-50 rounded-lg border-2 border-yellow-500 sm:text-xs focus:outline-none"
            placeholder="Your last name"
            required
          />
        </div>
        <div class="col-span-2 px-5 pb-5">
          <label
            for="small-input"
            class="text-lg font-medium text-gray-900 dark:text-gray-300"
            >Age</label
          >
          <input
            id="small-input"
            v-model="age"
            min="1"
            max="120"
            type="number"
            class="block p-2.5 w-full text-blue-900     bg-gray-50 rounded-lg border-2 border-yellow-500 sm:text-xs focus:outline-none"
            placeholder="Your age"
            required
          />
        </div>
        <div class="col-span-4 px-5">
          <label
            for="email-adress-icon"
            class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300"
            >Your Email</label
          >
          <div class="relative">
            <div
              class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none"
            >
              <svg
                class="w-5 h-5 text-yellow-600 dark:text-gray-400"
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M2.003 5.884L10 9.882l7.997-3.998A2 2 0 0016 4H4a2 2 0 00-1.997 1.884z"
                ></path>
                <path
                  d="M18 8.118l-8 4-8-4V14a2 2 0 002 2h12a2 2 0 002-2V8.118z"
                ></path>
              </svg>
            </div>
            <input
              id="email-adress-icon"
              v-model="email"
              type="email"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              placeholder="name@flowbite.com"
              required
            />
          </div>
        </div>
        <div class="col-span-3 px-5">
          <label
            for="email-adress-icon"
            class="block mb-2 text-sm font-medium text-gray-900 dark:text-gray-300"
            >Your Phone</label
          >
          <div class="relative">
            <div
              class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="16"
                height="16"
                fill="currentColor"
                class="bi bi-telephone  text-yellow-600"
                viewBox="0 0 16 16"
              >
                <path
                  d="M3.654 1.328a.678.678 0 0 0-1.015-.063L1.605 2.3c-.483.484-.661 1.169-.45 1.77a17.568 17.568 0 0 0 4.168 6.608 17.569 17.569 0 0 0 6.608 4.168c.601.211 1.286.033 1.77-.45l1.034-1.034a.678.678 0 0 0-.063-1.015l-2.307-1.794a.678.678 0 0 0-.58-.122l-2.19.547a1.745 1.745 0 0 1-1.657-.459L5.482 8.062a1.745 1.745 0 0 1-.46-1.657l.548-2.19a.678.678 0 0 0-.122-.58L3.654 1.328zM1.884.511a1.745 1.745 0 0 1 2.612.163L6.29 2.98c.329.423.445.974.315 1.494l-.547 2.19a.678.678 0 0 0 .178.643l2.457 2.457a.678.678 0 0 0 .644.178l2.189-.547a1.745 1.745 0 0 1 1.494.315l2.306 1.794c.829.645.905 1.87.163 2.611l-1.034 1.034c-.74.74-1.846 1.065-2.877.702a18.634 18.634 0 0 1-7.01-4.42 18.634 18.634 0 0 1-4.42-7.009c-.362-1.03-.037-2.137.703-2.877L1.885.511z"
                />
              </svg>
            </div>
            <input
              id="email-adress-icon"
              v-model="phone"
              maxlength="10"
              minlength="10"
              type="text"
              class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
              placeholder="+1 (555) 555-5555"
              oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*?)\..*/g, '$1');"
              required
            />
          </div>
        </div>
        <div class="col-span-2 px-5 pb-5">
          <label
            for="small-input"
            class="text-lg font-medium text-gray-900 dark:text-gray-300"
            >Date</label
          >
          <VueTailwindPicker :date-range="true" @change="(v) => (checkin = v)">
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
              :value="checkin"
              datepicker
              datepicker-autohide
              type="text"
              class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm     bg-gray-50 rounded-lg  focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2"
              placeholder="Select date"
            />
          </VueTailwindPicker>
        </div>
        <div class="col-span-3 px-5 pb-5">
          <label
            for="countries"
            class="text-lg font-medium text-gray-900 dark:text-gray-300"
            >Covid Test Results</label
          >
          <select
            v-model="Atktest"
            class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
            
            required
          >
          <option value="" disabled selected>Select your test results</option>
            <option>Negative</option>
            <option>Positive</option>
          </select>
        </div>
        <div class="col-span-2 px-5">
          <button
            type="submit"
            class="text-white bg-gradient-to-br px-5 from-purple-600 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:ring-blue-300 dark:focus:ring-blue-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
          >
            Submit
          </button>
        </div>
      </div>
    </form>

    <TableView :DataTable="csDoc"></TableView>
  </div>
</template>

<script>
import { addDoc, collection, getDocs } from 'firebase/firestore'
import Vue from 'vue'
import VueTailwindPicker from 'vue-tailwind-picker'
import db from '../plugin/index.js'
import TableView from '../components/TableView.vue'

export default {
  components: {
    VueTailwindPicker,
    TableView,
  },
  data() {
    return {
      csDoc: [],
      fname: '',
      lname: '',
      email: '',
      phone: '',
      Atktest: '',
      age: '',
      checkin: '',
    }
  },
  mounted() {
    Vue.use(VueTailwindPicker)
    this.readData()
  },
  methods: {
    async addData() {
      try {
        const docRef = await addDoc(collection(db, 'csmju'), {
          date: this.checkin,
          email: this.email,
          phone: this.phone,
          Atktest: this.Atktest,
          age: this.age,
          fullname: this.fname + ' ' + this.lname,
          
        })
        this.date = ''
        this.email = ''
        this.phone = ''
        this.Atktest = ''
        this.age = ''
        this.fname = ''
        this.lname = ''
        this.checkin = ''
        console.log('Document written with ID: ', docRef.id)
        this.readData()
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
