<template>
  <div
    v-for="data in data_slide"
    :class="
      isSlider != data.id
        ? 'hidden'
        : 'flex justify-between px-20 items-center py-1 h-[50vh] border'
    "
  >
    <div class="flex flex-col gap-y-11 w-1/2">
      <div class="space-y-2">
        <p class="text-lg font-semibold text-gray-500">#Big Fashion Sale</p>
        <p class="text-6xl font-bold text-gray-700">
          Limited Time Offer! Up to 50% OFF!
        </p>
        <p class="text-sm text-gray-500 font-semibold">
          Redefine Your Everyday Style
        </p>
      </div>
      <div class="flex gap-x-2">
        <div
          v-for="slide in data_slide"
          :key="slide.id"
          @click="onSlider(slide.id)"
          class="w-4 h-4 cursor-pointer rounded-full flex justify-center items-center border-2 border-gray-500"
        >
          <div
            :class="
              isSlider == slide.id
                ? 'w-2 h-2 bg-gray-400 rounded-full m-auto'
                : 'bg-transparent'
            "
          ></div>
        </div>
      </div>
    </div>
    <div class="w-1/4">
      <img :src="data.img" />
    </div>
  </div>
</template>

<script lang="ts" setup>
import { onMounted, onUnmounted, ref } from "vue";
interface DataType {
  id: number;
  img: string;
}

let isSlider = ref<number>(1);
let timeOut =ref(0);
const data_slide = [
  {
    id: 1,
    img: "https://s3.ap-southeast-1.amazonaws.com/uploads-store/uploads/all/O19sE5ZmMaVdO8O66od1v60QdccGiK7aGgtbQctJ.png",
  },
  {
    id: 2,
    img: "https://png.pngtree.com/png-vector/20241018/ourmid/pngtree-running-shoes-or-sneakers-on-a-transparent-background-png-image_14112954.png",
  },
  {
    id: 3,
    img: "https://dlcdnwebimgs.asus.com/gain/50a8a628-d516-4583-aded-6697c07b3b8c/",
  },
];

function onSlider(id: number) {
  isSlider.value = id;
  clearInterval(timeOut.value);
}

function onStart(){
  timeOut.value = setInterval(()=>{
    isSlider.value += 1;
    if(isSlider.value > data_slide.length){
      isSlider.value =1;
    }
  },3000);
}

function onEnd(){
  clearInterval(timeOut.value);
}

onMounted(onStart);
onUnmounted(onEnd)

</script>

<style></style>
