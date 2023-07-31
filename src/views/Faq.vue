<template>
    <section class="faq-section">
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
                    <div v-if="qa.question == currentQuestion" class="answer">{{ qa.answer }}</div>
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
                    "answer": "answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1 answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1answer1"
                },
                {
                    "question": "Do I apply with a team?",
                    "answer": "answer2"
                },
                {
                    "question": "How many people can be on one team?",
                    "answer": "answer3"
                },
            ],
            questions2: [
                {
                    "question": "When will registration begin?",
                    "answer": "answer4"
                },
                {
                    "question": "What if I want to join virtually?",
                    "answer": "answer5"
                },
                {
                    "question": "404 Question not found",
                    "answer": "answer6"
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
    margin: 250px 65px 0 65px;
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
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;    
}

@media screen and (max-width: 1400px) {
    .question-text {
        font-size: 24px;
        line-height: 1.3em;
    }
}

@media screen and (max-width: 1150px) {
    .question-text {
        font-size: 20px;
    }

    .arrow-down, .arrow-active {
        width: 25px;
    }
}

@media screen and (max-width: 1000px) {
    .faq-section {
        margin-block: 200px;
    }

    .questions-list {
        margin-top: 200px;
    }
    .question-text {
        font-size: 18px;
    }

    .arrow-down, .arrow-active {
        width: 20px;
    }
}

@media screen and (max-width: 900px) {
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
        font-size: 16px;
    }

    .arrow-down, .arrow-active {
        width: 18px;
    }
}

@media screen and (max-width: 775px) {
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
        font-size: 16px;
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

    .questions-list {
        margin: 60px 20px 0 20px;
    }
}

</style>