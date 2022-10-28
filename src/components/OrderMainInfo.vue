<template>
    <div class="main">
        <div class="item-text item-text-1">{{ order.id }}</div>
        <div class="item-text item-text-2">{{ order.title }}</div>
        <div class="item-text item-text-3 item-text-3-should" v-if="order.shouldProlong">{{ order.dateTo }}</div>
        <div class="item-text item-text-3" v-else>{{ order.dateTo }}</div>
        <div class="item-text item-text-4">
            <img src="@/assets/download.png" alt="">
        </div>
        <div class="item-text item-text-5">
            <img src="@/assets/file.png" alt="">
        </div>
        <div class="item-text item-text-6" @click="toggleSubItems">
            <div v-show="order.status.activated.length" class="activated">Активировано ({{ order.status.activated.length }})</div>
            <div v-show="order.status.notActivated.length" class="not-activated">Не активировано ({{ order.status.notActivated.length }})</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'OrderMainInfo',
    props: {
        order: Object
    },
    methods: {
        toggleSubItems() {
            this.$emit('toggleSubItems')
        }
    }
}
</script>

<style scoped>


.main {
    display: flex;
    background-color: white;
    margin-bottom: 15px;
}

.item-text {
    border-right: 1px solid #eeeeee;
    text-align: center;
    height: 89px;
    display: flex;
    align-items: center;
    justify-content: center;
}

.item-text-1 {
    width: 95px;
}

.item-text-2 {
    width: 246px;
}

@media screen and (max-width: 1120px){
    .item-text-2 {
        width: 170px;
    }
}
.item-text-3 {
    width: 134px;
}

.item-text-4 {
    width: 89px;
}

.item-text-5 {
    width: 80px;
}

.item-text-6 {
    width: 197px;
}

.item-text-3-should {
    color: #FC5426;
}

.item-text-4 img, .item-text-5 img {
    cursor: pointer;
}

.item-text-6 {
    display: flex;
    flex-direction: column;
    cursor: pointer;
}

.item-text-6 .activated {
    color: #27AE60;
}

.item-text-6 .not-activated {
    color: rgba(196, 196, 196, 1);
}
</style>
