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
import aashi from '../assets/ourTeam/testImages/aashi.png';
import becca from '../assets/ourTeam/testImages/becca.png';
import charissa from '../assets/ourTeam/testImages/charissa.png';
import dayun from '../assets/ourTeam/testImages/da_yun.png';
import diana from '../assets/ourTeam/testImages/diana.png';
import jake from '../assets/ourTeam/testImages/jake.png';
import yosha from '../assets/ourTeam/testImages/yosha.png';
import stella from '../assets/ourTeam/testImages/stella.png';
import kyleigh from '../assets/ourTeam/testImages/kyleigh.png';

export default {
   
    data() {
        return {
            scrollOffset: 0,
            prevScrollY: 0,
            imageUrls: [
                aashi,
                becca,
                charissa,
                dayun,
                diana,
                jake,
                yosha,
                stella,
                kyleigh
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
    /* position: absolute;*/
    z-index: 1; 
    display: flex;
    justify-content: center;
    /* margin-bottom: 295px; */
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
    /* height: 80vh; */
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

@media screen and (max-width: 860px) {
  .heading-text {
    font-size: 140px;
  }
}

@media screen and (max-width: 800px) {
  .heading-text {
    font-size: 120px;
  }
}

@media screen and (max-width: 600px) {
    .our-team-section {
        padding: 50px;
    }
}

@media screen and (max-width: 400px) {
  .heading-text {
    font-size: 90px;
    letter-spacing: -5px;
    line-height: 100px;
  }

  .our-team-section {
        padding: 30px;
    }
}



</style>
