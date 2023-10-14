<template>
    <NavbarAdmin />
    <div class="table-container min-h-screen">
        <div class="flex justify-end">

            <input
            v-model="searchTerm"
            type="text"
            class="w-60 p-2 border rounded-lg mb-2 bg-gray-100 ms-3 placeholder-slate-500 mt-5 "
            placeholder="Nomor Plat"
            style="position: sticky; top: 0; background-color: white; z-index: 1;"
            
            />
        </div>
        <table class="min-w-full divide-y divide-black border">
        <thead>
          <tr>
            <th class="px-6 py-3 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider">
              Nomor Plat
            </th>
            <th class="px-6 py-3 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider">
              Merk Kendaraan
            </th>
            <th class="px-6 py-3 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider">
              Tanggal
            </th>
            <th class="px-6 py-3 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider">
              Waktu
            </th>
            <th class="px-6 py-3 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider">
              Jenis Kendaraan
            </th>
            <th class="px-6 py-3 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider">
              Status
            </th>
            <th class="px-6 py-3 bg-gray-50 text-left text-xs leading-4 font-medium text-gray-500 uppercase tracking-wider">
              Action
            </th>
          </tr>
        </thead>
        <tbody>
          <!-- Loop through your data and create rows -->
          <tr v-for="(item, index) in data" :key="index">
            <td class="px-6 py-4 whitespace-no-wrap">{{ item.nomorPlat }}</td>
            <td class="px-6 py-4 whitespace-no-wrap">{{ item.merk }}</td>
            <td class="px-6 py-4 whitespace-no-wrap">{{ item.tanggal }}</td>
            <td class="px-6 py-4 whitespace-no-wrap">{{ item.waktu }}</td>
            <td class="px-6 py-4 whitespace-no-wrap">{{ item.jenisKendaraan }}</td>
            <td class="px-6 py-4 whitespace-no-wrap">{{ item.status }}</td>
            <td class="px-6 py-4 whitespace-no-wrap text-right text-sm leading-5 font-medium">
              <div class="flex items-center">
                <a href="#" @click="viewDetail(index)" class="text-blue-600 hover:text-blue-900 mr-3">
                  <svg
                    class="w-5 h-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    viewBox="0 0 24 24"
                  >
                    <path d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"></path>
                    <path
                      d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm3 10a1 1 0 01-2 0 1 1 0 012 0z"
                    ></path>
                  </svg>
                </a>
                <a href="#" @click="deleteItem(index)" class="text-red-600 hover:text-red-900">
                  <svg
                    class="w-5 h-5"
                    fill="none"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    viewBox="0 0 24 24"
                  >
                    <path d="M6 18L18 6M6 6l12 12"></path>
                  </svg>
                </a>
              </div>
            </td>
          </tr>
        </tbody>
        
      </table>
    </div>
  </template>
  
  
  <script>
  import NavbarAdmin from '../components/navbarAdmin.vue';

  export default {
    components: {
      NavbarAdmin
    },
    data() {
      return {
        data: [
          {
            nomorPlat: 'ABC123',
            merk: 'Toyota',
            tanggal: '2023-12-01',
            waktu: '09:30',
            jenisKendaraan: 'Mobil',
            status: 'Approved',
          },
        ],
        searchTerm: '', 
      };
    },
    computed: {
  filteredData() {
    // Fungsi untuk memfilter data berdasarkan searchTerm
    return this.data.filter(item =>
      item.nomorPlat.toLowerCase().includes(this.searchTerm.toLowerCase())
    );
  },
},
    methods: {
      viewDetail(index) {
        console.log('View details for item at index', index);
      },
      deleteItem(index) {
        console.log('Delete item at index', index);
        this.data.splice(index, 1);
      },
    },
  };
  </script>
  
  <style scoped >
    .table-container {
        overflow-x: auto;
        max-width: 100%;
    }
    </style>