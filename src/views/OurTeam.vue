<template>
    <section class="our-team-section" ref="ourTeamSection">
        <div class="parallax-container">
            <div class="heading-container">
                <h1 class="heading-text">Our Team</h1>
            </div>
            <div class="sponsor-box-two">
                <img
                        class="circle"
                        :style="{ top: `${scrollOffset * 0.5}px` }"
                        :src="currentImage"
                        ref="graphic"
                />
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            scrollOffset: 0,
            prevScrollY: 0,
            imageUrls: [
                "src/assets/ourTeam/testImages/aashi.png",
                "src/assets/ourTeam/testImages/becca.png",
                "src/assets/ourTeam/testImages/charissa.png",
                "src/assets/ourTeam/testImages/dayun.png",
                "src/assets/ourTeam/testImages/diana.png",
                "src/assets/ourTeam/testImages/jake.png",
                "src/assets/ourTeam/testImages/yosha.png",
                "src/assets/ourTeam/testImages/stella.png",
                "src/assets/ourTeam/testImages/kyleigh.png",
            ],
            currentImageIndex: 0,
            lockScreen: true,
        };
    },
    computed: {
        currentImage() {
            return this.imageUrls[this.currentImageIndex];
        },
    },
    mounted() {
        window.addEventListener("scroll", this.onScroll);
         const options = {
             root: null,
             rootMargin: "0px",
             threshold: 1.0,
        };
        const observer = new IntersectionObserver(
            this.handleSectionIntersection,
            options
        );
        observer.observe(this.$refs.ourTeamSection);
    },
    beforeDestroy() {
        window.removeEventListener("scroll", this.onScroll);
    },
    methods: {
      onScroll() {
        const currentScrollY = window.scrollY;
        const scrollDirection = currentScrollY > this.prevScrollY ? "down" : "up";
        const scrollDifference = Math.abs(currentScrollY - this.prevScrollY);
        const increment = 0.5;

        if (scrollDirection === "down") {
          this.scrollOffset += increment * scrollDifference;
        } else {
          this.scrollOffset -= increment * scrollDifference;
        }

        if (this.lockScreen && scrollDifference > 15) {
          if (scrollDirection === "down") {
            this.currentImageIndex = Math.min(
                this.currentImageIndex + 1,
                this.imageUrls.length - 1
            );
          } else {
            this.currentImageIndex = Math.max(this.currentImageIndex - 1, 0);
          }
          this.prevScrollY = currentScrollY;
        }
      },
        handleSectionIntersection(entries) {
            const inView = entries[0].isIntersecting;

            if (inView) {
                this.lockScreen = false;
            } else {
                this.lockScreen = true;
            }
        },
    },
};
</script>

<style scoped>
.our-team-section {
    border-radius: 16px;
    padding: 120px;
    color: #09702C;
    position: relative;
    min-height: 80vh;
}

.heading-container{
    position: absolute;
    z-index: 1;
}

.heading-text {
    font-size: 180px;
    font-style: normal;
    font-weight: 500;
    line-height: 180px;
    letter-spacing: -9px;
    text-transform: uppercase;
    margin-bottom: 60vh;
}

.parallax-container {
    overflow: hidden;
    position: relative;
    height: 80vh;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
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

@media screen and (max-width: 768px) {
    .heading-text {
        font-size: 12vw;
        letter-spacing: -0.1em;
    }
}

@media screen and (max-width: 480px) {
    .heading-text {
        font-size: 16vw;
        letter-spacing: -0.05em;
    }
}

</style>
