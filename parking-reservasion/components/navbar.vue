<template>
    <header class="bg-gray-100">
      <nav class="mx-auto flex items-center justify-between p-2 lg:px-8" aria-label="Global">
        <div class="flex lg:flex-1">
          <a href="#" class="-m-1.5 p-1.5">
            <span class="sr-only">Your Company</span>
            <img class="h-9 w-32" src="../assets/img/Screenshot_2023-10-12_151514-removebg-preview.png" alt="gambar" />
          </a>
        </div>
        <div class="flex lg:hidden">
          <button type="button" class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700" @click="mobileMenuOpen = true">
            <span class="sr-only">Open main menu</span>
            <Bars3Icon class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
        <PopoverGroup class="hidden lg:flex lg:gap-x-12">
          <a href="#" class="text-sm font-semibold leading-6 text-gray-900">Empty Parking Space</a>
          <div class="relative" @click="showNotifications">
            <BellIcon class="w-6 h-6 text-gray-500" />
            <!-- Tambahkan notifikasi di sini -->
            <div v-if="showNotification" class="absolute top-0 right-0 w-6 h-6 bg-red-500 rounded-full text-white flex items-center justify-center -mr-2 -mt-2">1</div>
          </div>
          <!-- Tambahkan Popover untuk menu "Company" -->
          <Popover>
            <template #default>
              <div @click="openUserMenu" class="cursor-pointer flex items-center -mt-1">
                <img
                  src="../assets/img/Screenshot_2023-10-12_151514-removebg-preview.png"
                  alt="Avatar Pengguna"
                  class="w-8 h-8 rounded-full mr-2 border border-black"
                />
              </div>
            </template>
          </Popover>
          <div @click="logout" class="text-sm font-semibold leading-6 text-gray-900 cursor-pointer">Log out</div>
        </PopoverGroup>
      </nav>
      <Dialog as="div" class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
        <div class="fixed inset-0 z-10" />
        <DialogPanel class="fixed inset-y-0 right-0 z-10 w-full overflow-y-auto bg-white px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10">
          <div class="flex items-center justify-between">
            <a href="#" class="-m-1.5 p-1.5">
              <span class="sr-only">Your Company</span>
              <img class="h-9 w-32" src="../assets/img/Screenshot_2023-10-12_151514-removebg-preview.png" alt="gambar" />
            </a>
            <button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-700" @click="mobileMenuOpen = false">
              <span class="sr-only">Close menu</span>
              <XMarkIcon class="h-6 w-6" aria-hidden="true" />
            </button>
          </div>
          <div class="mt-6 flow-root">
            <div class="-my-6 divide-y divide-gray-500/10">
              <div class="space-y-2 py-6">
                <a href="#" class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover-bg-gray-50">Profile</a>
                <div class="relative" @click="showNotifications">
                <a href="#" class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover-bg-gray-50">Notification</a>
                <div v-if="showNotification" class="absolute top-0 right-0 w-6 h-6 bg-red-500 rounded-full text-white flex items-center justify-center -mr-2 -mt-2">1</div>
                </div>
                <a href="#" class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold leading-7 text-gray-900 hover-bg-gray-50">Empty Parking Space</a>
                <div @click="logout" class="text-sm font-semibold leading-6 text-gray-900 cursor-pointer">Log out</div>
              </div>
            </div>
          </div>
        </DialogPanel>
      </Dialog>
    </header>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import {
    Dialog,
    DialogPanel,
    PopoverGroup,
  } from '@headlessui/vue';
  import {
    Bars3Icon,
    XMarkIcon,
    BellIcon,
  } from '@heroicons/vue/24/outline';
  
  const mobileMenuOpen = ref(false);
  const showNotification = ref(false);
  const isUserMenuOpen = ref(false);
  
  const showNotifications = () => {
    // Tambahkan logika untuk menampilkan notifikasi di sini
    // Anda dapat mengganti nilai `showNotification` sesuai dengan notifikasi yang sebenarnya
    showNotification.value = !showNotification.value;
  };
  
  const openUserMenu = () => {
    isUserMenuOpen.value = !isUserMenuOpen.value;
  };
  
  const logout = () => {
    // Implement your logout logic here
    console.log("User logged out");
  };
  </script>
  