<template>
  <Disclosure as="nav" class="bg-gray-800 sticky top-0 z-50" v-slot="{ open }">
    <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8">
      <div class="relative flex h-16 items-center justify-between">
        <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
          <!-- Mobile menu button-->
          <DisclosureButton class="relative inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
            <span class="absolute -inset-0.5" />
            <span class="sr-only">Open main menu</span>
            <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
            <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
          </DisclosureButton>
        </div>
        <div class="flex flex-1 items-center justify-end sm:items-stretch">
          <div class="hidden sm:block">
            <div class="flex space-x-20">
              <a 
                v-for="item in navigation" 
                :key="item.name" 
                :href="item.href"
                @click.prevent="handleClick(item)"
                :class="
                  [
                    item.current ? 'text-white scale-125 text-shadow-[0_4px_8px_#d1d5db]' : 
                    'text-gray-300 hover:text-white hover:scale-125 transition duration-300 ease-in-out hover:text-shadow-[0_4px_8px_#d1d5db]', 'rounded-md px-3 py-2 text-sm font-medium'
                  ]
                " 
                :aria-current="
                  item.current ? 'page' : 
                  undefined
                "
                >{{ item.name }}</a>
            </div>
          </div>
        </div>
      </div>
    </div>

    <DisclosurePanel class="sm:hidden">
      <div class="space-y-1 px-2 pb-3 pt-2">
        <DisclosureButton v-for="item in navigation" :key="item.name" as="a" :href="item.href" :class="[item.current ? 'bg-gray-900 text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white', 'block rounded-md px-3 py-2 text-base font-medium']" :aria-current="item.current ? 'page' : undefined">{{ item.name }}</DisclosureButton>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>

<script setup>
import { ref } from 'vue';
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline'

const navigation = ref([
  { name: 'About', href: '#about', current: false },
  { name: 'Projects', href: '#projects', current: false },
  { name: 'Contact', href: '#contact', current: false },
]);

function handleClick(item) {
  navigation.value.forEach(navItem => navItem.current = false);

  item.current = true;

  scrollToSection(item.href);
}

function scrollToSection(target) {
  const element = document.querySelector(target);
    if (element) {
      element.scrollIntoView({ behavior: 'smooth' });
    }
}
</script>