<template>
    <footer>
        <div class="main footer-content">
            <div class="footer-logo">
                <img :src="footer_logo" :alt="footer_logo_alt">
            </div>

            <p class="footer-info">
                © 2021, Game Tracker Inc. Todos os direitos reservados. Nulla facilisi. Etiam sagittis congue tempor. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Suspendisse eu velit et ante luctus egestas. Aenean sed nisi tellus. Duis non ornare libero. Quisque suscipit maximus nisi, in gravida felis. Cras ornare mauris ac nisi congue, ut condimentum sem tincidunt. Phasellus semper tellus malesuada turpis gravida cursus. Duis nec eleifend nunc, vitae finibus elit. Aliquam eget diam vitae purus suscipit viverra.
            </p>

            <div class="footer-links">
                <ul>
                    <li>
                        <a href="#">Termos de Serviço</a>
                    </li>
                    <li>
                        <a href="#">Política de Privacidade</a>
                    </li>
                    <li>
                        <a href="#">Trabalhe conosco</a>
                    </li>
                    <li>
                        <a href="#">Contato</a>
                    </li>
                </ul>
            </div>
        </div>
    </footer>
</template>

<script>
export default {
    name: "GameFooter",
    data() {
        return {
            footer_logo: '/img/footer-logo.svg',
            footer_logo_alt: 'Footer logo'
        }
    }
}
</script>

<style lang="scss">
@import "@/assets/scss/components/_footer.scss";
</style>