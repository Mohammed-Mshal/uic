<script setup>
    import CustomButton from '@/Elements/CustomButton.vue';
    import Logo from '../assets/images/logo.svg'
    import profileIcon from "@images/profile-circle.svg"
    import search from "@images/search-md.svg"    
import NotificationButton from '@/Elements/NotificationButton.vue';
</script>

<template>
    <div class="navbar section">
        <div class="container">
            <div class="navbar-left">
                <router-link to="/">
                    <img :src="Logo" alt="Logo" class="logo">
                </router-link>
            </div>
            <div class="navbar-center">
                <ul>
                    <li><router-link to="/">Home</router-link></li>
                    <li><router-link to="/dashboard">Dashboard</router-link></li>
                    <li><router-link to="/upcomingtraining">Upcoming Training Calendar</router-link></li>
                </ul>
            </div>
            <div class="navbar-right">
                <CustomButton link="#" text="Soha Elrayes" :icon="profileIcon"/>
                <CustomButton link="#"  :icon="search"/>
                <NotificationButton/>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    
    .navbar {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        background: $text-blue-1;
        z-index: 40;
        .container{
            display: flex; 
            justify-content: space-between;
            align-items: center;
            padding-block: 31px;
            .navbar-left {
                display: flex;
                align-items: center;
                .logo {
                    height: 100px;
                }
            }
            .navbar-center{
                position: relative;
                flex: 1;
                text-align: center;
                z-index: 40;
                gap: 12px;
                ul{
                    display: flex;
                    justify-content: space-evenly;
                    list-style: none;
                    li{
                        a{
                            
                            font-weight: 400;
                            font-size: clamp(15px,2vw,17px);
                            text-align: center;
                            vertical-align: middle;
                            text-decoration: none;
                            color: #fff;
                            padding: 10px 20px;
                            transition: all 0.3s ease;
                            &:hover{
                                color: $text-blue-1;
                            }
                        }
                    }
                }
            }
            .navbar-right {
                display: flex;
                align-items: center;
                gap: 12px;
            }
        }    
    }
</style>