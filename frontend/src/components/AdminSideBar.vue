
<template>
    <div class="text-center py-2">
        <router-link to="/admin">
            <img src="@/assets/images/logo.png">
        </router-link>
    </div>
    <div class="ms-2 nav flex-column">
        <div class="nav-item border-bottom border-white py-2">
            <router-link to="/admin/" class="nav-link text-white fw-semibold">
                <i class="fa-solid fa-umbrella-beach"></i> Quản lý Tour
            </router-link>
        </div>
        <div class="nav-item border-bottom border-white py-2">
            <router-link to="/admin/orders" class="nav-link text-white fw-semibold">
                <i class="fa-solid fa-ticket"></i> Quản lý Đặt Tour
            </router-link>
        </div>
        <div class="nav-item border-bottom border-white py-2">
            <router-link to="/admin/users" class="nav-link text-white fw-semibold">
                <i class="fa-regular fa-user"></i> Quản lý Người Dùng
            </router-link>
        </div>
    </div>
</template>

<style>    
    .nav-link:hover {
        color: var(--main-color) !important;
    }

    .nav-link[aria-current="page"] {
        color: gold !important;
    }
</style>