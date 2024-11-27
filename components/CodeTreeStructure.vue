<template>
  <ul>
    <li v-for="item in items" :key="item.id">
      <details v-if="item.children" open>
        <summary
            class="flex items-center space-x-2 cursor-pointer"
            @click.prevent="onItemClick(item)"
        >
          <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="h-4 w-4"
          >
            <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M2.25 12.75V12A2.25 2.25 0 014.5 9.75h15A2.25 2.25 0 0121.75 12v.75m-8.69-6.44l-2.12-2.12a1.5 1.5 0 00-1.061-.44H4.5A2.25 2.25 0 002.25 6v12a2.25 2.25 0 002.25 2.25h15A2.25 2.25 0 0021.75 18V9a2.25 2.25 0 00-2.25-2.25h-5.379a1.5 1.5 0 01-1.06-.44z"
            />
          </svg>
          <span>{{ item.name }}</span>
        </summary>

        <CodeTreeStructure :items="item.children" @item-click="emit('item-click', $event)" />
      </details>

      <!-- File (no children) -->
      <div
          v-else
          class="flex items-center space-x-2 cursor-pointer"
          @click.prevent="onItemClick(item)"
      >
        <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="h-4 w-4"
        >
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="h-4 w-4">
            <path stroke-linecap="round" stroke-linejoin="round" :d="item.icon" />
          </svg>

        </svg>
        <span>{{ item.name }}</span>
      </div>
    </li>
  </ul>
</template>

<script setup>

defineProps({
  items: {
    type: Array,
    required: true,
  },
});


const emit = defineEmits(['item-click']);  // Define the 'item-click' event

// This method will emit the event back to the parent component
const onItemClick = (item) => {
  emit('item-click', item);  // Emit the selected item to the parent component
};

</script>
