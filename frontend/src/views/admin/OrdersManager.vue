<script>
    import OrderService from '@/services/order.service';
    export default {
        data() {
            return {
                orders: [],
            }
        },
        methods: {
            async getData() {
                this.orders = await OrderService.getAll();
                this.orders = this.orders.reverse()
            },
        },
        created() {
            this.getData();
        }
    }
</script>

<template>
    <div>
        <h5 class="fw-bold my-3">Quản lý đặt Tour</h5>  
        <table class="table table-bordered">
            <thead>
                <tr class="table-secondary text-center">
                    <th scope="col">DU KHÁCH</th>
                    <th scope="col">TOUR</th>
                    <th scope="col">SỐ CHỖ</th>
                    <th scope="col">THỜI GIAN ĐẶT</th>
                    <th scope="col">GIÁ TRỊ</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(item, i) in this.orders" :key="item._id">
                    <td class="align-middle col-3">
                        <div class="fw-bold">{{item.name}}</div>
                        <div>E-mail: {{item.email}}</div>
                        <div>Phone: {{item.phone}}</div>
                        <div>Địa chỉ: {{item.address}}</div>
                    </td>
                    <td class="align-middle col-4">
                        <div class="fw-bold prod-name">{{item.tourId.name}}</div>
                        <div>Ngày khởi hành: {{item.tourId.start}}</div>
                        <div>Thời gian: {{item.tourId.day}} ngày {{item.tourId.night}} đêm</div>
                    </td>
                    <td class="align-middle">
                        <div>
                            <span class="fw-semibold me-1"><i class="fa-solid fa-person-walking-luggage me-1"></i>Người lớn:</span>
                            {{item.adult > 0 ? item.adult : 0}}
                        </div>
                        <div>
                            <span class="fw-semibold me-1"><i class="fa-solid fa-baby me-1"></i>Trẻ em:</span>
                            {{item.child > 0 ? item.child : 0}}
                        </div>
                    </td>
                    <td class="text-center align-middle">
                        {{new Date(Date.parse(item.createdAt)).toLocaleString()}}
                    </td>
                    <td class="text-center align-middle">
                        {{new Intl.NumberFormat('vi-VN', {style: 'currency', currency: 'VND'})
                            .format(item.total)
                        }}
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<style>
    .prod-name {
        font-weight: 700;
        line-height: 1.1;
        overflow: hidden;
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
    }
</style>                  