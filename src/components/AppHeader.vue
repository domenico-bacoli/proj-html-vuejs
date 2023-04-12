<script>
export default {
    data() {
        return {
            navLinks: [
                "home",
                "about",
                "services",
                "showcase",
                "blog",
                "contact",
            ],
            activeNavLinksIndex: 0,
        };
    },

    methods: {
        activeNavLinks(index) {
            this.activeNavLinksIndex = index;
        }
    },
}
</script>

<template>
    <header class="container-centered">
        <div class="contact-section">
            <div class="number">
                <div class="fax">(001)88451234</div>
                <div class="telephone">88455438</div>
            </div>
            <div class="social">
                <i class="fa-brands fa-facebook-f"></i>
                <i class="fa-brands fa-twitter"></i>
                <i class="fa-brands fa-pinterest-p"></i>
            </div>
        </div>
        <nav>
            <div class="nav-logo">
                <img src="/images/cropped-Group-39-2x.png" alt="logo image">
            </div>
            <div class="nav-link">
                <ul>
                    <li v-for="(link, index) in navLinks" :class="activeNavLinksIndex == index ? 'active' : ''"
                        @click="activeNavLinks(index)">{{ link }}</li>
                </ul>
            </div>
            <div class="nav-button">
                <div class="purchase-button">
                    <button class="btn btn-primary">PURCHASE</button>
                </div>
                <div class="search-icon">
                    <i class="fa-solid fa-magnifying-glass"></i>
                </div>
            </div>
        </nav>

        <section class="jumbo">
            <div class="jumbo-description">
                <div class="experience">17 years of experience</div>
                <div class="title">
                    <h1>We Are a<br>Web Design <span>Agency</span></h1>
                </div>
                <div class="separator">
                    <div class="separator-line line1"></div>
                    <div class="separator-line line2"></div>
                </div>
                <div class="overview">
                    <p>Far far away, behind the word mountains, far from the countries
                        Vokalia and Consonantia, there live the blind texts. Separated
                        they live in Bookmarksgrove right at the coast of the Semantics,
                        a large language ocean.Separated they live in Bookmarksgrove</p>
                </div>
                <div class="button">
                    <button class="btn btn-secondary">READ MORE</button>
                </div>
                <div class="slide-show">
                    <div class="social-list">
                        <ul>
                            <li>FACEBOOK</li>
                            <li> - INSTAGRAM</li>
                            <li> - YOUTUBE</li>
                            <li> - TWITTER</li>
                        </ul>
                    </div>
                    <div class="jumbo-slider">
                        <div class="slide-1"> 01</div>
                        <div class="slide-2">02</div>
                        <div class="slide-3">03</div>

                    </div>
                </div>


            </div>
        </section>
    </header>
</template>

<style lang="scss" scoped>
header {
    margin-bottom: 160px;

    .contact-section {
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 30px;
        padding: 0 44px;
        background-color: #3D3D3D;
        color: white;
        font-weight: bold;

        .number {
            display: flex;
            gap: 12px;
            font-size: 0.7em;
        }

        .social {
            display: flex;
            gap: 20px;
            font-size: 0.9em;
        }
    }

    nav {
        height: 100px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 20px;

        .nav-logo img {
            width: 80%;
        }

        .nav-link ul {
            display: flex;
            gap: 22px;
            text-transform: uppercase;
            font-size: 0.8em;

            li {
                cursor: pointer;
                color: #555555;

                &.active {
                    color: #00D9A6;
                }
            }
        }

        .nav-button {
            display: flex;
            align-items: center;
            gap: 30px;

            i {
                color: #00D9A6;
            }
        }
    }

    .jumbo {
        background-color: #F9F9F9;
        height: 700px;
        background-image: url("/images/Group-36-2x.png");
        background-repeat: no-repeat;
        background-position: 160% 50%;
        background-size: 75%;

        .jumbo-description {
            display: flex;
            flex-direction: column;
            height: 100%;
            width: 50%;
            padding-top: 110px;
            padding-left: 50px;

            .experience {
                color: #00D9A6;
                letter-spacing: 1.3ch;
                text-transform: uppercase;
                font-size: 0.7em;
                margin-bottom: 10px;
            }

            .title h1 {
                font-family: 'Quicksand', sans-serif;
                font-size: 3em;
                margin-bottom: 30px;

                span {
                    color: #00D9A6;
                }
            }
        }

        .overview {
            margin: 40px 0 50px;
            color: #555555;
            font-size: 0.8em;
            letter-spacing: 0.1ch;
        }

        .button {
            margin-bottom: 50px;
        }

        .slide-show {
            display: flex;
            align-items: center;
            justify-content: space-between;

            .social-list ul {
                display: flex;
                gap: 10px;
                font-size: 0.8em;

                li {
                    font-size: 0.8em;
                    font-weight: bold;
                    letter-spacing: 0.1ch;
                }
            }

            .jumbo-slider {
                display: flex;
                gap: 20px;
                background-color: #444444;
                padding: 10px 24px;
                border-radius: 20px;
                color: #AAAAAA;
            }
        }
    }
}
</style>