<script>

export default {
    data() {
        return {
            links: [
                "Careers",
                "News",
                "Terms of Use",
                "Privacy Projects",
                "About",
                "Contact",
            ]
        };
    },

    components: {

    }
}
</script>

<template>
    <footer class="container-centered">
        <section class="footer-top">
            <div class="col">
                <div class="logo">
                    <img src="/images/cropped-Group-39-2x.png" alt="logo image">
                </div>
                <div class="overview">
                    <p>While the lovely valley teems whit vapour around me, and
                        the meridian sun strikes the upper surface of the impenetrable
                        foliage of my trees. While the lovely valley teems with vapour
                        around me.
                    </p>
                </div>
            </div>
            <div class="col">
                <strong class="title">QUICk LINKS</strong>
                <div class="separator">
                    <div class="separator-line line1"></div>
                    <div class="separator-line line2"></div>
                </div>
                <ul>
                    <li v-for="link in links"><a href="#">{{ link }}</a></li>
                </ul>
            </div>
            <div class="col">
                <strong class="title">CONTACT</strong>
                <div class="separator">
                    <div class="separator-line line1"></div>
                    <div class="separator-line line2"></div>
                </div>
                <ul class="contact-list">
                    <li>Patricia C.Amedee 4401 Waldeck Street Grapevine
                        Nashville, TX 76051
                    </li>
                    <li>info@yourdomain.com</li>
                    <li>+99 (0) 101 0000 888</li>
                </ul>
            </div>
            <div class="col">
                <strong class="title">LOCATION ON MAP</strong>
                <div class="separator">
                    <div class="separator-line line1"></div>
                    <div class="separator-line line2"></div>
                </div>
                <div class="map-image">
                    <img src="/images/map.png" alt="Location map">
                </div>
            </div>
        </section>
        <section class="footer-bottom">
            <div class="copyright"> © 2020 PHLOX BUSINESS THEME.</div>

            <div class="social">
                <i class="fa-brands fa-facebook-f"></i>
                <i class="fa-brands fa-twitter"></i>
                <i class="fa-brands fa-pinterest-p"></i>
            </div>
        </section>
    </footer>
</template>

<style lang="scss" scoped>
@use "../scss/variables" as *;

.footer-top {
    display: flex;
    gap: 40px;
    padding: 80px 20px;

    .col {
        width: calc(100% / 4 - (40px / 4 * 3));

        .logo {
            padding-bottom: 10px;

            img {
                width: 80%;
            }
        }

        .overview {
            font-size: 0.9em;
            line-height: 1.3;
            color: $overview-color;
        }

        img {
            width: 100%;
        }

        strong {
            font-family: $font-title;
            font-size: 1.3em;
        }

        .separator {
            margin: 20px 0;
        }

        ul {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .contact-list {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        li {
            font-size: 0.9em;
            color: $overview-color;
        }

        a {
            color: $overview-color;
            text-decoration: none;

            &:hover {
                text-decoration: underline;
            }
        }

    }
}

.footer-bottom {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 40px;
    height: 80px;
    background: linear-gradient(to right, #444444, #202020);
    color: #AAAAAA;

    .copyright {
        font-size: 0.7em;
    }

    .social {
        display: flex;
        gap: 20px;
        font-size: 1em;

        i {
            cursor: pointer;

            &:hover {
                color: gray;
            }
        }
    }
}
</style>