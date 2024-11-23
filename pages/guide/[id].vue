<template>
  <div class="flex w-full">
    <div>
      <ul class="menu menu-xs bg-base-200 rounded-lg w-full max-w-xs">
        <CodeTreeStructure :items="menuItems" />
      </ul>
    </div>

    <div class="divider divider-horizontal">-></div>
    <div class="card bg-base-300 rounded-box grid h-20 flex-grow place-items-center">content</div>


  </div>
</template>


<script setup>


const pdfIcon = 'M19.5 14.25v-2.625a3.375 3.375 0 00-3.375-3.375h-1.5A1.125 1.125 0 0113.5 7.125v-1.5a3.375 3.375 0 00-3.375-3.375H8.25m0 12.75h7.5m-7.5 3H12M10.5 2.25H5.625c-.621 0-1.125.504-1.125 1.125v17.25c0 .621.504 1.125 1.125 1.125h12.75c.621 0 1.125-.504 1.125-1.125V11.25a9 9 0 00-9-9z'
const folderIcon = 'M2.25 12.75V12A2.25 2.25 0 014.5 9.75h15A2.25 2.25 0 0121.75 12v.75m-8.69-6.44l-2.12-2.12a1.5 1.5 0 00-1.061-.44H4.5A2.25 2.25 0 002.25 6v12a2.25 2.25 0 002.25 2.25h15A2.25 2.25 0 0021.75 18V9a2.25 2.25 0 00-2.25-2.25h-5.379a1.5 1.5 0 01-1.06-.44z'
const fileIcon = "M19.5 14.25v-2.625a3.375 3.375 0 00-3.375-3.375h-1.5A1.125 1.125 0 0113.5 7.125v-1.5a3.375 3.375 0 00-3.375-3.375H8.25m2.25 0H5.625c-.621 0-1.125.504-1.125 1.125v17.25c0 .621.504 1.125 1.125 1.125h12.75c.621 0 1.125-.504 1.125-1.125V11.25a9 9 0 00-9-9z"
const imageIcon = "M2.25 15.75l5.159-5.159a2.25 2.25 0 013.182 0l5.159 5.159m-1.5-1.5l1.409-1.409a2.25 2.25 0 013.182 0l2.909 2.909m-18 3.75h16.5a1.5 1.5 0 001.5-1.5V6a1.5 1.5 0 00-1.5-1.5H3.75A1.5 1.5 0 002.25 6v12a1.5 1.5 0 001.5 1.5zm10.5-11.25h.008v.008h-.008V8.25zm.375 0a.375.375 0 11-.75 0 .375.375 0 01.75 0z"

const databaseIconPath =
    "M4 6C4 4.89543 7.58172 4 12 4C16.4183 4 20 4.89543 20 6M4 6C4 7.10457 7.58172 8 12 8C16.4183 8 20 7.10457 20 6M4 6V18C4 19.1046 7.58172 20 12 20C16.4183 20 20 19.1046 20 18V6M4 10C4 11.1046 7.58172 12 12 12C16.4183 12 20 11.1046 20 10M4 14C4 15.1046 7.58172 16 12 16C16.4183 16 20 15.1046 20 14";



const menuItems = [
  // {
  //   id: 1,
  //   name: "resume.pdf",
  //   icon: pdfIcon, // Specific file icon for PDF
  //   children: null,
  // },
  {
    id: 2,
    name: "programuoki_v2",
    children: [
      {
        id: 9,
        name: ".data",
        icon: folderIcon, // Icon for PSD file
      },
      {
        id: 10,
        name: "components",
        icon: folderIcon, // Icon for PSD file
      },
      {
        id: 11,
        name: "layouts",
        icon: folderIcon, // Icon for PSD file
      },
      {
        id: 12,
        name: "pages",
        icon: folderIcon, // Icon for PSD file
      },
      {
        id: 13,
        name: "public",
        icon: folderIcon, // Icon for PSD file
      },
      {
        id: 14,
        name: "server",
        children: [
          {
            id: 14,
            name: "api",
            children: [
              {
                id: 15,
                name: "guides.get.ts",
                icon: fileIcon, // Icon for image file
              },
            ],
          },
        ],
      },
      {
        id: 16,
        name: "app.vue",
        icon: fileIcon, // Icon for PSD file
      },
      {
        id: 17,
        name: "nuxt.config.ts",
        icon: fileIcon, // Icon for PSD file
      },
      {
        id: 18,
        name: "package.json",
        icon: fileIcon, // Icon for PSD file
      },
    ],
  },
];

</script>