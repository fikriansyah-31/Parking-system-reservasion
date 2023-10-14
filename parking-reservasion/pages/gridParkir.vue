<template>
    <div>
      <Navbar />
      <div class="min-h-screen bg-gray-800 flex justify-center items-center">
        <div class="max-w-md w-3/4 mx-auto  p-4 bg-white rounded-lg shadow-lg">
          <h1 class="text-2xl font-semibold mb-4 sm:text-center">Form Kendaraan</h1>
          <div class="mb-4 text-center">
            <a href="#" class="text-indigo-600 font-medium text-lg mr-2">
              Empty Parking:
            </a>
            <span class="text-indigo-600 font-medium text-lg">{{ emptyParkingSpaces }}</span>
          </div>
          <form @submit.prevent="submitForm">
            <div class="mb-4">
              <label for="licensePlate" class="block text-sm font-medium text-gray-700">Nomor Plat</label>
              <input
                v-model="vehicle.licensePlate"
                type="text"
                id="licensePlate"
                name="licensePlate"
                class="mt-1 p-2 w-full rounded-md border border-gray-300 focus:ring-indigo-600 focus:ring focus:ring-opacity-50"
              />
            </div>
            <div class="mb-4">
              <label for="brand" class="block text-sm font-medium text-gray-700">Merk Kendaraan</label>
              <input
                v-model="vehicle.brand"
                type="text"
                id="brand"
                name="brand"
                class="mt-1 p-2 w-full rounded-md border border-gray-300 focus:ring-indigo-600 focus:ring focus:ring-opacity-50"
              />
            </div>
            <div class="mb-4">
              <label for="date" class="block text-sm font-medium text-gray-700">Tanggal</label>
              <input
                v-model="vehicle.date"
                type="date"
                id="date"
                name="date"
                class="mt-1 p-2 w-full rounded-md border border-gray-300 focus:ring-indigo-600 focus:ring focus:ring-opacity-50"
              />
            </div>
            <div class="mb-4">
              <label for="time" class="block text-sm font-medium text-gray-700">Jam dan Menit</label>
              <input
                v-model="vehicle.time"
                type="time"
                id="time"
                name="time"
                class="mt-1 p-2 w-full rounded-md border border-gray-300 focus:ring-indigo-600 focus:ring focus:ring-opacity-50"
              />
            </div>
            <div class="mb-4">
              <label for="vehicleType" class="block text-sm font-medium text-gray-700">Jenis Kendaraan</label>
              <select
                v-model="vehicle.vehicleType"
                id="vehicleType"
                name="vehicleType"
                class="mt-1 p-2 w-full rounded-md border border-gray-300 focus:ring-indigo-600 focus:ring focus:ring-opacity-50"
              >
                <option value="mobil">Mobil</option>
                <option value="motor">Motor</option>
                <option value="bus_truk">Bus/Truk</option>
                <option value="lainya">Lainya</option>
              </select>
            </div>
            <div class="mb-4">
              <button type="submit" class="px-4 py-2 bg-indigo-600 text-white w-full rounded-md hover:bg-indigo-500">
                Submit
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import Navbar from '../components/navbar.vue';

  
  export default {
    components: {
      Navbar,
    },
    data() {
      return {
        vehicle: {
          licensePlate: '',
          brand: '',
          vehicleType: '',
          date: '', 
          time: '',
        },
        emptyParkingSpaces: 50,
      };
    },
    methods: {
      submitForm() {
        this.$emit('vehicle-submitted', this.vehicle); // Mengirimkan data kendaraan
        this.emptyParkingSpaces -= 1;
      },
    },
  };
  </script>
  