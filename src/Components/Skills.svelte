<script>
    import Glide from '@glidejs/glide'
    import {onMount} from "svelte";
    const skills = [
        "Assets/python.png",
        "Assets/ts.png",
        "Assets/django.png",
        "Assets/react.png",
        "Assets/js.png",
        "Assets/java.png",
        "Assets/vue.png",
        "Assets/redux.png",
        "Assets/css.png",
        "Assets/ds.png",
        "Assets/html.png"
    ];

    onMount(()=>{
        new Glide('.skill__glide', {
            type: 'carousel',
            startAt: 0,
            perView: 7,
            autoplay: 2000,
            breakpoints:{
                768:{
                    perView: 6
                },
                625:{
                    perView: 4
                },

            }
        }).mount()
    })


</script>


<section id="skill" class="section about container  m-t-c">
    <div class="d__grid mb__g__fr1 mb_gr_gap">
        <div class="center-0 image g_col_1 g_row_1_2 mb_g_col_1 mb_g_row_2">
            <div class="image-container ic-80 mr-auto mb-mx-auto">
                <img src="Assets/MoreSkill.png" alt="">
            </div>
        </div>
        <div class="header g_col_2 g_row_1 mb_g_col_1 mb_g_row_1">
            <h2 class="red-header">My Skills</h2>
        </div>
        <div class="g_col_2 g_row_2 mb_g_col_1 mb_g_row_3">
            <p class="white-text">
                Learning to code since the age 13. Started my programming journey with Python, later Java and JavaScript. In past few years, learned more about web development. Learned a couple of backend and frontend frameworks, including Django and React
            </p>
        </div>
    </div>
    <div class="d__flex flex__row justify__space__between my-2">
        <div class="glide skill__glide">
            <div class="glide__track" data-glide-el="track">
                <ul class="glide__slides">
                    {#each skills as skill}
                        <li class="glide__slide">
                            <div class="round-icon-container bg__white center-0 or__border bg__round__icon">
                                <img src="{skill}" alt="">
                            </div>
                        </li>
                    {/each}
                </ul>
            </div>
        </div>
    </div>

</section>