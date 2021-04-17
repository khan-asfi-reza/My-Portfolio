<script lang="ts">
    import {onMount} from "svelte";

    export let navBg;

    let navOpen = false;
    const setNavOpen = () => {
        navOpen = !navOpen
    };

    onMount(()=>{
        const isInViewport = function (el) {
            const scrollPosition = document.documentElement.scrollTop;

            return  scrollPosition >= el.offsetTop - el.offsetHeight * 0.25 &&
                    scrollPosition <
                    el.offsetTop + el.offsetHeight - el.offsetHeight * 0.25
        };


        const navTags = document.querySelectorAll(".nav__menu__ul__item__a");
        const sections = document.querySelectorAll(".section");

        const onViewPort = (element, callback) => {
            window.addEventListener('scroll', function(event) {
                // add event on scroll
                if (isInViewport(element)) {
                    //if in Viewport
                    callback()
                }

            }, false);
        };


        const removeActiveClasses = () => {
            navTags.forEach((each)=>{
                each.classList.remove("active")
            })
        };

        const addActiveClass = (id) => {
            const selector = `.nav__menu__ul__item a[href="#${id}"]`;
            document.querySelector(selector).classList.add("active");
        };

        sections.forEach((eachSection) => {
            onViewPort(eachSection, ()=>{
                removeActiveClasses();
                addActiveClass(eachSection.attributes.id.value)
            })
        });
    })


</script>



<nav class="nav {navBg && 'nav__bg__dark'}" aria-label="Navigation Bar">
    <div class="d__flex container nav__div">
        <div class={"flex-1 align__item__center"} aria-label={"Logo Bar"}>
            <div class="image-container nav__image__box">
                <img src="/Assets/Main.png" alt="Khan Asfi Reza Logo" aria-label={"Logo"} aria-describedby={"Logo"}/>
            </div>
        </div>
        <div class="flex-4 nav__menu {navOpen && 'nav__menu__open'}">
            <ul class="d__flex flex__end nav__menu__ul" aria-label={"menubar"}>
                <li class="nav__menu__ul__item" aria-label="menuitem">
                    <span class="hover__line"></span>
                    <a class="nav__menu__ul__item__a" on:click={setNavOpen} href="#home">Home</a>
                </li>
                <li class="nav__menu__ul__item" aria-label="menuitem">
                    <span class="hover__line"></span>
                    <a class="nav__menu__ul__item__a" on:click={setNavOpen} href="#about">About</a>
                </li>
                <li class="nav__menu__ul__item" aria-label="menuitem">
                    <span class="hover__line"></span>
                    <a class="nav__menu__ul__item__a" on:click={setNavOpen} href="#skill">Skill</a>
                </li>
                <li class="nav__menu__ul__item" aria-label="menuitem">
                    <span class="hover__line"></span>
                    <a class="nav__menu__ul__item__a" on:click={setNavOpen} href="#project">Project</a>
                </li>
                <li class="nav__menu__ul__item" aria-label="menuitem">
                    <span class="hover__line"></span>
                    <a class="nav__menu__ul__item__a" on:click={setNavOpen} href="#contact">Contact</a>
                </li>
            </ul>
        </div>
        <div class="nav__expand__div flex-1 d__flex flex__end align__item__center m-0 p-0">
            <button on:click={setNavOpen} class="nav__expand__div__button m-0 p-0 {navOpen && 'nav__expand__div__button_close'}">
                {#each [1,2,3] as elem}
                <span class="line" id={"elem-"+elem}></span>
                {/each}
            </button>
        </div>
    </div>
</nav>

