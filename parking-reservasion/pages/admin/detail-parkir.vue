<template>
    <div class="bg-slate-50 min-h-screen">
        <div class="max-w-md w-3/4 mx-auto mt-16 p-2 bg-white rounded-lg shadow-lg shadow-black">
            <div class="flex">
                <img src="../../assets/img/Screenshot_2023-10-12_151514-removebg-preview.png" alt="Logo" class="w-24 h-16 justify-center" />
            </div>
            <form>
                <div class="mb-4">
          <svg id="barcode" class="w-full h-12"></svg>
        </div>
        <div class="mb-4">
          <label for="nomorPlat" class="text-gray-600">Nomor Plat :</label>
          <input type="text" id="nomorPlat" class="border rounded-lg w-full p-2" v-model="nomorPlat" disabled />
        </div>

        <div class="mb-4">
          <label for="merk" class="text-gray-600">Merk Kendaraan :</label>
          <input type="text" id="merk" class="border rounded-lg w-full p-2" v-model="merk" disabled />
        </div>

        <div class="mb-4">
          <label for="tanggal" class="text-gray-600">Tanggal:</label>
          <input type="date" id="tanggal" class="border rounded-lg w-full p-2" v-model="tanggal" disabled />
        </div>

        <div class="mb-4">
          <label for="waktu" class="text-gray-600">Waktu:</label>
          <input type="time" id="waktu" class="border rounded-lg w-full p-2" v-model="waktu" disabled />
        </div>

        <div class="mb-4">
          <label for="jenisKendaraan" class="text-gray-600">Jenis Kendaraan:</label>
          <input id="jenisKendaraan" class="border rounded-lg w-full p-2 block" v-model="jenisKendaraan" disabled/>
        </div>
        <div class="mb-4">
              <label for="status" class="block text-sm font-medium text-gray-700">Status</label>
              <select
                v-model="status"
                id="status"
                name="status"
                class="mt-1 p-2 w-full rounded-md border border-gray-300 focus:ring-indigo-600 focus:ring focus:ring-opacity-50"
              >
                <option value="approve">Approve</option>
                <option value="not_approve">Not Approve</option>
                <option value="pending">Pending</option>
              </select>
            </div>
        <button type="submit" class="bg-red-500 text-white justify-end flex rounded-lg py-2 px-4" v-if="showSubmitButton">Cancel</button>
      </form>
        </div>
    </div>
</template>

<script>
import JsBarcode from "jsbarcode";

    export default {
        data() {
    return {
      showSubmitButton: false, 
      nomorPlat: 'B35689UHU',
      merk: 'Honda',
      tanggal: '2023-12-12',
      waktu: '15:30',
      jenisKendaraan: 'Mobil',
      status: 'pending'
    };
  },
  mounted() {
    if (this.nomorPlat && this.merk && this.tanggal && this.waktu && this.jenisKendaraan) {
      this.showSubmitButton = false;
    } else {
        this.showSubmitButton = true
    }
    JsBarcode("#barcode", this.nomorPlat, {
      format: "CODE128",
      displayValue: false,
      width: 4,
      height: 80,
    });
  }
    }
</script>