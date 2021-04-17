<script>
    let TxtRotate = function(el, toRotate, period) {
        this.toRotate = toRotate;
        this.el = el;
        this.loopNum = 0;
        this.period = parseInt(period, 10) || 2000;
        this.txt = '';
        this.tick();
        this.isDeleting = false;
    };

    TxtRotate.prototype.tick = function() {
        let i = this.loopNum % this.toRotate.length;
        let fullTxt = this.toRotate[i];

        if (this.isDeleting) {
            this.txt = fullTxt.substring(0, this.txt.length - 1);
        } else {
            this.txt = fullTxt.substring(0, this.txt.length + 1);
        }

        this.el.innerHTML = '<span class="wrap">'+this.txt+'</span>';

        let that = this;
        let delta = 300 - Math.random() * 100;

        if (this.isDeleting) { delta /= 2; }

        if (!this.isDeleting && this.txt === fullTxt) {
            delta = this.period;
            this.isDeleting = true;
        } else if (this.isDeleting && this.txt === '') {
            this.isDeleting = false;
            this.loopNum++;
            delta = 500;
        }

        setTimeout(function() {
            that.tick();
        }, delta);
    };





    window.onload = function() {
        let elements = document.getElementsByClassName('txt-rotate');
        for (let i=0; i<elements.length; i++) {
            let toRotate = elements[i].getAttribute('data-rotate');
            let period = elements[i].getAttribute('data-period');
            if (toRotate) {
                new TxtRotate(elements[i], JSON.parse(toRotate), period);
            }
        }
        // INJECT CSS
        let css = document.createElement("style");
        css.type = "text/css";
        css.innerHTML = ".txt-rotate > .wrap { border-right: 0.08em solid #666 }";
        document.body.appendChild(css);
    };

    const buttonOnClick = () => {
        document.getElementById("about").scrollIntoView();
    }

</script>



<section id="home" class="section d__flex container mobile-flex-column home">
    <div class="flex-1 mobile-order-2 home__text__box">
        <h2>
            Hi, I'm
        </h2>
        <div class="glitch-wrapper">
            <h1 class="glitch" data-text={"KHAN ASFI REZA"}>
                KHAN ASFI REZA
            </h1>
        </div>
        <p>
            I'm a {"<"}
            <span class="txt-rotate" data-period="2000" data-rotate='[ "Full-Stack Web Developer", "Full-Stack Engineer", "Programmer", "Tech Enthusiast"]'></span> {"/>"}
        </p>
        <button on:click={buttonOnClick} class="home__text__box__button">
            Learn More
            <span class="red__bg">
            </span>
        </button>
    </div>
    <div class="flex-1 mobile-order-1 home__image__box">
        <div class="image-container home__image__box__container">
            <img src="Assets/HomeSection.png" alt="Khan Asfi Reza Cartoon Art"/>
        </div>
        <div class="home__image__box__circle">

        </div>
    </div>
</section>

