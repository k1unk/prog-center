<template>
    <div class="programs">
        <div class="content-title">Мои программы</div>
        <div class="search">
            <img src="@/assets/search.png">
            <input type="text" placeholder="Введите название" v-model="search">
        </div>
        <div class="table">
            <div class="headers">
                <div class="title title-1">Номер заказа</div>
                <div class="title title-2">Программа</div>
                <div class="title title-3">Действует до</div>
                <div class="title title-4">Скачать</div>
                <div class="title title-5">Руководство</div>
                <div class="title title-6">Статус</div>
            </div>
            <div class="orders" v-for="order in ordersToShow">
                <Order :order="order" :showModal="showModal" @changeModal="changeModal"/>
            </div>
            <div
                v-if="ordersSearched.length>countToShow"
                class="load-more"
                @click="loadMore"
            >
                Показать еще
            </div>
            <div v-else style="margin-bottom: 150px"></div>
        </div>

    </div>
</template>

<script>
import Order from "@/components/Order";

export default {
    name: 'Programs',
    components: {Order},
    props: {
        showModal: Boolean
    },
    computed: {
        ordersToShow() {
            return [...this.ordersSearched].slice(0,this.countToShow)
        },
        ordersSearched() {
            return [...this.orders].filter(value => value.title.toLowerCase().includes(this.search.toLowerCase()))
        }
    },
    methods: {
        loadMore() {
            this.countToShow += 2
        },
        changeModal(value) {
            this.$emit("changeModal", value)
        }
    },
    data() {
        return {
            search: "",
            countToShow: 3,
            orders: [
                {
                    id: 112192,
                    title: "(2) Детский сад: Питание",
                    dateTo: "08.09.2022",
                    status: {
                        activated: [
                            {
                                id: 1,
                                activationDate: "2022-09-15 13:54:59",
                                comment: "Хочу перенести программу",
                                pcInfo: {
                                    name: "HOME-PC",
                                    user: "Роман",
                                    core: "Pentium (R) Dual-Core CPU T440 @ 2.20 GHz",
                                    version: "Майкрософт Windows 8.1 Профессиональная"
                                }
                            },
                        ],
                        notActivated: [
                            {id: 1},
                        ]
                    },
                    shouldProlong: true
                },
                {
                    id: 112193,
                    title: "(2) Детский сад: Питание Здоровье",
                    dateTo: "08.09.2022",
                    status: {
                        activated: [
                            {
                                id: 1,
                                activationDate: "2022-09-15 13:54:59",
                                comment: "Хочу перенести программу",
                                pcInfo: {
                                    name: "HOME-PC",
                                    user: "Роман",
                                    core: "Pentium (R) Dual-Core CPU T440 @ 2.20 GHz",
                                    version: "Майкрософт Windows 8.1 Профессиональная"
                                }
                            },

                        ],
                        notActivated: [
                            {id: 1},
                        ]
                    },
                    shouldProlong: false
                },
                {
                    id: 112194,
                    title: "(2) Детский сад: Питание Здесь",
                    dateTo: "08.09.2022",
                    status: {
                        activated: [
                            {
                                id: 1,
                                activationDate: "2022-09-15 13:54:59",
                                comment: "Хочу перенести программу",
                                pcInfo: {
                                    name: "HOME-PC",
                                    user: "Роман",
                                    core: "Pentium (R) Dual-Core CPU T440 @ 2.20 GHz",
                                    version: "Майкрософт Windows 8.1 Профессиональная"
                                }
                            },
                            {
                                id: 2,
                                activationDate: "2022-09-15 13:54:59",
                                comment: "Хочу перенести программу",
                                pcInfo: {
                                    name: "HOME-PC",
                                    user: "Роман",
                                    core: "Pentium (R) Dual-Core CPU T440 @ 2.20 GHz",
                                    version: "Майкрософт Windows 8.1 Профессиональная"
                                }
                            },

                        ],
                        notActivated: [
                            {id: 1},
                            {id: 2}
                        ]
                    },
                    shouldProlong: false
                }, {
                    id: 112195,
                    title: "(2) Детский сад: Питание",
                    dateTo: "08.09.2022",
                    status: {
                        activated: [],
                        notActivated: [
                            {id: 1},
                        ]
                    },
                    shouldProlong: false
                },
                {
                    id: 112196,
                    title: "(2) Детский сад: Питание",
                    dateTo: "08.09.2022",
                    status: {
                        activated: [
                            {
                                id: 1,
                                activationDate: "2022-09-15 13:54:59",
                                comment: "Хочу перенести программу",
                                pcInfo: {
                                    name: "HOME-PC",
                                    user: "Роман",
                                    core: "Pentium (R) Dual-Core CPU T440 @ 2.20 GHz",
                                    version: "Майкрософт Windows 8.1 Профессиональная"
                                }
                            },
                        ],
                        notActivated: [
                            {id: 1},
                        ]
                    },
                    shouldProlong: true
                },
                {
                    id: 112197,
                    title: "(2) Детский сад: Питание",
                    dateTo: "08.09.2022",
                    status: {
                        activated: [
                            {
                                id: 1,
                                activationDate: "2022-09-15 13:54:59",
                                comment: "Хочу перенести программу",
                                pcInfo: {
                                    name: "HOME-PC",
                                    user: "Роман",
                                    core: "Pentium (R) Dual-Core CPU T440 @ 2.20 GHz",
                                    version: "Майкрософт Windows 8.1 Профессиональная"
                                }
                            },
                        ],
                        notActivated: [
                            {id: 1},
                        ]
                    },
                    shouldProlong: false
                },
                {
                    id: 112198,
                    title: "(2) Детский сад: Питание",
                    dateTo: "08.09.2022",
                    status: {
                        activated: [
                            {
                                id: 1,
                                activationDate: "2022-09-15 13:54:59",
                                comment: "Хочу перенести программу",
                                pcInfo: {
                                    name: "HOME-PC",
                                    user: "Роман",
                                    core: "Pentium (R) Dual-Core CPU T440 @ 2.20 GHz",
                                    version: "Майкрософт Windows 8.1 Профессиональная"
                                }
                            },
                        ],
                        notActivated: [
                            {id: 1},
                        ]
                    },
                    shouldProlong: false
                },

            ],

        }
    },
}
</script>

