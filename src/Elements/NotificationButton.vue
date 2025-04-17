<script setup>
import { ref } from 'vue'
import icon from '@images/notification.svg'
const notificationList = ref([])
const notificationCount = ref(1)
const notificationButton = ref(null)
const listStatus = ref(false)
const toggleNotification = () => {
    listStatus.value = !listStatus.value
}
const outClickable = document.addEventListener('click', (e) => {
    if (notificationButton.value && !notificationButton.value.contains(e.target)) {
        listStatus.value = false
        document.removeEventListener('click', outClickable)
    }
})
</script>
<template>
    <div class="notification" ref="notificationButton">
        <div class="notification-button" @click="toggleNotification">
            <div class="notification-icon">
                <img :src="icon" alt="Notification" />
            </div>
            <div class="notification-count" v-if="notificationCount > 0">
                {{ notificationCount }}
            </div>
        </div>
        <div class="notification-list" :class="`${listStatus && 'show'}`">
            <div class="header-list">
                <h4 class="title">Notifications</h4>
                <router-link to="/notification"> View All </router-link>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.notification {
    position: relative;

    .notification-button {
        position: relative;
        cursor: pointer;

        .notification-icon {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 10px;
            color: $text-white;
            font-size: $text-size-2;
            font-weight: 400;
            text-decoration: none;
            border-radius: 33px;
            background-color: $button-background-1;
            transition: all 0.3s ease;

            &:hover {
                background: $button-background-hover-1;
            }

            img {
                height: 100%;
                width: 100%;
                object-fit: contain;
            }
        }

        .notification-count {
            position: absolute;
            top: -5px;
            right: -5px;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 20px;
            width: 20px;
            padding: 4px;
            color: $text-blue-1;
            font-size: $text-size-xsmall;
            font-weight: 700;
            text-decoration: none;
            border-radius: 50%;
            background-color: #fff;
        }
    }

    .notification-list {
        position: absolute;
        top: 100%;
        right: 0;
        z-index: 1;
        max-width: 100vw;
        width: 800px;
        background-color: #fff;
        border: 1px solid #ccc;
        border-radius: 17px;
        padding: 30px 60px;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        transition: 0.5s all ease-in-out;
        opacity: 0;
        pointer-events: none;
        transform: translateY(-10px);

        &.show {
            pointer-events: all;
            opacity: 1;
            transform: translateY(0);
        }

        .header-list {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 8px;

            .title {
                color: $text-blue-3;
                font-weight: 800;
                font-size: $text-size-2;
            }

            a {
                text-decoration: none;
                color: $text-black;
                font-size: $text-size-small;
                font-weight: 700;
            }
        }
    }
}
</style>