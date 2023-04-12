<script>

export default {
    data() {
        return {
            cards: [
                {
                    image: "/images/serious-businesswoman-with-documents-talking-on-P9Q6LX6-1024.jpg",
                    title: "Marketing Ideas",
                    date: "May 24, 2018 by Alex",
                },
                {
                    image: "/images/Businessman-at-the-desk-in-his-office-resting--1024x768.jpg",
                    title: "Rest During Working Hours",
                    date: "May 24, 2018 by Alex",
                },
                {
                    image: "/images/simple-home-office-with-tree-PBXRXYB-large-1024x768.jpg",
                    title: "Develop Your Startup Idea",
                    date: "May 24, 2018 by Alex",
                }
            ],

            clients: [
                {
                    name: "Avantgarde",
                    logo: "/images/client-1-2x.png",
                },
                {
                    name: "Fastlane",
                    logo: "/images/client-9-2x.png",
                },
                {
                    name: "Ron Jones",
                    logo: "/images/client-7-2x.png",
                },
                {
                    name: "Chippy's",
                    logo: "/images/client-3-2x.png",
                },
                {
                    name: "Bullseye",
                    logo: "/images/client-4-2x.png",
                },
                {
                    name: "Mighty furnitures",
                    logo: "/images/client-5-2x.png",
                },
            ],
        };
    },

    components: {

    }
}
</script>

<template>
    <div class="blog container-centered">
        <div class="blog-title">
            <h2>Latest News & Our <span>Blog</span></h2>
        </div>
        <div class="separator">
            <div class="separator-line line1"></div>
            <div class="separator-line line2"></div>
        </div>
        <div class="blog-cards">
            <div v-for="card in cards" class="card">
                <img :src="card.image" :alt="card.title">
                <div class="cards-details">
                    <div class="date">
                        {{ card.date }}
                    </div>
                    <div class="title">
                        <span><i class="fa-solid fa-circle"></i></span>{{ card.title }}
                    </div>

                </div>
            </div>
            <div class="blog-button">
                <button class="btn btn-secondary">VIEW ALL POST</button>
            </div>
        </div>
        <section class="questions">
            <div class="questions-card secondary">
                <div class="ready">Are You Ready?</div>
                <div class="email-insert-title">
                    <h4>Start a New Project</h4>
                </div>
                <div class="questions-input">
                    <input type="text" placeholder="Enter Your Email Address">
                </div>
            </div>
            <div class="questions-card primary">
                <div class="dont-wait">What Are You Waiting for</div>
                <div class="talk-with-us-title">
                    <h4>Let's Talk About Work</h4>
                </div>
                <div class="questions-button">
                    <button class="btn btn-secondary">START NOW</button>
                </div>
            </div>

        </section>
        <section class="client">

            <div class="client-logo">
                <img v-for="client in clients" :src="client.logo" :alt="client.name">
            </div>
        </section>
    </div>
</template>

<style lang="scss" scoped>
.blog {

    .blog-title,
    .separator {
        display: flex;
        justify-content: center;
        margin-bottom: 30px;

        h2 {
            font-family: 'Quicksand', sans-serif;
            font-size: 2.4em;
            font-weight: 600;
            margin-bottom: 30px;

            span {
                color: #00D9A6;
            }
        }
    }

    .blog-cards {
        display: flex;
        flex-flow: row wrap;
        gap: 10px;
        padding: 0 10px;


        .card {
            position: relative;
            width: calc(100% / 3 - (10px / 3 * 2));
            margin-bottom: 80px;


            img {
                width: 100%;
                border-radius: 10px;
            }
        }

        .cards-details {
            display: flex;
            flex-direction: column;
            justify-content: center;
            gap: 6px;
            position: absolute;
            padding-left: 30px;
            width: 80%;
            height: 35%;
            background-color: white;
            bottom: -10%;
            right: 50%;
            transform: translateX(50%);
            box-shadow: 0 0 50px rgba(0, 0, 0, 0.2);
            border-radius: 10px;


            .date {
                color: #AAAAAA;
                font-size: 0.7em;
            }

            .title {
                display: flex;
                align-items: center;
                font-family: 'Quicksand', sans-serif;

                span {
                    color: #00D9A6;
                    font-size: 0.5em;
                    padding-right: 8px;
                }
            }
        }

        .blog-button {
            display: flex;
            justify-content: center;
            width: 100%;
        }
    }
}

.questions {
    display: flex;
    gap: 20px;
    margin: 150px 10px 0;

    .questions-card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 20px;
        width: calc(100% / 2);
        padding: 50px 0;
        border-radius: 20px;

        .ready {
            color: #AAAAAA;
        }

        .dont-wait {
            color: rgba(255, 255, 255, 0.7);
        }

        h4 {
            font-family: 'Quicksand', sans-serif;
            font-size: 1.8em;
            font-weight: 600;
            margin-bottom: 30px;
            color: white;
        }

        .questions-input {
            input {
                padding: 16px 100px;
                border-radius: 30px;
                border: none;
                background-color: rgb(75, 75, 75);
                box-shadow: 0 0 40px rgba(0, 0, 0, 0.6);
            }

            ::placeholder {
                color: #AAAAAA;
            }
        }
    }

    .primary {
        background: linear-gradient(to right, #00D9A6, #2ef41c90);
        box-shadow: 2px 6px 20px #00D9A680;
    }

    .secondary {
        background: linear-gradient(to right, #444444, #202020);
        box-shadow: 2px 2px 20px #20202080;
    }
}

.client {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 100px 0;
    background-color: #f9f9f980;

    .client-logo {
        display: flex;
        align-items: center;
        gap: 60px;
    }
}
</style>