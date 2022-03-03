<template>
  <div>
    <div class="flex flex-col">
      <div class="overflow-x-auto shadow-md sm:rounded-lg">
        <div class="inline-block min-w-full align-middle">
          <div class="overflow-hidden">
            <table
              class="min-w-full divide-y divide-gray-200 table-fixed dark:divide-gray-700"
            >
              <thead class="bg-gray-100 dark:bg-gray-700">
                <tr>
                  <th
                    scope="col"
                    class="py-3  px-3 text-xs font-medium tracking-wider text-left text-gray-700 uppercase dark:text-gray-400"
                  >
                    #
                  </th>
                  <th
                    scope="col"
                    class="py-3  px-3 text-xs font-medium tracking-wider text-left text-gray-700 uppercase dark:text-gray-400"
                  >
                    Date
                  </th>
                  <th
                    scope="col"
                    class="py-3  px-3 text-xs font-medium tracking-wider text-left text-gray-700 uppercase dark:text-gray-400"
                  >
                    Name
                  </th>
                  <th
                    scope="col"
                    class="py-3  px-3 text-xs font-medium tracking-wider text-left text-gray-700 uppercase dark:text-gray-400"
                  >
                    Age
                  </th>
                  <th
                    scope="col"
                    class="py-3  px-3 text-xs font-medium tracking-wider text-left text-gray-700 uppercase dark:text-gray-400"
                  >
                    Phone
                  </th>
                  <th
                    scope="col"
                    class="py-3  px-3 text-xs font-medium tracking-wider text-left text-gray-700 uppercase dark:text-gray-400"
                  >
                    Email
                  </th>
                  <th
                    scope="col"
                    class="py-3  px-3 text-xs font-medium tracking-wider text-left text-gray-700 uppercase dark:text-gray-400"
                  >
                    Covid Test
                  </th>
                </tr>
              </thead>
              <tbody
                v-for="(item, index) in DataTable"
                :key="index"
                class="bg-white divide-y divide-gray-200 dark:bg-gray-800 dark:divide-gray-700"
              >
                <tr
                  class="hover:bg-gray-100 dark:hover:bg-gray-700"
                  v-if="index >= (x - 1) * 5 && index < x * 5"
                  :style="{
                    color:
                      item.data.Atktest == 'Positive' ? '#db2777' : '#2563eb',
                  }"
                >
                  <td
                    class="py-4 px-3 text-sm font-bold whitespace-nowrap dark:text-white"
                  >
                    {{ index + 1 }}
                  </td>
                  <td
                    class="py-4 px-3 text-sm font-bold whitespace-nowrap dark:text-white"
                  >
                    {{ item.data.date }}
                  </td>
                  <td
                    class="py-4 px-3 text-sm font-bold whitespace-nowrap dark:text-white"
                  >
                    {{ item.data.fullname }}
                  </td>
                  <td
                    class="py-4 px-3 text-sm font-bold whitespace-nowrap dark:text-white"
                  >
                    {{ item.data.age }}
                  </td>
                  <td
                    class="py-4  px-3 text-sm font-bold whitespace-nowrap dark:text-white"
                  >
                    {{ item.data.phone }}
                  </td>
                  <td
                    class="py-4  px-3 text-sm font-bold whitespace-nowrap dark:text-white"
                  >
                    {{ item.data.email }}
                  </td>
                  <td
                    class="py-4  px-3 text-sm font-bold whitespace-nowrap dark:text-white"
                  >
                    {{ item.data.Atktest }}
                  </td>
                </tr>
              </tbody>
            </table>
            <div class="flex justify-center">
              <button
                @click="x == 1 ? (x = 1) : x--"
                class="px-10 text-white bg-gradient-to-r from-purple-500 to-pink-500 hover:bg-gradient-to-l focus:ring-4 focus:ring-purple-200 dark:focus:ring-purple-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
              >
                Prev
              </button>
              <div
                class="text-white bg-gradient-to-r from-pink-500 to-pink-700 hover:bg-gradient-to-br focus:ring-4 focus:ring-red-300 dark:focus:ring-red-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
              >
                {{ x }}
              </div>
              <button
                class="px-10 text-white font-semibold bg-gradient-to-r from-pink-500 to-purple-500 hover:bg-gradient-to-l focus:ring-4 focus:ring-purple-200 dark:focus:ring-purple-800 font-medium rounded-lg text-sm px-5 py-2.5 text-center mr-2 mb-2"
                @click="DataTable.length / 5 - 1 < x - 1 ? x : x++"
              >
                Next
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['DataTable'],
  data() {
    return {
      x: 1,
    }
  },
}
</script>

<style></style>
