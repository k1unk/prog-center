<template>
    <div class="menu">
        <div :class="getClass(1)" @click="changeActiveItem(1)">
            <p>Дашборд</p>
            <img src="@/assets/arrow-right.png" alt="">
        </div>
        <div :class="getClass(2)" @click="changeActiveItem(2)">
            <p>Мои заказы</p>
            <img src="@/assets/arrow-right.png" alt="">
        </div>
        <div :class="getClass(3)" @click="changeActiveItem(3)">
            <p>Мои программы</p>
            <img src="@/assets/arrow-right.png" alt="">
        </div>
        <div :class="getClass(4)" @click="changeActiveItem(4)">
            <p>Учебный центр</p>
            <img src="@/assets/arrow-right.png" alt="">
        </div>
        <div :class="getClass(5)" @click="changeActiveItem(5)">
            <p>Запрос токена</p>
            <img src="@/assets/arrow-right.png" alt="">
        </div>
        <div :class="getClass(6)" @click="changeActiveItem(6)">
            <p>Техподдержка</p>
            <img src="@/assets/arrow-right.png" alt="">
        </div>
    </div>

</template>

<script>
export default {
    name: 'Menu',
    data() {
        return {
            activeItem: 3
        }
    },
    methods: {
        getClass(value) {
            return value === this.activeItem ? "item item-selected" : "item"
        },
        changeActiveItem(value) {
            this.activeItem = value
        }
    }
}
</script>

<style scoped>
.menu {
    margin: 293px 62px 150px 20px;
    width: 250px;
    max-width: 250px;
    min-width: 160px;
    position: sticky;
    top: 0;
}
@media screen and (max-width: 1120px){
    .menu{
        margin-right: 20px;
    }
}

.item {
    padding: 20px 0;
    border-bottom: 1px solid rgba(42, 95, 203, 0.15);
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
}

.item p {
    font-size: 16px;
    line-height: 32px;
    color: rgba(62, 62, 62, 0.7);
}

.item img {
    width: 15px;
    height: 19px;
    display: none;
}

.item-selected p {
    color: #2A5FCB;
}

.item-selected img {
    display: block;
}
</style>
