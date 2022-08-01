<template>
    <div class="bg-white w-[65%] lg:w-[15%] p-3 flex flex-col justify-center text-center rounded-xl space-y-4">
        <div class="relative bg-light-blue w-full h-52 rounded-xl overflow-hidden">
            <div class="absolute -top-24 -left-16 bg-lighter-blue bg-opacity-50 w-52 h-52 rounded-full"></div>
            <QRCodeVue :value="qrCode" :size="qrSize" render-as="svg" class="svg-fill z-50" />
            <div class="absolute -bottom-36 -right-24 bg-lighter-blue bg-opacity-50 w-52 h-52 rounded-full"></div>
        </div>

        <div class="space-y-2 pb-4">
            <h1 class="font-bold text-lg text-dark-blue">Improve your front-end skills by building projects</h1>
            <p class="text-sm text-grayish-blue">Scan the QR code to visit Frontend Mentor and take your coding skills to the next level</p>
        </div>
    </div>
</template>

<script lang="ts">
    import QRCodeVue from 'qrcode.vue'

    export default {
        components: {
            QRCodeVue
        },

        props: {
            qrCode: String
        },

        data() {
            return {
                qrSize: '120'
            }
        }
    }
</script>

<style>
    .svg-fill {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }

    .svg-fill > path:first-child {
        fill: transparent;
    }

    .svg-fill > path:last-child {
        fill: #fff;
    }
</style>