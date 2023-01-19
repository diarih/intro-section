<script setup lang="ts">
import { ref } from "vue";

const isMenuOpen = ref(false);
const isFeatureOpen = ref(false);
const isCompanyOpen = ref(false);

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value;
}

function toggleCompany() {
  isCompanyOpen.value = !isCompanyOpen.value;
}

console.log(isCompanyOpen.value);
</script>

<template>
  <div class="md:px-2 px-0">
    <nav class="bg-white py-6 relative">
      <div class="container flex flex-wrap items-center md:flex-no-wrap mx-auto">
        <a href="#"
          ><img src="./assets/logo.svg" class="mr-3 h-6 md:ml-0 ml-3" alt="Snap Logo"
        /></a>
        <div class="ml-auto md:hidden">
          <button
            class="flex items-center px-3 py-2"
            @click="isMenuOpen = !isMenuOpen"
            type="button"
          >
            <img src="./assets/icon-menu.svg" alt="todo icon" />
          </button>
          <div>
            <div
              class="fixed top-0 right-0 h-screen w-52 bg-white z-50 px-6 py-6"
              :class="{ block: isMenuOpen, hidden: !isMenuOpen }"
            >
              <!-- off-canvas menu content here -->
              <img
                class="ml-auto"
                src="./assets/icon-close-menu.svg"
                alt="todo icon"
                @click="toggleMenu"
              />
              <div class="mt-6 text-slate-500">
                <div class="flex flex-col gap-4">
                  <div>
                    <button
                      class="flex items-center group"
                      @click="isFeatureOpen = !isFeatureOpen"
                    >
                      <span class="pr-1 flex-1 text-sm">Features</span>
                      <span>
                        <svg
                          class="fill-current h-4 w-4"
                          :class="{
                            'transform rotate-180': isFeatureOpen,
                            'transform rotate-0': !isFeatureOpen,
                          }"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                        >
                          <path
                            d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
                          />
                        </svg>
                      </span>
                    </button>
                    <ul
                      class="bg-white text-slate-500 gap-4 flex flex-col rounded-lg pl-5 mt-5"
                      :class="{ block: isFeatureOpen, hidden: !isFeatureOpen }"
                    >
                      <a
                        href="#"
                        class="w-24 flex items-center rounded-sm hover:text-slate-900"
                        ><img src="./assets/icon-todo.svg" alt="todo icon" />
                        <div class="ml-3 text-sm">Todo List</div>
                      </a>
                      <a
                        href="#"
                        class="flex items-center rounded-sm hover:text-slate-900"
                        ><img src="./assets/icon-calendar.svg" alt="calendar icon" />
                        <div class="ml-3 text-sm">Calendar</div>
                      </a>
                      <a
                        href="#"
                        class="flex items-center rounded-sm hover:text-slate-900"
                        ><img src="./assets/icon-reminders.svg" alt="reminder icon" />
                        <div class="ml-3 text-sm">Reminder</div>
                      </a>
                      <a
                        href="#"
                        class="flex items-center rounded-sm hover:text-slate-900"
                        ><img src="./assets/icon-planning.svg" alt="planning icon" />
                        <div class="ml-3 text-sm">Planning</div>
                      </a>
                    </ul>
                  </div>
                  <div>
                    <button class="flex items-center group" @click="toggleCompany">
                      <span class="pr-1 flex-1 text-sm">Company</span>
                      <span>
                        <svg
                          class="fill-current h-4 w-4"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                          :class="{
                            'transform rotate-180': isCompanyOpen,
                            'transform rotate-0': !isCompanyOpen,
                          }"
                        >
                          <path
                            d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
                          />
                        </svg>
                      </span>
                    </button>
                    <ul
                      class="bg-white text-slate-500 gap-4 flex flex-col pl-5 mt-5"
                      :class="{ block: isCompanyOpen, hidden: !isCompanyOpen }"
                    >
                      <a
                        href="#"
                        class="flex items-center rounded-sm hover:hover:text-slate-900"
                      >
                        <div class="text-sm">History</div>
                      </a>
                      <a
                        href="#"
                        class="flex items-center rounded-sm hover:hover:text-slate-900"
                      >
                        <div class="text-sm">Our Team</div>
                      </a>
                      <a
                        href="#"
                        class="flex items-center rounded-sm hover:hover:text-slate-900"
                      >
                        <div class="text-sm">Blog</div>
                      </a>
                    </ul>
                  </div>
                  <div>
                    <a href="#" class="pr-1 flex-1 text-sm" aria-current="page"
                      >Carrers</a
                    >
                  </div>
                  <div>
                    <a href="#" class="pr-1 flex-1 text-sm" aria-current="page">About</a>
                  </div>
                  <div class="flex flex-col justify-center mt-4 gap-2">
                    <button class="text-sm">Login</button>
                    <button class="text-sm py-2 border border-slate-400 rounded-lg">
                      Register
                    </button>
                  </div>
                </div>
              </div>
            </div>
            <div
              :class="{
                'fixed top-0 left-0 w-full h-full bg-black bg-opacity-50 z-40': isMenuOpen,
                hidden: !isMenuOpen,
              }"
              @click="toggleMenu"
            ></div>
          </div>
        </div>

        <div
          class="w-full md:block md:w-auto md:flex-grow md:flex md:items-center hidden md:block"
        >
          <div href="#" class="flex items-center md:items-center">
            <div
              class="md:pl-14 md:justify-between items-center w-full md:flex md:w-auto md:order-1"
            >
              <ul
                class="flex flex-col mt-4 md:flex-row md:space-x-8 md:mt-0 md:text-xs md:font-medium md:items-center"
              >
                <li>
                  <div class="group inline-block text-slate-500 hover:text-slate-900">
                    <button class="flex items-center">
                      <span class="pr-1 flex-1">Features</span>
                      <span>
                        <svg
                          class="fill-current h-4 w-4 transform group-hover:-rotate-180 transition duration-150 ease-in-out"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                        >
                          <path
                            d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
                          />
                        </svg>
                      </span>
                    </button>
                    <div
                      class="scale-0 z-50 group-hover:scale-100 absolute transform transition duration-150 ease-in-out origin-top -left-16"
                    >
                      <ul
                        class="bg-white text-slate-500 drop-shadow-xl gap-4 flex flex-col rounded-lg px-5 py-4 mt-5"
                      >
                        <a
                          href="#"
                          class="w-24 flex items-center rounded-sm hover:text-slate-900"
                          ><img src="./assets/icon-todo.svg" alt="todo icon" />
                          <div class="ml-3">Todo List</div>
                        </a>
                        <a
                          href="#"
                          class="flex items-center rounded-sm hover:text-slate-900"
                          ><img src="./assets/icon-calendar.svg" alt="calendar icon" />
                          <div class="ml-3">Calendar</div>
                        </a>
                        <a
                          href="#"
                          class="flex items-center rounded-sm hover:text-slate-900"
                          ><img src="./assets/icon-reminders.svg" alt="reminder icon" />
                          <div class="ml-3">Reminder</div>
                        </a>
                        <a
                          href="#"
                          class="flex items-center rounded-sm hover:text-slate-900"
                          ><img src="./assets/icon-planning.svg" alt="planning icon" />
                          <div class="ml-3">Planning</div>
                        </a>
                      </ul>
                    </div>
                  </div>
                </li>
                <li>
                  <div class="group inline-block text-slate-500 hover:text-slate-900">
                    <button class="flex items-center">
                      <span class="pr-1 flex-1">Company</span>
                      <span>
                        <svg
                          class="fill-current h-4 w-4 transform group-hover:-rotate-180 transition duration-150 ease-in-out"
                          xmlns="http://www.w3.org/2000/svg"
                          viewBox="0 0 20 20"
                        >
                          <path
                            d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"
                          />
                        </svg>
                      </span>
                    </button>
                    <div
                      class="scale-0 z-50 group-hover:scale-100 absolute transform transition duration-150 ease-in-out origin-top"
                    >
                      <ul
                        class="bg-white text-slate-500 drop-shadow-xl gap-4 flex flex-col rounded-lg px-5 py-4 mt-5 w-24"
                      >
                        <a
                          href="#"
                          class="flex items-center rounded-sm hover:hover:text-slate-900"
                        >
                          <div class="">History</div>
                        </a>
                        <a
                          href="#"
                          class="flex items-center rounded-sm hover:hover:text-slate-900"
                        >
                          <div class="">Our Team</div>
                        </a>
                        <a
                          href="#"
                          class="flex items-center rounded-sm hover:hover:text-slate-900"
                        >
                          <div class="">Blog</div>
                        </a>
                      </ul>
                    </div>
                  </div>
                </li>
                <li>
                  <a
                    href="#"
                    class="block md:py-2 md:pr-4 md:pl-3 text-slate-500 hover:text-slate-900 rounded md:p-0"
                    aria-current="page"
                    >Carrers</a
                  >
                </li>
                <li>
                  <a
                    href="#"
                    class="block md:py-2 md:pr-4 md:pl-3 text-slate-500 hover:text-slate-900 rounded md:p-0"
                    aria-current="page"
                    >About</a
                  >
                </li>
              </ul>
            </div>
          </div>
          <div class="flex md:flex-row flex-col ml-auto items-center md:order-2 text-xs">
            <div>
              <button
                class="text-slate-500 hover:text-slate-900 pr-4 pl-3 md:mr-6 mb-4 md:mb-0"
              >
                Login
              </button>
            </div>
            <div>
              <button
                class="text-slate-500 hover:text-slate-900 py-2 px-4 rounded-lg border-slate-500 border hover:border-slate-900"
              >
                Register
              </button>
            </div>
          </div>
        </div>
      </div>
    </nav>

    <div class="grid grid-cols-12 gap-4 container mx-auto md:px-10 px-0 relative">
      <div class="col-span-12 md:col-span-7 m-auto order-last md:order-none md:pl-16">
        <div
          class="md:text-7xl text-4xl text-center md:text-left font-bold md:mb-14 md:mt-0 mt-6 mb-4"
        >
          Make <br class="hidden md:block" />
          Remote Work
        </div>
        <div
          class="w-100 text-slate-500 text-lg md:mb-14 mb-4 md:text-left text-center px-2 md:pr-36"
        >
          Get your team in sync, no matter your location. Streamline processes, create
          team rituals, and watch productivity soar.
        </div>
        <div class="flex justify-center md:flex-none md:justify-start mt-6">
          <button
            class="text-white text-sm hover:text-black border hover:border-black hover:bg-transparent py-3 px-4 bg-black font-medium rounded-lg md:mb-14 mb-12"
          >
            Learn More
          </button>
        </div>
        <div class="grid grid-cols-4 gap-2 md:p-0 p-4">
          <div class="m-auto">
            <img src="./assets/client-databiz.svg" alt="" />
          </div>
          <div class="m-auto">
            <img src="./assets/client-audiophile.svg" alt="" />
          </div>
          <div class="m-auto">
            <img src="./assets/client-maker.svg" alt="" />
          </div>
          <div class="m-auto">
            <img src="./assets/client-meet.svg" alt="" />
          </div>
        </div>
      </div>
      <div class="md:col-span-5 col-span-12 md:p-16 p-0">
        <img src="./assets/image-hero-desktop.png" class="md:block hidden" alt="" />
        <img src="./assets/image-hero-mobile.png" class="md:hidden block" />
      </div>
    </div>
  </div>
</template>

<style>
@import "./assets/base.css";
</style>
