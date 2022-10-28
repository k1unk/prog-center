<template>
    <div class="prolong-notify" v-show="order.shouldProlong"></div>
    <div class="extra-info-1"><img src="@/assets/extra-info-1.png"></div>
    <div class="item">
        <OrderMainInfo :order="order" @toggleSubItems="toggleSubItems"/>
        <OrderActivationInfo v-show="visible" :order="order" :showModal="showModal" @changeModal="changeModal" visible="visible"/>
    </div>
</template>

<script>
import OrderActivationInfo from "@/components/OrderActivationInfo";
import OrderMainInfo from "@/components/OrderMainInfo";

export default {
    name: 'Order',
    components: {
        OrderActivationInfo, OrderMainInfo
    },
    props: {
        order: Object,
        showModal: Boolean
    },
    data() {
        return {
            visible: false
        }
    },
    methods: {
        toggleSubItems() {
            this.visible = !this.visible
        },
        changeModal(value) {
            this.$emit("changeModal", value)
        }
    }
}
</script>

<style scoped>
.prolong-notify {
    position: absolute;
    width: 12px;
    height: 12px;
    background-color: #FC5426;
    border-radius: 50%;
    top: 0;
    left: 0;
    cursor: pointer;
}

.extra-info-1 {
    position: absolute;
    top: -45px;
    left: -5px;
    display: none;
}

.prolong-notify:hover + .extra-info-1 {
    display: block;
}

.item {
    background-color: white;
    margin-bottom: 15px;
}

</style>
