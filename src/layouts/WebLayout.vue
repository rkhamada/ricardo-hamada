<script setup>
</script>


<script>

import { ref } from 'vue';

export default {
    props: [ 'bgColor' ],
    setup ( )
    { }
}

</script>


<template>
    <body v-bind:class="bgColor">
        <main id="web-container">
            <slot />
        </main>
    </body>
</template>

<style>
@media screen and (min-width: 900px) {
    body {
        background: url(/images/1.jpg);
        background-color: #000;
        background-repeat: no-repeat;
        background-size: cover;
        background-attachment: fixed;
        background-position: center; 
    }
}
@media screen and (max-width: 900px) {
    body {
        background: url(/images/1.jpg);
        background-color: #000;
        background-repeat: no-repeat;
        background-size: cover;
        background-attachment: fixed;
        background-position: center; 
    }
}

</style>