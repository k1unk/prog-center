<template>
    <div class="activation-info">
        <div class="to-activate">
            <div class="text-1">Доступно к активации: {{ order.status.notActivated.length }}</div>
            <div class="text-2">Запросите код и активируйте программу</div>
            <div class="code-button" @click="changeModal(true)">Запросить код</div>
        </div>
        <div class="to-deactivate" v-for="item in order.status.activated">
            <div class="deactivate-item">
                <div class="info">
                    <div class="info-1">
                        <div class="key">Дата активации:</div>
                        <div class="value">{{ item.activationDate }}</div>
                    </div>
                    <div class="info-2">
                        <div class="key">Наименование компьютера:</div>
                        <div class="value">{{ item.pcInfo.name }}</div>
                        <div class="pc-info">
                            <div class="showMore">
                                <img class="showMoreImg" src="@/assets/pc-info.png">
                                <div class="pc-info-notify">
                                    <img src="@/assets/extra-info-2.png">
                                    <div class="text">
                                        <div class="text-1">{{ item.pcInfo.user }}</div>
                                        <div class="text-2">{{ item.pcInfo.core }}</div>
                                        <div class="text-3">{{ item.pcInfo.version }}</div>
                                    </div>
                                </div>
                            </div>

                        </div>
                    </div>
                    <div class="info-3">
                        <div class="key">Комментарий:</div>
                        <div class="value">{{ item.comment }}</div>
                    </div>
                </div>
                <div class="deactivate-button">Деактивировать</div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'OrderActivationInfo',
    props: {
        order: Object,
        showModal: Boolean
    },
    methods: {
        changeModal(value) {
            this.$emit("changeModal", value)
        }
    }
}
</script>

<style scoped>
.activation-info {

}

.to-activate {
    padding: 30px 0 45px 26px;
    background-image: url("@/assets/background.jpg");
    background-size: 100% auto;
}

.to-activate .text-1 {
    margin-bottom: 20px;
    font-weight: 600;
    font-size: 20px;
    line-height: 150%;
    color: #3E3E3E;
}

.to-activate .text-2 {
    margin-bottom: 30px;
    font-size: 14px;
    line-height: 28px;
    color: #000000;
}

.code-button {
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    color: #FFFFFF;
    padding: 12px 35px;
    background-color: #2A5FCB;
    border-radius: 50px;
    display: inline-block;
    cursor: pointer;
}

.deactivate-item {
    width: 100%;
    display: flex;
    justify-content: space-between;
    border-bottom: 1px solid #DEDCDC;;
}

.info {
    margin: 30px 0 45px 24px;
}

.info-1, .info-2, .info-3 {
    display: flex;
    align-items: center;
    margin-bottom: 15px;
}

.key {
    margin-right: 4px;
    color: #A5A5A5;
}

.value {
    color: black;
}

.info-2 .value {
    margin-right: 15px;
}

.pc-info {
    position: relative;
}

.pc-info-notify {
    display: none;
}

.showMore {
    width: 20px;
    height: 20px;
    position: relative;
    cursor: pointer;
}

.showMoreImg {
    width: 20px;
    height: 20px;
}

.showMore:hover > .pc-info-notify {
    display: block;
    position: absolute;
    top: -45px;
    left: 1px;
}

.showMore .text {
    position: absolute;
    top: 45px;
    left: 50px;

}


.pc-info .text-1, .pc-info .text-2, .pc-info, .text-3 {
    font-weight: 500;
    font-size: 12px;
    line-height: 20px;
    color: #A5A5A5;
}

.deactivate-button {
    margin: 88px 26px 45px 0;
    padding: 12px 25px;
    color: #2A5FCB;
    border: 1px solid #2A5FCB;
    border-radius: 50px;
    cursor: pointer;
}

</style>
