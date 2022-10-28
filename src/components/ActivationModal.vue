<template>
    <div class="overlay" v-if="showModal">
        <div class="modal" v-if="showModal">
            <img src="@/assets/close-btn.png" @click="changeModal(false)">
            <div class="title">Запрос кода активации</div>
            <div class="text">Введите исходный код, который выдает программа</div>
            <div class="forms">
                <input type="text" class="form"><input type="text" class="form"><input type="text" class="form"><input
                type="text" class="form"><input type="text" class="form"><input type="text" class="form"><input
                type="text" class="form"><input type="text" class="form"><input type="text" class="form"><input
                type="text" class="form"><input type="text" class="form"><input type="text" class="form"><input
                type="text" class="form"><input type="text" class="form"><input type="text" class="form">

            </div>
            <textarea placeholder="Комментарий..." class="comment"></textarea>
            <div class="button">Запросить код</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ActivationModal',
    props: {
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

.overlay {
    position: fixed;
    display: block;
    z-index: 2;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background-color: rgba(0, 0, 0, .5);
}

.modal {
    position: relative;
    top: 120px;
    width: 600px;
    z-index: 3;
    margin: 0 auto;
    padding: 40px 40px 45px 40px;
    background-color: #fff;
    border-radius: 10px;
}

.close {
    position: absolute;
    top: 10px;
    right: 10px;
}

.title {
    font-weight: 600;
    font-size: 24px;
    line-height: 29px;
    color: #3E3E3E;
    margin-bottom: 15px;
}

.text {

    font-weight: 500;
    font-size: 14px;
    line-height: 18px;
    color: rgba(62, 62, 62, 0.5);
    margin-bottom: 30px;

}

.forms {
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
}

.form {
    height: 45px;
    width: 30px;
    border: 1px solid #C4C4C4;
    border-radius: 5px;
}

textarea {
    padding: 11px;
    width: 520px;
    height: 118px;
    resize: none;
    margin-bottom: 30px;
    border: 1px solid #C4C4C4;
}

textarea::placeholder {

    font-weight: 500;
    font-size: 12px;
    line-height: 18px;
    color: rgba(62, 62, 62, 0.5);
}

.button {
    display: inline-block;
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    color: #C4C4C4;

    padding: 12px 35px;
    border: 1px solid #C4C4C4;
    border-radius: 50px;
    cursor: pointer;
}

img {
    position: absolute;
    top:0;
    right: -60px;
    cursor: pointer;
}
</style>
