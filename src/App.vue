<template>
    <ActivationModal @changeModal="changeModal" :showModal="showModal"/>
    <div class="wrapper">
        <Menu/>
        <Programs @changeModal="changeModal" :showModal="showModal"/>
    </div>
</template>

<script>
import Menu from "@/components/Menu";
import Programs from "@/components/Programs";
import ActivationModal from "@/components/ActivationModal";

export default {
    name: 'App',
    components: {
        ActivationModal,
        Programs,
        Menu,
    },
    data() {
        return {
            showModal: false
        }
    },
    methods: {
        changeModal(value) {
            this.showModal = value
        }
    }
}
</script>

<style>

@font-face {
    font-family: "Montserrat";
    src: url("@/assets/fonts/Montserrat.ttf") format("truetype");
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: "Montserrat", sans-serif;
}

body {
    background-color: #F9FBFE;
    min-height: 100vh;
}

#app {
    min-height: 100vh;
}

.wrapper {
    max-width: 1180px;
    margin: auto;
    display: flex;
    position: relative;
}

</style>
