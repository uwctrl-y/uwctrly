<template>
    <section class="our-team-section" ref="ourTeamSection">
        <div class="Header">
            <h1 class="heading-text">Our Team</h1>
        </div>
        <div class="parallax-container">
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
            prevScrollY: 0, // Store the previous scroll position
            imageUrls: [
                "src/assets/ourTeam/testImages/zee.png",
                "src/assets/ourTeam/testImages/image2.png",
                "src/assets/ourTeam/testImages/image3.png",
                "src/assets/ourTeam/testImages/image4.png",
                "src/assets/ourTeam/testImages/image1.png",
                "src/assets/ourTeam/testImages/image5.png",
                "src/assets/ourTeam/testImages/image6.png",
                "src/assets/ourTeam/testImages/image7.png",
                "src/assets/ourTeam/testImages/image8.png",
                "src/assets/ourTeam/testImages/image9.png",
                "src/assets/ourTeam/testImages/image10.png",
                "src/assets/ourTeam/testImages/image11.png",
            ],
            currentImageIndex: 0, // The index of the currently displayed image
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
        const increment = 0.02; // Adjust this constant increment to control the speed

        if (scrollDirection === "down") {
          this.scrollOffset += increment * scrollDifference; // Use the constant increment multiplied by the scroll difference
        } else {
          this.scrollOffset -= increment * scrollDifference; // Use the constant increment multiplied by the scroll difference
        }

        if (this.lockScreen) {
          // Update the displayed image index based on the scroll direction
          if (scrollDirection === "down") {
            this.currentImageIndex = Math.min(
                this.currentImageIndex + 1,
                this.imageUrls.length - 1
            );
          } else {
            this.currentImageIndex = Math.max(this.currentImageIndex - 1, 0);
          }
        }

        this.prevScrollY = currentScrollY;
      },
        handleSectionIntersection(entries) {
            // Check if the "Our Team" section is fully in view
            const inView = entries[0].isIntersecting;

            if (inView) {
                // Unlock the screen when the section is in view
                this.lockScreen = false;
            } else {
                // Lock the screen if the section is not in view
                this.lockScreen = true;
            }
        },
    },
};
</script>

<style scoped>
.our-team-section {
    border-radius: 16px;
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
    height: 70vh; /* Adjust this height to control the parallax effect range */
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
