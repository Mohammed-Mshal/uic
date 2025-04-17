<script setup>

    const props=defineProps({
        text: {
            type:String,
            required:false
        },
        icon: {
            type:String,
            required:false
        },
        link: {
            type:String,
            required:false
        }, 
    })
    import { RouterLink } from 'vue-router';
</script>

<template>
        <RouterLink  :to="link"  class="custom-button" :class="`${!text&&'paddingCircle'}`">
            <span v-if="text">{{ text }}</span>
            <div class="container-icon" v-if="icon">
                <img :src="icon" alt="">
            </div>
        </RouterLink> 
</template>

<style lang="scss">
    .custom-button{
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 10px;
        padding: 9px 14px;
        color: $text-white;
        font-size: $text-size-2;
        font-weight: 400;
        text-decoration: none;
        border-radius: 33px;
        background-color: $button-background-1;
        transition: all 0.3s ease;
        &:hover{
            background: $button-background-hover-1;
        }
        &.paddingCircle{
            padding: 10px;
        }
        .container-icon{
            height: 24px;
            width: 24px;
            img{
                height: 100%;
                width: 100%;
                object-fit: contain;
                
            }
        }
    
    }
</style>