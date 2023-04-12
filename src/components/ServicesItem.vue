<script>
export default {
    data() {
        return {
            services: [
                {
                    image: "/images/speedometer.png",
                    title: "Speed Optimization",
                    overview: "Far far away, behind the word mountains, far from the countries Vokalia Separated..."
                },
                {
                    image: "/images/cloud.png",
                    title: "Cloud Solutions",
                    overview: "Far far away, behind the word mountains, far from the countries Vokalia Separated...",
                },
                {
                    image: "/images/tablet.png",
                    title: "Website Design",
                    overview: "Far far away, behind the word mountains, far from the countries Vokalia Separated...",
                },
                {
                    image: "/images/stopwatch.png",
                    title: "Online Marketing",
                    overview: "Far far away, behind the word mountains, far from the countries Vokalia Separated...",
                }
            ],
        };
    },

}
</script>

<template>
    <div id="services" class="container-centered">
        <section class="our-services">
            <div class="our-services-left">
                <h2>We Are Here To Make Your <span>Website</span> Look More<span> Elegant</span> And Stylish</h2>
                <div class="separator">
                    <div class="separator-line line1"></div>
                    <div class="separator-line line2"></div>
                </div>
                <div class="view-all-button">
                    <button class="btn btn-primary">VIEW ALL</button>
                </div>
            </div>
            <div class="our-services-right">
                <div v-for="service in services" class="service-box">
                    <div class="icon">
                        <img :src=service.image alt="Speed Optimization">
                    </div>
                    <div class="title">{{ service.title }}</div>
                    <div class="text">{{ service.overview }}</div>
                </div>

            </div>
        </section>
        <section class="our-missions">
            <div class="our-missions-left">
                <div class="overlay"></div>
                <div class="absolute-image">
                    <img src="/images/businesswoman-analysing-document-P8WSNMC-1024x820.jpg" alt="our missions image">
                </div>
            </div>
            <div class="our-missions-right">
                <div class="title">
                    <h3>learn more about our <span>missions</span></h3>
                </div>
                <div class="separator">
                    <div class="separator-line line1"></div>
                    <div class="separator-line line2"></div>
                </div>
                <div class="overview">
                    <p>Far far away,behind the word mountains, far from countries
                        Vokalia and Consonantia, there live the blind texts. Separated
                        they live in Bookmarksgrove right at the coast of the Semantics,
                        a large language ocean.Separated they live in Bookmarkgrove.
                    </p>
                </div>
                <div class="view-all-button">
                    <button class="btn btn-primary">READ MORE</button>
                </div>
            </div>
        </section>
    </div>
</template>

<style lang="scss" scoped>
.our-services {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 150px;

    .our-services-left {
        width: 35%;
        line-height: 1.5;
        padding-left: 20px;

        h2 {
            font-family: 'Quicksand', sans-serif;
            margin-bottom: 30px;
            font-size: 2.5em;
            font-weight: 600;

            span {
                color: #00D9A6;
            }
        }

        .separator {
            margin-bottom: 40px;
        }
    }

    .our-services-right {
        width: 60%;
        display: flex;
        flex-flow: row wrap;
        gap: 28px;
    }

    .service-box {
        display: flex;
        flex-direction: column;
        gap: 14px;
        width: calc(100% / 2 - 28px);
        padding: 40px 60px;
        border-radius: 12px;
        box-shadow: 0 0 50px 2px rgba(0, 0, 0, 0.1);

        .title {
            font-size: 1.3em;
            color: #393939;
        }

        .text {
            font-size: 0.7em;
            color: #555555;
            line-height: 1.5;
        }
    }
}

.our-missions {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background-color: #f9f9f9;
    padding: 150px 0;
    margin-bottom: 150px;

    .our-missions-left {
        position: relative;
        width: 40%;
        height: 400px;
        background-image: url("/images/busy-architect-PYVKWM4-1024x872.jpg");
        background-repeat: no-repeat;
        background-size: cover;
        border-radius: 0 30px 0 0;

        .overlay {
            width: 100%;
            height: 100%;
            background: linear-gradient(#19d5a9, #2ef41c90);
            border-radius: 0 30px 0 0;
        }

        .absolute-image {
            position: absolute;
            top: 10%;
            right: -20%;

            img {
                width: 500px;
                border-radius: 30px;
            }
        }
    }

    .our-missions-right {
        width: 30%;
        display: flex;
        flex-direction: column;
        gap: 30px;
        margin-right: 120px;

        .title h3 {
            font-family: 'Quicksand', sans-serif;
            font-size: 2.4em;
            font-weight: 600;

            span {
                color: #00D9A6;
            }
        }

        .overview {
            font-size: 0.9em;
            color: #555555;

        }
    }

}
</style>