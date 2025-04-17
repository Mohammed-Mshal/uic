<script setup>
    import Logo from '../assets/logo.svg'
</script>

<template>
    <div class="navbar">
        <div class="navbar-left">
            <router-link to="/">
                <img :src="Logo" alt="Logo" class="logo">
            </router-link>
        </div>
        <div class="navbar-center">
            <ul>
                <li><router-link to="/">Home</router-link></li>
                <li><router-link to="/about">About</router-link></li>
                <li><router-link to="/contact">Contact</router-link></li>
            </ul>
        </div>
        <div class="navbar-right">
            
        </div>
    </div>
</template>