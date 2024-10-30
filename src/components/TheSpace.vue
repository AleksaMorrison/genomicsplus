<template>
    <div class="space">
        <slot></slot>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
.space {
    padding: 0 16px;
    margin:32px 0;
    @media (min-width: 1024px) {
        padding: 0 130px;
        margin: 80px 0;
    }
}
</style>