<style scoped>
.programs {
    padding-right: 20px;
}

.content-title {
    margin: 222px 0 30px 0;
    font-weight: 600;
    font-size: 38px;
    line-height: 46px;
    color: #3E3E3E;
}

.search {
    width: 100%;
    position: relative;
    margin-bottom: 75px;
}

.search img {
    position: absolute;
    width: 24px;
    height: 24px;
    top: 18px;
    left: 0px;
    cursor: pointer;

}

.search input {
    width: 100%;
    height: 56px;
    font-size: 24px;
    line-height: 30px;
    padding-left: 32px;
    background-color: #F9FBFE;
    border: 0;
    border-bottom: 1px solid #c4c4c4;
}

.search input::placeholder {
    font-weight: 500;
    font-size: 14px;
    line-height: 17px;
    color: #9E9E9E;
}

.search input:focus {
    outline: none;
    border-bottom: 1px solid black;
}

.table {

}

.headers {
    display: flex;
    margin-bottom: 22px;
}

.headers .title {
    font-weight: 500;
    font-size: 12px;
    line-height: 15px;
    color: #9E9E9E;
    text-align: center;
}

.orders {
    position: relative;
}

.title-1 {
    width: 95px;
}

.title-2 {
    width: 246px;
}
@media screen and (max-width: 1120px){
    .title-2 {
        width: 170px;
    }
}

.title-3 {
    width: 134px;
}

.title-4 {
    width: 89px;
}

.title-5 {
    width: 80px;
}

.title-6 {
    width: 197px;
}
.load-more{
    margin-bottom: 150px;
    font-weight: 500;
    font-size: 14px;
    line-height: 17px;
    color: #A5A5A5;
    text-align: end;
    cursor: pointer;
}
</style>
