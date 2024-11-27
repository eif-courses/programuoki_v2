<template>
  <div class="flex w-full">
    <!-- Sidebar with Tree Structure -->
    <div>
      <ul class="menu menu-xs bg-base-200 rounded-lg w-full max-w-xs">
        <li v-for="item in menuItems" :key="item.id">
          <!-- Pass item.children to the CodeTreeStructure for recursive rendering -->
          <CodeTreeStructure :items="item.children" @item-click="handleItemClick" />
        </li>
      </ul>
    </div>

    <div class="divider divider-horizontal">-></div>

    <!-- Content Area -->
    <div class="card bg-base-300 rounded-box grid h-20 flex-grow place-items-center">
      {{ selectedItemContent }}
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import CodeTreeStructure from "~/components/CodeTreeStructure.vue";

const icons = {
  pdf: "M10 2v6a3 3 0 010 6H5a3 3 0 01-3-3V5c0-2 3-3 3-3h4.5a3 3 0 013 3z",
  folder: 'M2.25 12.75V12A2.25 2.25 0 014.5 9.75h15A2.25 2.25 0 0121.75 12v.75m-8.69-6.44l-2.12-2.12a1.5 1.5 0 00-1.061-.44H4.5A2.25 2.25 0 002.25 6v12a2.25 2.25 0 002.25 2.25h15A2.25 2.25 0 0021.75 18V9a2.25 2.25 0 00-2.25-2.25h-5.379a1.5 1.5 0 01-1.06-.44z',
  file: "M12 4C7.589 4 4 7.589 4 12s3.589 8 8 8 8-3.589 8-8-3.589-8-8-8zm0 10c-1.654 0-3-1.346-3-3s1.346-3 3-3 3 1.346 3 3-1.346 3-3 3z",
  image: "M2.25 15.75l5.159-5.159a2.25 2.25 0 013.182 0l5.159 5.159m-1.5-1.5l1.409-1.409a2.25 2.25 0 013.182 0l2.909 2.909m-18 3.75h16.5a1.5 1.5 0 001.5-1.5V6a1.5 1.5 0 00-1.5-1.5H3.75A1.5 1.5 0 002.25 6v12a1.5 1.5 0 001.5 1.5zm10.5-11.25h.008v.008h-.008V8.25zm.375 0a.375.375 0 11-.75.375.375 0 01.75 0z",
  database: "M4 6C4 4.89543 7.58172 4 12 4C16.4183 4 20 4.89543 20 6M4 6C4 7.10457 7.58172 8 12 8C16.4183 8 20 7.10457 20 6M4 6V18C4 19.1046 7.58172 20 12 20C16.4183 20 20 19.1046 20 18V6M4 10C4 11.1046 7.58172 12 12 12C16.4183 12 20 11.1046 20 10M4 14C4 15.1046 7.58172 16 12 16C16.4183 16 20 15.1046 20 14",
};



const menuItems = [
  {
    id: 2,
    name: "programuoki_v2",
    children: [
      { id: 9, name: ".data", icon: icons.folder },
      { id: 10, name: "components", icon: icons.folder },
      { id: 11, name: "layouts", icon: icons.folder },
      { id: 12, name: "pages", icon: icons.folder },
      { id: 13, name: "public", icon: icons.folder },
      {
        id: 14,
        name: "server",
        children: [
          {
            id: 15,
            name: "api",
            children: [{ id: 16, name: "guides.get.ts", icon: icons.pdf }],
          },
        ],
      },
      { id: 17, name: "app.vue", icon: icons.file },
      { id: 18, name: "nuxt.config.ts", icon: icons.file },
      { id: 19, name: "package.json", icon: icons.file },
    ],
  },
];

const selectedItemContent = ref("Click an item to see its content");

function handleItemClick(item) {
  selectedItemContent.value = item.name || "Unknown item";
}
</script>
