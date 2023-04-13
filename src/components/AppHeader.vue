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

            slides: [
                {
                    number: "01",
                    image: "/images/Group-36-2x.png",
                    title: "We Are a Web Design",
                    titleSpan: "Agency",
                    overview: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics a large language ocean.Separated they live in Bookmarksgrove",
                },
                {
                    number: "02",
                    image: "/images/Group-40-2x.png",
                    title: "A Group of Expert",
                    titleSpan: "Planners",
                    overview: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics a large language ocean.Separated they live in Bookmarksgrove. Far far away, behind the word mountains, far from the countriesVokalia and Consonantia, there live the blind texts.",
                },
                {
                    number: "03",
                    image: "/images/Group-35-2x.png",
                    title: "Focus on Your",
                    titleSpan: "Business",
                    overview: "Far far away, behind the word mountains, far from the countries Vokalia and Consonantia, there live the blind texts. Separated they live in Bookmarksgrove right at the coast of the Semantics a large language ocean.Separated they live in Bookmarksgrove. Separated they live in Bookmarksgrove right at the coast of the Semantics a large language ocean.",
                },
            ],
            activeSlideIndex: 0,
        };
    },

    methods: {
        activeNavLinks(index) {
            this.activeNavLinksIndex = index;
        },
        activeJumboSlides(index) {
            this.activeSlideIndex = index;
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
                    <li v-for="(link, index) in navLinks" :class="this.activeNavLinksIndex == index ? 'active' : ''"
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
                    <h1>{{ this.slides[this.activeSlideIndex].title }} <span>{{ this.slides[this.activeSlideIndex].titleSpan
                    }}</span>
                    </h1>
                </div>
                <div class="separator">
                    <div class="separator-line line1"></div>
                    <div class="separator-line line2"></div>
                </div>
                <div class="overview">
                    <p>{{ this.slides[this.activeSlideIndex].overview }}</p>

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
                    <div class="jumbo-sliders">
                        <div v-for="(slide, index) in slides " :class="this.activeSlideIndex == index ? 'active' : ''"
                            @click="activeJumboSlides(index)" class="jumbo-slider">{{ slide.number }}</div>
                    </div>
                </div>
            </div>
            <div class="jumbo-image">
                <img :src="this.slides[this.activeSlideIndex].image" :alt="this.slides[activeSlideIndex].title">
            </div>
        </section>
    </header>
</template>

<style lang="scss" scoped>
@use "../scss/variables" as *;

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

            i {
                cursor: pointer;

                &:hover {
                    color: gray;
                }
            }
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
            gap: 26px;
            text-transform: uppercase;
            font-size: 0.85em;

            li {
                cursor: pointer;
                color: #555555;
                transition: all 0.2s ease-in-out;

                &.active {
                    color: $primary-color;
                }

                &:hover {
                    transform: scale(1.12);
                }
            }
        }

        .nav-button {
            display: flex;
            align-items: center;
            gap: 30px;

            i {
                color: $primary-color;
                cursor: pointer;
            }
        }
    }

    .jumbo {
        display: flex;
        background-color: #F9F9F9;
        overflow: hidden;

        .jumbo-image {
            margin: -20px -255px -20px 0;
            width: 70%;

            img {
                width: 85%;

            }
        }

        .jumbo-description {
            display: flex;
            flex-direction: column;
            height: 100%;
            width: 50%;
            padding-top: 110px;
            padding-left: 50px;

            .experience {
                color: $primary-color;
                letter-spacing: 1.3ch;
                text-transform: uppercase;
                font-size: 0.7em;
                margin-bottom: 10px;
            }

            .title h1 {
                font-family: $font-title;
                font-size: 3.8em;
                margin-bottom: 30px;
                width: 80%;

                span {
                    color: $primary-color;
                }
            }
        }

        .overview {
            margin: 40px 0 30px;
            color: $overview-color;
            font-size: 0.8em;
            letter-spacing: 0.1ch;
            line-height: 1.4;
            min-height: 80px;
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

            .jumbo-sliders {
                display: flex;
                align-items: center;
                justify-content: space-around;
                background-color: #444444;
                width: 160px;
                height: 42px;
                border-radius: 20px;
                color: #AAAAAA;

                .jumbo-slider {
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    width: 80px;
                    height: 36px;
                    margin: 0 3px;
                    cursor: pointer;
                }

                .active {
                    background: linear-gradient(to right, $primary-color, $secondary-color);
                    border-radius: 20px;
                    color: rgb(255, 255, 255, 0.7);
                }
            }
        }
    }
}

@media (max-width: 1024px) {
    header {

        .jumbo {

            .jumbo-description {
                .title h1 {

                    font-size: 2.8em;
                }
            }

            .slide-show {
                .social-list ul {
                    gap: 4px;
                    font-size: 0.7em;

                    li {
                        font-size: 0.6em;
                    }
                }

                .jumbo-sliders {
                    width: 120px;

                    .jumbo-slider {
                        width: 60px;
                    }
                }
            }
        }
    }
}
</style>