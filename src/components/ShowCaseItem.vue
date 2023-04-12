<script>

export default {
    data() {
        return {
            projects: [
                {
                    name: "A Famous Ferris Wheel",
                    image: "/images/ina-soulis-227104-unsplash-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "A Famous Ferris Wheel",
                    image: "/images/sunisa-misa-531163-unsplash-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "A Famous Ferris Wheel",
                    image: "/images/355H-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "A Famous Ferris Wheel",
                    image: "/images/photo-1448932252197-d19750584e56-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "A Famous Ferris Wheel",
                    image: "/images/business-competition-PB366D8-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "A Famous Ferris Wheel",
                    image: "/images/cozy-sofa-in-living-room-PQR5AB9-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "A Famous Ferris Wheel",
                    image: "/images/photo-1448932252197-d19750584e56-1024x1024.jpg",
                    category: "Marketing",
                },
                {
                    name: "A Famous Ferris Wheel",
                    image: "/images/cody-davis-253928-unsplash-1024x1024.jpg",
                    category: "Marketing",
                },
            ],
        };
    },

}
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
        <section class="customers-review">
            <div class="text">
                <div class="icon">
                    <i class="fa-solid fa-quote-left"></i>
                </div>
                <p>When it comes to barbequing, there are two main schools of thought for the
                    techniques that you can use. Freshly scrambled eggs with applewood smoked bacon
                    - are amazing!
                </p>
                <div class="customers-details">
                    <div class="customers-image">
                        <img src="/images/businesswoman-analysing-document-P8WSNMC-1024x820.jpg" alt="Lissa Durbin">
                    </div>
                    <div class="customers-name">
                        LISSA DURBIN
                    </div>
                    <div class="type">Client</div>
                </div>
            </div>
            <div class="overlay"></div>

        </section>

    </div>
</template>

<style lang="scss" scoped>
.projects-example {
    margin: 0 10px;

    .section-title {
        margin: 30px 0;
    }

    .card-container {
        display: flex;
        flex-flow: row wrap;
        gap: 4px;
        margin: 60px 0 80px;

        .card {
            position: relative;
            width: calc(100% / 4 - (4px / 4 * 3));
            transition: all 0.4s ease-in-out;
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
                background: linear-gradient(to right, #2ef41c90, #00D9A6);
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
                font-size: 1.2em;


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
                z-index: 2;
                transform: scale(1.13);
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
                font-family: 'Quicksand', sans-serif;
                font-size: 2.4em;

                span {
                    color: #00D9A6;
                }
            }
        }

        .section-overview {
            align-self: flex-end;
            width: 55%;
            font-size: 0.85em;
            color: #555555;
            line-height: 1.5;
        }
    }
}

.customers-review {
    position: relative;
    height: 600px;
    background-image: url("/images/four-businesspeople-in-a-boardroom-with-paperwork-PC4V8H4.jpg");
    background-size: cover;
    background-position: center;
    opacity: 0.9;
    margin-bottom: 200px;

    .text {
        position: absolute;
        color: rgba(255, 255, 255, 0.6);
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        line-height: 2;
        text-align: center;
        font-size: 1.2em;
        font-style: italic;

        .icon {
            font-size: 2.4em;
            color: #00D9A6;
        }

        .customers-details {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-top: 40px;

            .customers-image {
                margin: 20px 0;

                img {
                    width: 80px;
                    border-radius: 50%;
                    border: 3px solid white;
                }
            }

            .customers-name {
                color: #00D9A6;
                font-size: 0.9em;
            }

            .type {
                font-size: 0.8em;
            }
        }

    }

    .overlay {
        width: 100%;
        height: 100%;
        background-color: rgb(0, 0, 0, 0.9);
    }
}
</style>