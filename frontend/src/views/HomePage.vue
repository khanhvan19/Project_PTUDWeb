<script>

</script>

<template>
    <div class="slider-container position-relative">
        <div id="slider1" class="carousel slide carousel-fade" data-bs-ride="carousel" data-bs-touch="false" data-bs-pause="false">
            <div class="carousel-inner">
                <div class="carousel-item active" data-bs-interval="5000">
                    <img src="@/assets/images/banner/1.jpg" class="d-block w-100">
                </div>
                <div class="carousel-item" data-bs-interval="5000">
                    <img src="@/assets/images/banner/2.jpg" class="d-block w-100">
                </div>
                <div class="carousel-item" data-bs-interval="5000">
                    <img src="@/assets/images/banner/3.jpg" class="d-block w-100">
                </div>
                <div class="carousel-item" data-bs-interval="5000">
                    <img src="@/assets/images/banner/4.jpg" class="d-block w-100">
                </div>
                <div class="carousel-item" data-bs-interval="5000">
                    <img src="@/assets/images/banner/5.jpg" class="d-block w-100">
                </div>
            </div>
            <button class="carousel-control-prev" data-bs-target="#slider1" data-bs-slide="prev"></button>
            <button class="carousel-control-next" data-bs-target="#slider1" data-bs-slide="next"></button>
        </div>
    </div>
    <form class="search-form text-center">
        <img src="@/assets/images/logo.png" class="m-2 w-50"/>
        <div class="input-group input-group-lg p-3 rounded-4">
            <input type="text" class="form-control" placeholder="Tìm tại địa điểm bạn quan tâm...">
            <button class="btn btn-success">Tìm kiếm</button>
        </div>
    </form>
</template>

<style scoped>
    .slider-container img {
        width: 100vw;
        height: 100vh;
    }

    .slider-container::after {
        content: "";
        top: 0;
        width: 100%;
        height: 100%;
        background-image: linear-gradient(#00000059 , #00000099);
        position: absolute;
        z-index: 2;
    }

    .search-form {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 3;
    }

    .search-form .input-group {
        width: 50vw;
        background-color: rgba(255, 255, 255, 0.2);
        backdrop-filter: blur(5px);
    }
</style>
