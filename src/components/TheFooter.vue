<template>
    <footer>
        <ul class="footer-content">
            <li class="logo"><a href="#">Genomics+Ai</a></li>
            <li>GenomicsPlusAi ©2024. All rights reserved.</li>
        </ul>
    </footer>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
footer {
    background-color: var(--dark-background);
    color: var(--light-gray);
    text-align: center;
    font-size: 14px;
    border-top: 1px solid var(--dark-gray);
    .footer-content {
        justify-content: space-between;
        align-items: center;
        width: 100%;
        padding: 80px 0;
        display: flex;
        flex-direction: column;
        @media (min-width: 1024px) {
            flex-direction: row;
        }

        & .logo {
            &  a {
                flex-grow: 1;
                display: flex;
                justify-content: flex-start;
                font-size: 40px;
                font-weight: 500;
                color: var(--light-gray);
            }
        }
    }
}

</style>