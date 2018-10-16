<template>
    <div class="sector"></div>
</template>

<script>
    export default {
        name: "Sector-graph"
    }
</script>

<style scoped>
    .sector{
        width: 240px;
        height: 240px;
        border-radius: 50%;
        background: yellowgreen linear-gradient(to right, transparent 50%, currentColor 0);
        color: #655;
    }

    .sector:before{
        content: '';
        display: block;
        margin-left: 50%;
        height: 100%;
        border-radius: 0 100% 100% 0/50%;
        background-color: inherit;
        transform-origin: left;
        animation: spin 3s linear infinite, bg 6s step-end infinite;
    }

    @keyframes spin {
        to {transform: rotate(.5turn);}
    }

    @keyframes bg {
        50% {background: currentColor;}
    }
</style>
