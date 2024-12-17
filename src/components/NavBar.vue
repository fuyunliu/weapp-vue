<template>
  <Menubar :model="items" class="mx-16 border-none">
    <template #start>
      <IconBrandDisqus />
    </template>

    <template #end>
      <div class="flex items-center gap-2">
        <InputText placeholder="Search" type="text" class="w-32 sm:w-auto" />
        <Avatar
          class="cursor-pointer"
          image="https://primefaces.org/cdn/primevue/images/avatar/amyelsner.png"
          shape="circle"
          @click="toggle"
        />
        <Menu ref="menu" :model="oitems" :popup="true" />
      </div>
    </template>
  </Menubar>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import Menubar from "primevue/menubar";
import Menu from "primevue/menu";
import Avatar from "primevue/avatar";
import InputText from "primevue/inputtext";
import { IconBrandDisqus } from "@tabler/icons-vue";
const items = ref([
  {
    label: "首页",
    icon: "pi pi-home",
  },
  {
    label: "诗歌",
    icon: "pi pi-star",
  },
  {
    label: "Projects",
    icon: "pi pi-search",
    items: [
      {
        label: "Components",
        icon: "pi pi-bolt",
      },
      {
        label: "Blocks",
        icon: "pi pi-server",
      },
      {
        label: "UI Kit",
        icon: "pi pi-pencil",
      },
      {
        label: "Templates",
        icon: "pi pi-palette",
        items: [
          {
            label: "Apollo",
            icon: "pi pi-palette",
          },
          {
            label: "Ultima",
            icon: "pi pi-palette",
          },
        ],
      },
    ],
  },
  {
    label: "Contact",
    icon: "pi pi-envelope",
  },
]);

const menu = ref();
const oitems = ref([
  {
    label: "Options",
    items: [
      {
        label: "Refresh",
        icon: "pi pi-refresh",
      },
      {
        label: "Export",
        icon: "pi pi-upload",
      },
    ],
  },
]);

const toggle = (event: any) => {
  menu.value.toggle(event);
};
</script>
