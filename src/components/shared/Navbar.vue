<template>
  <div>
    <div
      class="shadow-xs flex justify-between px-2 items-centers items-center"
    >
      <div class="font-bold text-sm text-gray-500"> Welcome to Play Store Ecommerce</div>
      <div class="flex items-center gap-x-1">
        <Button
          size="sm"
          variant="ghost"
          class="rounded-none cursor-pointer text-xs uppercase font-bold text-gray-500"
          >About Store</Button
        >
        <Button
          size="sm"
          variant="ghost"
          class="rounded-none cursor-pointer text-xs uppercase font-bold text-gray-500"
          >SignUp</Button
        >
        <hr class="border h-5" />
        <Button
          size="sm"
          variant="ghost"
          class="rounded-none cursor-pointer text-xs uppercase font-bold text-gray-500"
          >Login</Button
        >
      </div>
    </div>
    <div
      class="h-[8vh] shadow-xs items-center flex justify-between px-2 w-full"
    >
      <p class="text-gray-500 font-extrabold uppercase flex items-center text-sm gap-x-1"><Archive :size="18"/>PlayStore Web</p>
      <div class="flex items-center w-1/2">
        <Select>
          <SelectTrigger size="sm" class="rounded-sm rounded-r-none cursor-pointer min-w-48 focus-visible:ring-0">
            <SelectValue placeholder="Select Filter" class="placeholder:text-gray-400"/>
          </SelectTrigger>
          <SelectContent class="rounded-xs">
            <SelectItem value="toys" class="text-xs">Toys</SelectItem>
          </SelectContent>
        </Select>
        <div class="flex items-center border border-gray-200 shadow-xs w-full rounded-r-sm">
          <Search :size="14" class="w-7 text-gray-400"/>
          <Input type="text" placeholder="Search" class="rounded-none shadow-none placeholder:text-gray-400 border-0 h-7.5 ring-0 focus-visible:ring-0 pl-0 focus-visible:border-gray-500"/>
        </div>
      </div>
      <div>
        <Button size="icon-sm" variant="ghost" class="cursor-pointer text-gray-500">
          <ShoppingBagIcon/>
        </Button>
        <Button size="icon-sm" variant="ghost" class="cursor-pointer text-gray-500">
          <Bell/>
        </Button>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import Button from "../ui/button/Button.vue";
import { Archive, ShoppingBagIcon,Bell,Search } from "lucide-vue-next";
import Select from "../ui/select/Select.vue";
import SelectTrigger from "../ui/select/SelectTrigger.vue";
import SelectValue from "../ui/select/SelectValue.vue";
import SelectContent from "../ui/select/SelectContent.vue";
import Input from "../ui/input/Input.vue";
import SelectItem from "../ui/select/SelectItem.vue";
</script>

<style></style>
