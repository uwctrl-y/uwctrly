<template>
    <section class="faq-section" ref="faqSection">
        <div class="title">
            <div>FAQ</div>
            <img class="faq-graphic" ref="graphic" src="../assets/faqGraphic.svg" />
            <div>Frequently Asked Questions</div>
        </div>
        <div class="questions-list">
            <div class="list1">
                <div class="qanda" v-for="qa in questions1" :key="qa">
                <div @click="show(qa.question)" class="question">
                    <div class="question-text">{{ qa.question }}</div>
                    <img :class="{ 'arrow-active': qa.question == currentQuestion, 'arrow-down': true }" ref="graphic"
                        src="../assets/faqArrow.svg" />
                </div>
                <Transition name="fadeHeight">
                    <div v-if="qa.question == currentQuestion" class="answer">{{ qa.answer }}</div>
                </Transition>
            </div>
            </div>
            <div class="list2">
                <div class="qanda" v-for="qa in questions2" :key="qa">
                <div @click="show(qa.question)" class="question">
                    <div class="question-text">{{ qa.question }}</div>
                    <img :class="{ 'arrow-active': qa.question == currentQuestion, 'arrow-down': true }" ref="graphic"
                        src="../assets/faqArrow.svg" />
                </div>
                <Transition name="fadeHeight">
                    <div v-if="qa.question == currentQuestion && qa.answer[0] != 'C'" class="answer">{{ qa.answer }}</div>
                    <div v-else-if="qa.question == currentQuestion && qa.answer[0] == 'C'" class="answer">
                        Contact us at <a href="mailto:ctrlplusy2023@gmail.com">ctrlplusy2023@gmail.com</a>!
                    </div>
                </Transition>
            </div>
            </div>
        </div>

    </section>
</template>
  
<script>

export default {
    data() {
        return {
            questions1: [
                {
                    "question": "Who can attend?",
                    "answer": "The designathon is open to anyone passionate about design and innovation! Whether you're a seasoned designer, a student, a creative professional, or someone simply interested in exploring the world of design, you're welcome to attend and participate."
                },
                {
                    "question": "Do I apply with a team?",
                    "answer": "Yes, you can definitely apply with a team! If you already have a team in mind, you can register together. Don't worry if you don't have a team, though – we've got you covered! You can also register individually, and we'll help you find a team that aligns with your skills and interests."
                },
                {
                    "question": "How many people can be on one team?",
                    "answer": "Teams can consist of up to four members. While individual participation is allowed, we encourage team collaboration as it often leads to diverse and innovative solutions. If you're registering as an individual, we'll assist you in forming a well-balanced team during the event."
                },
            ],
            questions2: [
                {
                    "question": "When will registration begin?",
                    "answer": "Registration for the designathon will kick off on the 1st of September. Mark your calendars and get ready to secure your spot in this exciting event!"
                },
                {
                    "question": "What if I want to join virtually?",
                    "answer": "We understand that everyone's circumstances are different. That's why we offer both in-person and virtual participation options. If you're unable to join us physically, you can still be a part of the designathon from wherever you are, participating virtually and contributing your ideas and skills to the event."
                },
                {
                    "question": "Still have questions?",
                    "answer": "Contact us at ctrlplusy2023@gmail.com!"
                },
            ],
            currentQuestion: ""
        };
    },
    methods: {
        show(question) {
            if (this.currentQuestion == question) this.currentQuestion = "";
            else this.currentQuestion = question;
        }
    }

}
</script>
  
<style scoped>
.faq-section {
    color: #09702C;
    margin-block: 268px;
}

.title {
    text-align: center;
}

.title> :first-child {
    font-size: 180px;
    font-style: normal;
    font-weight: 500;
    line-height: 180px;
    letter-spacing: -9px;
    text-transform: uppercase;
    margin-bottom: 16px;
}

.title> :last-child {
    font-size: 30px;
    font-style: normal;
    font-weight: 400;
    line-height: 40px;
    letter-spacing: -1.5px;
    margin-top: 16px;
}

.questions-list {
    margin: 250px 40px 0 40px;
    display: flex;
    gap: 32px
}

.list1, .list2 {
    width: calc(0.5*(100% - 32px));
}

.qanda {
    overflow: hidden;
}

.question {
    display: flex;
    width: 100%;
    justify-content: space-between;
    padding: 16px;
    align-items: center;
    border-bottom: 2px solid rgba(9, 112, 44, 0.25);
}

.question-text {
    font-size: 30px;
    font-style: normal;
    font-weight: 400;
    line-height: 40px;
    letter-spacing: -1.5px;
}

.arrow-down {
    transition: all 0.5s ease;
    overflow: visible;
}

.arrow-active {
    transition: all 0.5s ease;
    transform: rotate(180deg);
    overflow: visible;
}

.fadeHeight-enter-active, .fadeHeight-leave-active {
  transition: all 0.3s ease-in-out;
}

.fadeHeight-enter-from,
.fadeHeight-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}

.answer {
    padding: 16px;
    max-width: 100%;
}

@media screen and (max-width: 1400px) {
    .question-text {
        font-size: 24px;
        line-height: 1.3em;
    }
}

a {
    color: #09702C;
    font-weight: 600;
}

@media screen and (max-width: 1150px) {
    .question-text {
        font-size: 22px;
    }

    .arrow-down, .arrow-active {
        width: 25px;
    }
}

@media screen and (max-width: 950px) {
    .faq-section {
        margin-block: 200px;
    }

    .questions-list {
        margin-top: 200px;
    }
    .question-text {
        font-size: 20px;
    }

    .arrow-down, .arrow-active {
        width: 20px;
    }
}

@media screen and (max-width: 860px) {
    .faq-section {
        margin-block: 150px;
    }
    .title > :first-child {
        font-size: 140px;
    }

    .title > img {
        width: 60px;
    }
    .questions-list {
        margin-top: 100px;
    }
    .question-text {
        font-size: 18px;
    }

    .arrow-down, .arrow-active {
        width: 18px;
    }
}

@media screen and (max-width: 800px) {
    .faq-section {
        margin-block: 100px;
    }
    .title > :first-child {
        font-size: 120px;
    }

    .title > :last-child {
        font-size: 25px;
    }
    .questions-list {
        display: block;
    }

    .list1, .list2 {
        width: 100%;
    }

    .question-text {
        font-size: 20px;
    }

    .arrow-down, .arrow-active {
        width: 22px;
    }
}

@media screen and (max-width: 500px) {
    .question-text {
        font-size: 20px;
    }

    .arrow-down, .arrow-active {
        width: 18px;
        margin-left: 10px;
    }
}

@media screen and (max-width: 400px) {
    .faq-section {
        margin-block: 75px;
    }

    .title > :first-child {
        font-size: 100px;
    }

    .title > :last-child {
        font-size: 20px;
    }
}

</style>