<template>
    <div class="info">
        <ul class="info-block-list">
            <li class="info-block">
                <div class="info-block__content">
                    <h2>Our Mission</h2>
                    <p>🧬 End-to-end automatic scientific discovery for cellular biology</p>
                </div>
            </li>
            <li class="info-block">
                <div class="info-block__content">
                    <h2>Key Applications</h2>
                    <ul class="key-list">
                        <li><p>🎯 Target identification for drug discovery</p></li>
                        <li><p>🩺 Early diagnostics & prognostics</p></li>
                        <li><p>💊 Precision medicine</p></li>
                    </ul>
                </div>
            </li>
            <li class="info-block">
                <div class="info-block__content">
                    <h2>Our Team</h2>
                    <p>🔬 Industry-academic hybrid team with strong network in AI and Biotech</p>
                </div>
            </li>
        </ul>
        <a href="#" class="cta-button">Contact Us</a>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped lang="scss">
.info {
    display: flex;
    gap: 40px;
    flex-direction: column;
    & .info-block-list {
        display: grid;
        gap: 20px;
        @media (min-width: 1024px) {
            grid-template-columns: 1fr 1fr 1fr;
            grid-template-rows: 1fr;
        }

        & .info-block {
            color: var(--light-text);
            background-color: var(--dark-gray);
            padding: 20px;
            border-radius: 10px;
            border: 1px solid rgba(255, 255, 255, 0.1);

            &__content {
                display: flex;
                flex-direction: column;
                gap: 10px;
                justify-content: center;

                @media (min-width: 1024px) {
                    align-items: center;
                }

                h2 {
                    font-size: 20px;
                    font-weight: 700;

                    @media (min-width: 1024px) {
                        font-size: 32px;
                        font-weight: 700;
                    }
                }
                p {
                    font-size: 14px;
                    @media (min-width: 1024px) {
                        font-size: 16px;
                    }
                }
            }
        }
    }

    & .cta-button {
        background: linear-gradient(to right,#ffc75f, #da7df0 ,#00d5e6 51%, #f9f871);
        background-clip: text;
        -webkit-text-fill-color: transparent;
        background-size: 200% 200%;
        color:var(--light-text);
        transition: color .2s ease-in-out;
        font-weight: 700;
        text-align: center;
        border-radius: 8px;
        border:  1px solid var(--light-text);
        width: 200px;
        align-self: center;
        font-size: 16px;
        padding: 5px 10px;
        transition: background 0.3s;
        animation: rainbow 2s ease-in-out infinite;

        &:hover {
            background: linear-gradient(to right, #f9f871,#00d5e6 51%,#da7df0, #ffc75f);
            background-clip: text;
            color: var(--dark-gray);
        }

        @media (min-width: 1024px) {
            font-size: 20px;
            padding: 10px 20px;
        }
    }
}

</style>