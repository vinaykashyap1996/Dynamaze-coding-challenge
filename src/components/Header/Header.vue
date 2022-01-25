<template>
    <div class="header-container">
        <img
            class="header-logo"
            :src="logo"
            alt="logo"       
        >
        <hr class="header-line">
    </div>
</template>

<script>
import logo from '../../assets/dynamaze_logo.png';
import "./Header.css";

export default {
    name:"Header",
    data:function() {
        return {
            logo: logo,
        };
    },
};
</script>
