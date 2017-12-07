<template>
    <div id="app">
        <!-- <x-address @change="selectAddress"></x-address> -->
        <div id="address" v-text="selectedAddress"></div>
        <button @click="showpop">showpop</button>
        <div class="mask" v-show="popstatus">
            <div class="popup">
                <h2>选择地址</h2>
                <x-address @change="selectAddress" @close="closeMask"></x-address>
            </div>
        </div>
    </div>
</template>

<script>
    import xAddress from './components/address.vue'

    export default {
        name: 'app',
        components: {
            xAddress
        },
        data: () => {
            return {
                selectedAddress: '',
                popstatus: false
            }
        },
        methods: {
            selectAddress (address) {
                this.selectedAddress = address
            },
            closeMask () {
                this.popstatus = false
            },
            showpop () {
                this.popstatus = true
            },
            hidepop () {
                this.popstatus = false
            }
        }
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        color: #2c3e50;
    }
    #address {
        margin-top: 15px;
        margin-bottom: 15px;
    }
    .mask {
        position: fixed;
        left: 0;
        top: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(0, 0, 0, 0.6);
    }
    .popup {
        position: absolute;
        left: 0;
        bottom: 0;
        min-width: 200px;
        min-height: 200px;
        background-color: #fff;
        padding: 15px;
        max-width: 100%;
    }
    @media screen and (max-width: 768px) {
        .popup {
            padding: 5px;
            min-width: 100%;
            min-height: 200px;
        }
    }
    .popup h2 {
        margin: 0;
        margin-bottom: 8px; 
        font-size: 16px;
        line-height: 24px;
        border-bottom: solid 1px #ddd;
    }
    .popup .btns {
        margin-top: 50px;
        display: -webkit-flex;
        display: -ms-flex;
        display: flex;
        justify-content: space-around;
    }
    button {
        border: 0;
        outline: none;
        padding: 8px 10px;
        border-radius: 5px;
        background-color: #ff9967;
        color: #fff;
    }
    /*覆盖样式*/
    .stf-select {
        display: inline-block;
        min-width: 120px;
        text-align: left;
        padding-left: 10px;
    }
    .stf-select,
    .stf-select__inner-wrapper {
        background-color: #ff9967;
        color: #fff;
    }
</style>
