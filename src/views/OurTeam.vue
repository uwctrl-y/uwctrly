<template>
    <section class="our-team-section">
        <div class="Header">
            <h1 class="heading-text">
                Our Team
            </h1>
        </div>
        <div class="parallax-container">
<!--            image 1-->
            <div class="sponsor-box-two">
                <img class="circle" :style="{ top: `${scrollOffset * 0.5}px` }" ref="graphic" src="../assets/ourTeam/testImages/image1.png" />
            </div>

<!--            image 2-->
            <div class="sponsor-box-two">
                <img class="circle" :style="{ top: `${scrollOffset * 0.3}px` }" ref="graphic" src="../assets/ourTeam/testImages/image2.png" />
            </div>

<!--            image 3-->
            <div class="sponsor-box-two">
                <img class="circle" :style="{ top: `${scrollOffset * 0.2}px` }" ref="graphic" src="../assets/ourTeam/testImages/image3.png" />
            </div>

<!--            image 4-->
            <div class="sponsor-box-two">
                <img class="circle" :style="{ top: `${scrollOffset * 0.2}px` }" ref="graphic" src="../assets/ourTeam/testImages/image4.png" />
            </div>

        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            scrollOffset: 0,
        };
    },
    mounted() {
        window.addEventListener("scroll", this.onScroll);
    },
    beforeDestroy() {
        window.removeEventListener("scroll", this.onScroll);
    },
    methods: {
        onScroll() {
            this.scrollOffset = -window.scrollY * 0.5; // Adjust the scrolling speed here (0.5 is just an example)
        },
    },
};
</script>

<style scoped>
.our-team-section {
    border-radius: 16px;
    background: white;
    padding: 96px;
    color: #09702C;
}

.Header {
    display: flex;
    justify-content: center;
}

.heading-text {
    font-size: 180px;
    font-style: normal;
    font-weight: 500;
    line-height: 180px;
    letter-spacing: -9px;
    text-transform: uppercase;
    margin-bottom: -8.5vh;
}

.parallax-container {
    overflow: hidden;
    position: relative;
    height: 60vh; /* Adjust this height to control the parallax effect range */
}

.sponsor-box-two {
    align-items: center;
    text-align: center;
    width: 100%;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.circle {
    border-radius: 50%;
    max-width: 100%;
    transition: top 0.2s ease; /* Add a smooth transition for the parallax effect */
}
</style>
