<script>
    import Glide from '@glidejs/glide'
    import {onMount} from "svelte";

    const projects = [
        {
            image: "Assets/chatapi.png",
            title: "Django Chat Application",
            text: "A minimalistic chat based web application built with Django, Django Rest Framework, Django Channels, VueJS",
            link:"https://django-chat-api.herokuapp.com/"
        },
        {
            image: "Assets/medic.png",
            title: "Disease Symptom Checker",
            text: "Disease Finder using patient's symptoms, This application can detect user's disease by their symptom",
            link:"https://khan-asfi-reza.github.io/SympomChecker/"
        },
        {
            image: "Assets/home.PNG",
            title: "Tech Mountain Website",
            text: "A Technology company website using Pure HTML, CSS, JavaScript",
            link:"https://www.khanasfireza.cf/"
        },
        {
            image: "Assets/accitc2.PNG",
            title: "A Club Website",
            text: "A club's landing website and internal club member's management website using django, pure html, css",
            link:"https://accitclub.ml/"
        },
        {
            image: "Assets/wp.PNG",
            title: "Portfolio Website",
            text: "A Portfolio website using WordPress",
            link:"https://khan-asfi-reza.github.io/portfolio/"
        },
        {
            image: "Assets/invasso.png",
            title: "Invasso LLC Website",
            text: "Invasso LLC Portfolio website built with Django",
            link:"https://invasso.com"
        },
        {
            image: "Assets/ecom.png",
            title: "E-Commerce Website",
            text: "A E-Commerce Website",
            link:"https://store.nafis.xyz"
        }

    ];

    onMount(()=>{
        new Glide('.project__glide', {
            type: 'carousel',
            startAt: 0,
            perView: 3,
            autoplay: 4000,
            breakpoints:{
                868:{
                    perView:2,
                },
                525:{
                    perView:1,
                }
            }
        }).mount()
    })
</script>





<section id="project" class="section projects container m-t-c">
    <h2 class="red-header">My Projects</h2>
    <div class="glide project__glide">
        <div class="glide__track" data-glide-el="track">
            <ul class="glide__slides">
                {#each projects as {image, title, text, link}}
                    <li class="glide__slide">
                        <div class="project glass">
                            <div class="project__container">
                                <div class="image-container">
                                    <img src={image} alt="">
                                </div>
                                <p class="white-text">{title}</p>
                            </div>
                            <div class="shadow__container center-0">
                                <div>
                                    <h3 class="text__hc">{title}</h3>
                                    <p class="white-text">{text}</p>
                                    <a target="_blank" href="{link}">Visit Website</a>
                                </div>
                            </div>
                        </div>
                    </li>
                {/each}
            </ul>
        </div>
    </div>
</section>