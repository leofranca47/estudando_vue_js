<template>
    <header class="header">
        <h1>
            <slot name="title" />
        </h1>
        <slot />
    </header>

</template>

<script>
export default {
        
        
    }
</script>

<style>

    .header {
        background-color: #000;
        color: #fff;
    }

</style>