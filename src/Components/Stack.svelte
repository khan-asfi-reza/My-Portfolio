<script>

    let current = 0;

    const changeCurrent = (e) => {
        current = parseInt(e.target.value);
    };

    const stacks = [
        {
            logo: 'Assets/backend.png',
            title: "Back-end Development",
            text: "I am quite good with backend development I have worked with backend frameworks like Django, Flask, Express, Ruby On Rails I have made Chat based App, Social Media App etc\n"
        },
        {
            logo: 'Assets/frontend.png',
            title: "Front-end Development",
            text: "I can built front-end website using several frontend frameworks and UI Component Library. I have expertise in React, Svelte, VueJs etc and also used ant.design and material ui "
        },
        {
            logo: 'Assets/fullstack.png',
            title: "Full-stack Development",
            text: "I can build full-stack application using Django, Flask, Ruby On Rails, MERN Stack. I have created several full stack application, including a Social Media Website, A Chat API Website etc"
        }
    ];

</script>

<section class="expertise bg__content">
    <div class="container p-t-c pb__10">
        <div>

            <h2 class="red-header">My Expertise</h2>
            <div class="mt-1 d__flex justify__space__between align__end mobile-flex-column">
                <div class="d__grid stack__grid flex-1 mb_my_2">
                    <div class=" d__in_block mb_text_center">
                        <h3 class="text__hc or__text project__number">10+</h3>
                        <h3 class="text__hc or__text project__number">Languages</h3>
                    </div>
                    <div class=" d__in_block  mb_text_center">
                        <h3 class="text__hc or__text project__number">15+</h3>
                        <h3 class="text__hc or__text project__number">Projects</h3>
                    </div>
                    <div class=" d__in_block mr_1 mb_text_center">
                        <h3 class="text__hc or__text project__number">10+</h3>
                        <h3 class="text__hc or__text project__number">Clients</h3>
                    </div>
                </div>
                <div class="flex-1 project__box__text mb_my_2">
                    <div class="d__flex">
                        <button on:click={changeCurrent} value="0" class="flex-1 mr_1 expertise__button {current === 0 && 'active'}">Back-end</button>
                        <button on:click={changeCurrent} value="1" class="flex-1 mr_1 expertise__button {current === 1 && 'active'}">Front-end</button>
                        <button on:click={changeCurrent} value="2" class="flex-1 expertise__button {current === 2 && 'active'}">Full-stack</button>
                    </div>
                    <div class="mt_2">
                        <p class="white-text">{stacks[current].text}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

