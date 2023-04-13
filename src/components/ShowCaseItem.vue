<script>

import { defineComponent } from 'vue'
import { Carousel, Pagination, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
    name: 'Autoplay',
    components: {
        Carousel,
        Slide,
        Pagination,
    },

    data() {
        return {
            projects: [
                {
                    name: "The Basket of Flower",
                    image: "/images/ina-soulis-227104-unsplash-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "A Famous Ferris Wheel",
                    image: "/images/sunisa-misa-531163-unsplash-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "Complementary Colors",
                    image: "/images/355H-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "Business Prestige",
                    image: "/images/photo-1448932252197-d19750584e56-1024x1024.jpg",
                    category: "Branding",
                },
                {
                    name: "Colorful Origami Boats",
                    image: "/images/business-competition-PB366D8-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "Modern Couch",
                    image: "/images/cozy-sofa-in-living-room-PQR5AB9-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "Hot Air Balloons",
                    image: "/images/photo-1448932252197-d19750584e56-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "Make Difference",
                    image: "/images/cody-davis-253928-unsplash-1024x1024.jpg",
                    category: "Branding",
                },
            ],

            customers: [
                {
                    image: "/images/businesswoman-analysing-document-P8WSNMC-1024x820.jpg",
                    name: "Lissa Durbin",
                    overview: "When it comes to barbequing, there are two main schools of thought for the techniques that you can use. Freshly scrambled eggs with applewood smoked bacon - are amazing!",
                },
                {
                    image: "/images/businesswoman-analysing-document-P8WSNMC-1024x820.jpg",
                    name: "Lisa Simpson",
                    overview: "When it comes to barbequing, there are two main schools of thought for the techniques that you can use. Freshly scrambled eggs with applewood smoked bacon - are amazing!",
                },
                {
                    image: "/images/businesswoman-analysing-document-P8WSNMC-1024x820.jpg",
                    name: "Marge Simpson",
                    overview: "When it comes to barbequing, there are two main schools of thought for the techniques that you can use. Freshly scrambled eggs with applewood smoked bacon - are amazing!",
                },
            ],
        };
    },

})

</script>

<template>
    <div id="showcase" class="container-centered">
        <section class="projects-example">
            <div class="separator">
                <div class="separator-line line1"></div>
                <div class="separator-line line2"></div>
            </div>
            <div class="section-text">
                <div class="section-title">
                    <h2>Our recent <span>web designs</span> & some examples of past <span>projects</span></h2>
                </div>
                <div class="section-overview">
                    <p>Far far away,behind the word mountains, far from countries
                        Vokalia and Consonantia, there live the blind texts. Separated
                        they live in Bookmarksgrove right at the coast of the Semantics,
                        a large language ocean.Separated they live in Bookmarkgrove. Far far away,
                        behind the word mountains, far from the countries Vokalia and Consonantia,
                        there live the bind texts. Separated they live in Bookmarksgrove.
                    </p>
                </div>
            </div>

            <div class="separator">
                <div class="separator-line line1"></div>
                <div class="separator-line line2"></div>
            </div>
            <div class="card-container">
                <div class="card" v-for="project in projects">
                    <img :src="project.image" :alt="project.name">
                    <div class="overlay"></div>
                    <div class="text-absolute">
                        <div class="title"> {{ project.name }}</div>
                        <div class="category">{{ project.category }}</div>
                    </div>
                </div>
            </div>
            <div class="read-more-button">
                <button class="btn btn-primary">READ MORE</button>
            </div>

        </section>

        <!-- START CAROUSEL -->
        <section class="customers-review">
            <img class="back-image" src="/images/four-businesspeople-in-a-boardroom-with-paperwork-PC4V8H4.jpg" alt="">
            <div class="overlay"></div>
            <Carousel :autoplay="2000" :wrap-around="true">
                <Slide v-for="slide in customers" :key="slide">
                    <div class="carousel__item">

                        <div class="text">
                            <div class="icon">
                                <i class="fa-solid fa-quote-left"></i>
                            </div>
                            <div class="customers-details">
                                <div class="customers-overview">
                                    {{ slide.overview }}
                                </div>
                                <div class="customers-image">
                                    <img :src="slide.image" alt="Lissa Durbin">
                                </div>
                                <div class="customers-name">
                                    {{ slide.name }}
                                </div>
                                <div class="type">Client</div>
                            </div>
                        </div>
                    </div>
                </Slide>
                <template #addons>
                    <Pagination />
                </template>
            </Carousel>
        </section>
        <!-- END CAROUSEL -->
    </div>
</template>

<style lang="scss" scoped>
@use "../scss/variables" as *;

.projects-example {
    margin: 0 10px;

    .section-title {
        margin: 30px 0;
    }

    .card-container {
        position: relative;
        display: flex;
        flex-flow: row wrap;
        gap: 4px;
        margin: 60px 0 80px;

        .card {
            position: relative;
            width: calc(100% / 4 - (4px / 4 * 3));
            transition: all 0.2s ease-in-out;
            cursor: pointer;

            img {
                display: block;
                width: 100%;
                border-radius: 4px;
            }

            .overlay {
                position: absolute;
                display: none;
                width: 100%;
                height: 100%;
                top: 0;
                bottom: 0;
                border-radius: 4px;
                background: linear-gradient(to right, rgba(155, 225, 93, 0.8), rgba(0, 217, 166, 0.8));
            }

            .text-absolute {
                position: absolute;
                display: none;
                flex-direction: column;
                gap: 10px;
                bottom: 15%;
                left: 8%;
                color: white;
                font-weight: bold;
                font-size: 1.25em;
                font-family: $font-title;


                .category {
                    font-size: 0.7em;
                    text-transform: uppercase;
                    font-weight: 400;
                }
            }

            &:hover .text-absolute,
            &:hover .overlay {
                display: flex;
            }

            &:hover {
                position: relative;
                z-index: 1;
                transform: scale(1.10);
            }


        }
    }

    .read-more-button {
        text-align: center;
        margin-bottom: 150px;
    }

    .section-text {
        display: flex;
        justify-content: space-between;

        .section-title {
            width: 40%;

            h2 {
                font-family: $font-title;
                font-size: 2.6em;
                font-weight: 600;

                span {
                    color: $primary-color;
                }
            }
        }

        .section-overview {
            align-self: flex-end;
            width: 50%;
            font-size: 0.85em;
            color: $overview-color;
            line-height: 1.5;
        }
    }
}

.carousel {
    position: absolute;
    color: white;
    top: 60%;
    left: 50%;
    transform: translate(-50%, -50%);
    line-height: 1.8;
    text-align: center;
    font-size: 1.1em;
    font-style: italic;
    width: 100%;
}

.carousel__item {
    height: 500px;
    width: 100%;
}

.customers-review {
    position: relative;
    height: 550px;
    width: 100%;

    .back-image {
        width: 100%;
        height: 550px;
        object-fit: cover;
        opacity: 0.3;
    }

    .text {
        .icon {
            font-size: 2.4em;
            color: $primary-color;
        }

        .customers-details {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-top: 40px;

            .customers-overview {
                width: 50%;
            }

            .customers-image {
                margin: 30px 0;

                img {
                    width: 80px;
                    border-radius: 50%;
                    border: 3px solid white;
                }
            }

            .customers-name {
                color: $primary-color;
                font-size: 0.9em;
                text-transform: uppercase;
            }

            .type {
                font-size: 0.8em;
            }
        }

    }

    .overlay {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: rgb(0, 0, 0, 0.7);
    }
}
</style>