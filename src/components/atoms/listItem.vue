<script setup>
</script>

<template>
    <li>
        <slot class="orderedBullet" name="bullet"></slot>
        <slot class="content"></slot>
    </li>
</template>

<style>
    li {
        margin-left: 0;
        margin-bottom: 8px;
        line-height: 23px;
    }
    .content {
        margin-left: 16px;
    }
</style>
