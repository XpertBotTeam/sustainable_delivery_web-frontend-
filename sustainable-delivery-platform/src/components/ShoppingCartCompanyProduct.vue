<script setup>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { faMinus, faPlus } from '@fortawesome/free-solid-svg-icons';

//define props variables
import { defineProps,defineEmits  } from 'vue';
const props = defineProps(['product'])

//define emits
const emit = defineEmits(['addToCart','removeFromCart'])
</script>
<template>
    
        <div class="px-5 flex items-center justify-between py-3 border-b border-dashed border-[#7D7777] ">
            <div class="DarkerGrotesque text-[18px]">{{props.product.name}}</div>
            <div class="flex items-center gap-5">
                <button class="text-white bg-[black] text-[12px] rounded-[6px] w-[28px] h-[22px] flex items-center justify-center  DarkerGrotesque" @click="emit('removeFromCart',props.product.id)"><FontAwesomeIcon :icon="faMinus" /></button>
                <div>{{props.product.quantity}}</div>
                <button class="text-white bg-[black] text-[12px] rounded-[6px] w-[28px] h-[22px] flex items-center justify-center   DarkerGrotesque" @click="emit('addToCart',props.product.id)"><FontAwesomeIcon :icon="faPlus"></FontAwesomeIcon></button>
            
            </div>
        </div>
</template>