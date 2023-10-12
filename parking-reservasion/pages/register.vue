<template>
  <div class="flex min-h-full flex-1 flex-col justify-center px-6 py-12 lg:px-8">
    <div class="sm:mx-auto sm:w-full sm:max-w-sm">
      <h2 class="mt-10 text-center text-2xl font-bold leading-9 tracking-tight text-gray-900">Register for Parking Service</h2>
    </div>
    <div class="mt-5 sm:mx-auto sm:w-full sm:max-w-sm">
      <form class="space-y-6 bg-white border p-6 rounded-lg" action="#" method="POST">
        <div>
          <label for="name" class="block text-sm font-medium leading-6 text-gray-900">Full Name</label>
          <div class="mt-2">
            <input
              id="name"
              name="name"
              type="text"
              autocomplete="name"
              required
              class="block w-full rounded-md border border-gray-300 py-2 px-3 text-gray-900 shadow-sm focus:ring-2 focus:ring-indigo-600 focus:ring-inset sm:text-sm sm:leading-5"
            />
          </div>
        </div>
        
        <div>
          <label for="email" class="block text-sm font-medium leading-6 text-gray-900">Email address</label>
          <div class="mt-2">
            <input
              id="email"
              name="email"
              type="email"
              autocomplete="email"
              required
              class="block w-full rounded-md border border-gray-300 py-2 px-3 text-gray-900 shadow-sm focus:ring-2 focus:ring-indigo-600 focus:ring-inset sm:text-sm sm:leading-5"
            />
          </div>
        </div>

        <div>
          <label for="password" class="block text-sm font-medium leading-6 text-gray-900">Password</label>
          <div class="mt-2">
            <input
              id="password"
              name="password"
              type="password"
              autocomplete="new-password"
              required
              class="block w-full rounded-md border border-gray-300 py-2 px-3 text-gray-900 shadow-sm focus:ring-2 focus:ring-indigo-600 focus:ring-inset sm:text-sm sm:leading-5"
            />
          </div>
        </div>

        <div>
          <label for="confirmPassword" class="block text-sm font-medium leading-6 text-gray-900">Confirm Password</label>
          <div class="mt-2">
            <input
              id="confirmPassword"
              name="confirmPassword"
              type="password"
              autocomplete="new-password"
              required
              class="block w-full rounded-md border border-gray-300 py-2 px-3 text-gray-900 shadow-sm focus:ring-2 focus:ring-indigo-600 focus:ring-inset sm:text-sm sm:leading-5"
            />
          </div>
        </div>
        
        <div>
          <button type="submit" class="w-full flex justify-center rounded-md bg-indigo-600 px-3 py-2 text-sm font-semibold leading-5 text-white shadow-sm hover:bg-indigo-500 focus:ring-2 focus:ring-inset focus:ring-indigo-600">Register</button>
        </div>
        
        <p class="flex justify-center items-center"> or</p>
        <div class="mt-4">
          <a
            href="#"
            class="block w-full rounded-md border border-gray-300 py-2 text-center text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50 hover:text-indigo-600 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-5"
          >
            <span class="mr-2">
              <i class="fa fa-google text-indigo-600"></i>
            </span>
            Register with Google
          </a>
        </div>
      </form>
    </div>
  </div>
</template>
