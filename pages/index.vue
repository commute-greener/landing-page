<script setup>

    const wrapper = ref(null);
    const screenSize = ref(undefined);
    const cards = [
        { iconName: "fa-solid:car-side", text:"COMMUTE integrates ride-sharing seamlessly into your day-to-day life. Wether you're going to work or visiting friends on the other side of town: with COMMUTE, sharing rides is as easy and fast as calling an Uber." },
        { iconName: "mdi:leaf", text:"It doesn't matter wether you're the driver or one of the passengers: Sharing rides means splitting up your CO2-emissions and substantially reducing the negative impact of cars on our climate." },
        { iconName: "healthicons:money-bag", text:"Ride Sharing is a Win-Win for all! As a driver, what you earn will help you cover the costs of owning a car. As a passenger, you get to enjoy the benefits of moving fast from A to B, at a really low fare." },
        { iconName: "mingcute:traffic-lights-line", text:"Sharing our cars more efficiently means less cars on our streets. This not only reduces traffic congestion, but also improves the safety of streets and overall livability of your city." }
    ]

    onMounted(() => {
        screenSize.value = getComputedStyle(wrapper.value, '::after').content.replace(/\"/g, '');
        console.log(screenSize.value === "s")

        window.onresize = () => {
            screenSize.value = getComputedStyle(wrapper.value, '::after').content.replace(/\"/g, '');
        }
    })

    onBeforeUnmount(() => {
        window.onresize = null;
    })

</script>

<template>
    <div ref="wrapper" class="wrapper">
        <NavBar />
        <SectionComponent 
            id="section1"
            :title="'COMMUTE'"
            :body="'Day-to-Day Ride-sharing made easy.'"
            :color="'var(--color-dark)'"
            :textColor="'var(--color-white)'"
        >
            <RoadAnimation />
            <PhoneElementComponent />
        </SectionComponent>
        <SectionComponent
            id="section2"
            :title="'What is it?'"
            :color="'var(--color-light-green)'"
            :textColor="'var(--color-dark)'"
        >
            <div class="city-wrapper">
                <swiper
                    class="swiper-cards"
                    :space-between="50"
                    :slides-per-view="1"
                    :loop="true"
                    :autoplay="{
                        delay: 3000,
                        disableOnInteraction: true
                    }"
                >   
                    <swiper-slide v-for="card in cards">
                        <Card :iconName="card.iconName" :text="card.text"/>
                    </swiper-slide>
                    <div class="swiper-pagination">
                        <span class="pagination-bullet" v-for="(card, index) in cards" @click="console.log(card)"></span>
                    </div>
                </swiper>
                <div class="city-wrapper">
                    <TinyCityComponent />
                </div>
            </div>
        </SectionComponent>
        <SectionComponent
            id="section3"
            :title="'Get in touch!'"
            :body="'We are also launching a newsletter! If you want to know all about environmental news, it is one click away!'"
            :color="'var(--color-dark)'"
            :textColor="'var(--color-white)'"
        >
            <img class="img" src="/traffic-jam.png" alt="Cars stuck in traffic">
            <RegisterForm />
        </SectionComponent>
        <footer id="section4">
            <FooterComp />
        </footer>
    </div>
</template> 

<style scoped>

    .wrapper {
        width: 100%;
    }

    .city-wrapper {
        margin-top: 5svh;
        height: 110vh;
        gap: 5svh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .img {
        padding-left: 15px;
        width: 100%;
        height: auto;
    }

    .card-preview {
        height: 200px;
        width: 10px;
    }

    .city-wrapper {
        position: relative;
        width: 100%;
        display: flex;
        justify-content: center;
    }

    .wrapper::after {
        content: 'l';
        display: none;
        visibility: hidden;
    }

    .swiper {
        width: 100%;
        height: 110%;
        display: flex;
        justify-content: space-evenly;
    }

    .swiper-slide {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .swiper-pagination {
        display: flex;
        justify-content: center;
        align-items: center;
        color: transparent;
        gap: 8px;
        bottom: 2svh;
    }

    .pagination-bullet {
        display: flex;
        justify-content: center;
        align-items: center;
        opacity: 1;
        border-radius: 50%;
        width: 16px;
        height: 16px;
        background-color: var(--color-dark);
    }

    .swiper-pagination-bullet-active {
        background-color: black;
    }

    @media only screen and (max-width: 768px) {
        .wrapper::after {
            content: 's';
        }
    }

</style>