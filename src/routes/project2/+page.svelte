<script>
  

  import { onMount } from 'svelte';
    // show/hide faq answer
    let isOpen = false;
    let isOpen1 = false;
    let isOpen2 = false;
    let isOpen3 = false;
    let isOpen4 = false;
    let isOpen5 = false;
    let isOpen6 = false;
    let isOpen7 = false;
    let isOpen8 = false;
    let isOpen9 = false;
    
    








  let navClass = '';

  onMount(() => {
    window.addEventListener('scroll', () => {
      navClass = window.scrollY > 0 ? 'window-scroll' : '';
    });
  });




 let navMenu
 let closeBtn
 let openBtn

 function open(){
    navMenu.style.display = "flex"
    closeBtn.style.display = "block"
    openBtn.style.display = "none"
}

 function close(){
    navMenu.style.display = "none"
    closeBtn.style.display = "none"
    openBtn.style.display = "block"
}


import Swiper from 'swiper';
let swiper;

onMount(() => {
    swiper = new Swiper(".mySwiper", {
    slidesPerView: "1",
    spaceBetween: 30,
    pagination: {
        el: ".swiper-pagination",
        clickable: true,
    },
    // WHEN WINDOW WIDTH IS => 600PX
    breakpoints: {
        600: {
            slidesPerView: 2
        }
    }
    });
})

</script>

<style>
    * {
  margin: 0%;
  padding: 0%;
  border: 0%;
  outline: 0;
  text-decoration: none;
  -webkit-box-sizing: border-box;
          box-sizing: border-box;
  list-style: none;
}

body {
  line-height: 1.7;
  color: #fff;
  background-color: #1f2641;
  font-family: sans-serif;
}

.container {
  width: 80%;
  margin: 0 auto;
}

section {
  padding: 6rem 0;
}

section h2 {
  text-align: center;
  margin-bottom: 4rem;
}

h1,
h2,
h3,
h4,
h5 {
  line-height: 1.2;
}

h1 {
  font-size: 2.4rem;
}

h2 {
  font-size: 2rem;
}

h3 {
  font-size: 1.6rem;
}

h4 {
  font-size: 1.3rem;
}

a {
  color: #fff;
}

img {
  width: 100%;
  display: block;
  -o-object-fit: cover;
     object-fit: cover;
}

.btn {
  display: inline-block;
  background-color: #fff;
  color: #000;
  padding: 1rem 2rem;
  border: 1px solid transparent;
  font-weight: 500;
  -webkit-transition: all 400ms ease;
  transition: all 400ms ease;
}

.btn:hover {
  background-color: transparent;
  color: #fff;
  border: #fff;
}

.btn-primary {
  background-color: #f75842;
  color: #fff;
}

.popup-button {
    position: fixed;
    right: 20px;
    bottom: 20px;
    width: 50px;
    height: 50px;
    background-color: #ddd;
    border-radius: 50%;
    box-shadow: 0px 0px 10px #999;
    text-align: center;
    /* transition: all 0.2s ease-in-out; */
    animation: rotate 0.8s infinite;
    z-index: 3;
}
@keyframes rotate {
    from {transform: rotate(0deg);}
    to {transform: rotate(360deg);}
}
/* .popup-button:hover {
    transform: scale(1.1);
    background-color: #ccc;
} */
.popup-button a {
    display: block;
    width: 100%;
    height: 100%;
    line-height: 50px;
    color: #333;
    text-decoration: none;
}
.popup-button a i {
    font-size: 30px;
}

nav {
  background-color: transparent;
  width: 100vw;
  height: 5rem;
  position: fixed;
  top: 0;
  z-index: 11;
}

/* change navbar styles on scroll using javascript*/
.window-scroll {
  background-color: #6c63ff;
  -webkit-box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.2);
          box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.2);
}

.nav__container {
  height: 100%;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
}

.nav__btn {
  display: none;
  border: none;
}

.nav__menu {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  gap: 4rem;
}

.nav__menu a {
  font-size: 0.9rem;
  -webkit-transition: all 400ms ease;
  transition: all 400ms ease;
}

.nav__menu a:hover {
  color: #424890;
}

header {
  position: relative;
  top: 5rem;
  overflow: hidden;
  height: 70vh;
  margin-bottom: 5rem;
}

.header__container {
  display: -ms-grid;
  display: grid;
  -ms-grid-columns: 1fr 1fr;
      grid-template-columns: 1fr 1fr;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  gap: 5rem;
  height: 100%;
}

.header__left p {
  margin: 1rem 0 2.4rem;
}

.categories {
  background-color: #2e3267;
  height: 32rem;
}

.categories h1 {
  line-height: 1;
  margin-bottom: 3rem;
}

.categories__container {
  display: -ms-grid;
  display: grid;
  -ms-grid-columns: 40% 60%;
      grid-template-columns: 40% 60%;
  gap: 4
 1rem;
}

.categories__left {
  margin-right: 3rem;
}

.categories__left p {
  margin: 1rem 0 3rem;
}

.categories__right {
  display: -ms-grid;
  display: grid;
  -ms-grid-columns: (1fr)[3];
      grid-template-columns: repeat(3, 1fr);
  gap: 1.2rem;
}

.category {
  background-color: #424890;
  padding: 2rem;
  border-radius: 2rem;
  -webkit-transition: all 400ms ease;
  transition: all 400ms ease;
}

.category:nth-child(2) .category__icon {
  background-color: #f75842;
}

.category:nth-child(3) .category__icon {
  background-color: #00bf8e;
}

.category:nth-child(4) .category__icon {
  background-color: #f7c94b;
}

.category:nth-child(5) .category__icon {
  background-color: #00bf8e;
}

.category:hover {
  -webkit-box-shadow: 0 3rem 3rem rgba(0, 0, 0, 0.2);
          box-shadow: 0 3rem 3rem rgba(0, 0, 0, 0.2);
  z-index: 1;
}

.category__icon {
  background-color: #6c63ff;
  border-radius: 0.9rem;
  padding: 0.7rem;
}

.category h5 {
  margin: 2rem 0 1rem;
}

.category p {
  font-size: 0.85rem;
}

.courses {
  margin-top: 10rem;
}

.courses__container {
  display: -ms-grid;
  display: grid;
  gap: 2rem;
  -ms-grid-columns: (1fr)[3];
      grid-template-columns: repeat(3, 1fr);
}

.course {
  background-color: #424890;
  border: 1px solid transparent;
  text-align: center;
  -webkit-transition: all 400ms ease;
  transition: all 400ms ease;
}

.course:hover {
  background-color: transparent;
  border-color: #6c63ff;
}

.courses__info {
  padding: 2rem;
}

.courses__info p {
  font-size: 0.9rem;
  margin: 1.2rem 0 2rem;
}

.faq {
  background-color: #2e3267;
  -webkit-box-shadow: inset 0 0 3rem rgba(0, 0, 0, 0.5);
          box-shadow: inset 0 0 3rem rgba(0, 0, 0, 0.5);
}

.faqs__container {
  display: -ms-grid;
  display: grid;
  -ms-grid-columns: 1fr 1fr;
      grid-template-columns: 1fr 1fr;
  gap: 1rem;
}

.faqs {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  padding: 2rem;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  gap: 1.4rem;
  height: -webkit-fit-content;
  height: -moz-fit-content;
  height: fit-content;
  background-color: #6c63ff;
  cursor: pointer;
}

.faqs__icon {
  -ms-flex-item-align: start;
      align-self: flex-start;
  font-size: 1.2rem;
}

.faqs h4 {
  font-size: 1rem;
  line-height: 2.2;
}

.faqs p {
  margin-top: 0.8rem;
  display: none;
}

.faqs.openFaq p {
  display: block;
}


.testimonias__container {
  overflow-x: hidden;
  position: relative;
  margin-bottom: 5rem;
}

.testimonia {
  padding-top: 2rem;
}

.avata {
  height: 6rem;
  width: 6rem;
  margin: 0 auto 1rem;
  border-radius: 50%;
  overflow: hidden;
  border: 1rem solid #2e3267;
}

.testimonia__info {
  text-align: center;
}

.testimonia__body {
  padding: 2rem;
  background-color: #6c63ff;
  margin-top: 3rem;
  position: relative;
}

.testimonia__body::before {
  content: "";
  display: block;
  background: linear-gradient(135deg, transparent, #6c63ff, #6c63ff);
  height: 3rem;
  width: 3rem;
  position: absolute;
  left: 47%;
  top: -1.5rem;
  -webkit-transform: rotate(45deg);
          transform: rotate(45deg);
}

footer {
  background-color: #2e3267;
  padding-top: 5rem;
  font-size: 0.9rem;
}

.footer__container {
  display: -ms-grid;
  display: grid;
  -ms-grid-columns: (1fr)[4];
      grid-template-columns: repeat(4, 1fr);
  gap: 5rem;
}

.footer__container > div h4 {
  margin-bottom: 1.2rem;
}

.footer__01 p {
  margin: 0 0 2rem;
}

footer ul li {
  margin-bottom: 0.7rem;
}

footer ul li:hover {
  text-decoration: underline;
}

.footer__socials {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  gap: 1rem;
  font-size: 1.2rem;
  margin-top: 2rem;
}

.footer__copyright {
  text-align: center;
  margin-top: 4rem;
  padding: 1.2rem 0;
  border-top: 1px solid #424890;
}

@media screen and (max-width: 1024px) {
  h1 {
    font-size: 2.2rem;
  }
  h2 {
    font-size: 1.7rem;
  }
  h3 {
    font-size: 1.4rem;
  }
  h4 {
    font-size: 1.2rem;
  }
  .container {
    width: 90%;
  }
  /*================================ NAVBAR ================================*/
  nav button {
    display: inline-block;
    background: transparent;
    font-size: 1.8rem;
    color: #fff;
    cursor: pointer;
  }
  nav button#close-menu-btn {
    display: none;
  }
  .nav__btn {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  }
  .nav__menu {
    display: none;
    position: fixed;
    top: 5rem;
    right: 5%;
    height: -webkit-fit-content;
    height: -moz-fit-content;
    height: fit-content;
    width: 18rem;
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
        -ms-flex-direction: column;
            flex-direction: column;
    gap: 0;
  }
  .nav__menu li {
    width: 100%;
    height: 5.8rem;
    -webkit-animation: alternateNavItems 400ms linear forwards;
            animation: alternateNavItems 400ms linear forwards;
    -webkit-transform-origin: top right;
            transform-origin: top right;
    opacity: 0;
  }
  .nav__menu li:nth-child(2) {
    -webkit-animation-delay: 200ms;
            animation-delay: 200ms;
  }
  .nav__menu li:nth-child(3) {
    -webkit-animation-delay: 400ms;
            animation-delay: 400ms;
  }
  .nav__menu li:nth-child(4) {
    -webkit-animation-delay: 600ms;
            animation-delay: 600ms;
  }
  @-webkit-keyframes alternateNavItems {
    0% {
      -webkit-transform: rotateZ(-90deg);
              transform: rotateZ(-90deg);
    }
    100% {
      -webkit-transform: rotateZ(0);
              transform: rotateZ(0);
      opacity: 1;
    }
  }
  @keyframes alternateNavItems {
    0% {
      -webkit-transform: rotateZ(-90deg);
              transform: rotateZ(-90deg);
    }
    100% {
      -webkit-transform: rotateZ(0);
              transform: rotateZ(0);
      opacity: 1;
    }
  }
  .nav__menu li a {
    background-color: #6c63ff;
    -webkit-box-shadow: -4rem 6rem 10rem rgba(0, 0, 0, 0.6);
            box-shadow: -4rem 6rem 10rem rgba(0, 0, 0, 0.6);
    width: 100%;
    height: 100%;
    display: -ms-grid;
    display: grid;
    place-items: center;
  }
  .nav__menu li a:hover {
    background-color: #424890;
    color: #fff;
  }
  /* =================================== HEADER ===================================*/
  header {
    height: 52vh;
    margin-bottom: 4rem;
  }
  .header__container {
    gap: 0;
    padding-bottom: 3rem;
  }
  /* =================================== CATEGORIES ===================================*/
  .categories {
    height: auto;
  }
  .categories__container {
    -ms-grid-columns: 1fr;
        grid-template-columns: 1fr;
    gap: 3rem;
  }
  .categories__left {
    margin-right: 0;
  }
  /* =================================== POPULAR COURSES ===================================*/
  .courses {
    margin-top: 0;
  }
  .courses__container {
    -ms-grid-columns: 1fr 1fr;
        grid-template-columns: 1fr 1fr;
  }
  /* =================================== FAQs ===================================*/
  .faqs__container {
    -ms-grid-columns: 1fr;
        grid-template-columns: 1fr;
  }
  .faq {
    padding: 1.5rem;
  }
  /* =================================== FOOTER ===================================*/
  .footer__container {
    -ms-grid-columns: 1fr 1fr;
        grid-template-columns: 1fr 1fr;
  }
}





@media screen and (max-width: 600px) {
  .container {
    width: 94%;
  }
  /*================================ NAVBAR ================================*/
  .nav__menu {
    right: 3rem;
  }
  .nav__btn {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
  }
  /* =================================== HEADER ===================================*/
  header {
    height: 100vh;
  }
  .header__container {
    -ms-grid-columns: 1fr;
        grid-template-columns: 1fr;
    text-align: center;
    margin-top: 0;
  }
  .header__left p {
    margin-bottom: 1.3rem;
  }
  /* =================================== CATEGORIES ===================================*/
  .categories__right {
    -ms-grid-columns: 1fr 1fr;
        grid-template-columns: 1fr 1fr;
    gap: 0.7rem;
  }
  .category {
    padding: 1rem;
    border-radius: 1rem;
  }
  .category__icon {
    margin-top: 4px;
    display: inline-block;
  }
  /* =================================== POPULAR COURSES ===================================*/
  .courses__container {
    -ms-grid-columns: 1fr;
        grid-template-columns: 1fr;
  }
  /* =================================== TESTONIALS ===================================*/
  .testimonia__body {
    padding: 1.2rem;
  }
  /* =================================== FOOTER ===================================*/
  .footer__container {
    -ms-grid-columns: 1fr;
        grid-template-columns: 1fr;
    text-align: center;
    gap: 2rem;
  }
  .footer__01 p {
    margin: 1rem auto;
  }
  .footer__socials {
    -webkit-box-pack: center;
        -ms-flex-pack: center;
            justify-content: center;
  }
}
/*# sourceMappingURL=style.css.map */
</style>



<head>
    <title>Responsive Multipage Education Website Using HTML, CSS & JavaScript</title>
    <!-- ICONSCOUT CDN-->
    <link rel="stylesheet" href="https://unicons.iconscout.com/release/v2.1.6/css/unicons.css">
    <!-- SWIPERJS CDN-->
    <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/swiper@8/swiper-bundle.min.css"
    />
</head>
<body>
    
        <nav class={navClass}>
            <div class="container nav__container">
                <a href="/"><h4>YCMB</h4></a>
                <ul class="nav__menu" bind:this={navMenu}>
                    <li><a href="/">Home</a></li>
                    <li><a href="/">About</a></li>
                    <li><a href="/">Courses</a></li>
                    <li><a href="/">Contact</a></li>
                </ul>
                <button on:click={open} bind:this={openBtn} class="nav__btn" id="open-menu-btn"><i class="uil uil-bars"></i></button>
                <button on:click={close} bind:this={closeBtn} class="nav__btn" id="close-menu-btn"><i class="uil uil-multiply"></i></button>
            </div>
        </nav>
        <!--==================== END OF NAVBAR ===================-->
    
        <header>
            <div class="container header__container">
                <div class="header__left">
                    <h2>Grow Your Skills To Advance Your Career Path</h2>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum cupiditate architecto explicabo, sit accusantium porro doloribus ullam quasi. Possimus, atque?</p>
                    <a href="/" class="btn btn-primary">Get Started</a>
                </div>
                <div class="header__right">
                    <div class="header__right-image">
                        <img src="/header.svg" alt="">
                    </div>
                </div>
                <div class="close_all">
                  <button id="close_all" class="popup-button"><a href="/"><i class="uil uil-multiply"></i></a></button>
                </div>
            </div>
        </header>
        <!--==================== END OF HEADER ===================-->
    
        <section class="categories">
            <div class="container categories__container">
                <div class="categories__left">
                    <h1>Categories</h1>
                    <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Omnis hic iste minus at labore earum dolore, nobis cum temporibus alias inventore, similique voluptate ratione quasi totam quos ipsa ea explicabo?</p>
                    <a href="#" class="btn">Learn More</a>
                </div>
                <div class="categories__right">
                    <article class="category">
                        <span class="category__icon"><i class="uil uil-bitcoin-circle"></i></span>
                        <h5>Blockchain</h5>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, repudiandae?</p>
                    </article>
                    
                    <article class="category">
                        <span class="category__icon"><i class="uil uil-palette"></i></span>
                        <h5>Graphic Design</h5>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, repudiandae?</p>
                    </article>
    
                    <article class="category">
                        <span class="category__icon"><i class="uil uil-usd-circle"></i></span>
                        <h5>Finance</h5>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, repudiandae?</p>
                    </article>
    
                    <article class="category">
                        <span class="category__icon"><i class="uil uil-megaphone"></i></span>
                        <h5>Marketing</h5>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, repudiandae?</p>
                    </article>
    
                    <article class="category">
                        <span class="category__icon"><i class="uil uil-music"></i></span>
                        <h5>Music</h5>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, repudiandae?</p>
                    </article>
    
                    <article class="category">
                        <span class="category__icon"><i class="uil uil-puzzle-piece"></i></span>
                        <h5>Business</h5>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit, repudiandae?</p>
                    </article>
                  
                </div>
            </div>
    
        </section>
        <!--==================== END OF CATEGORIES ===================-->

        <section class="courses">
            <h2>Our Popular Courses</h2>
            <div class="container courses__container">
                <article class="course">
                    <div class="courses__image">
                        <img src="/course1.jpg">
                    </div>
                        <div class="courses__info">
                            <h4>Responsive Social Media Website UI Design</h4>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde, optio. Aut commodi repellat harum sit in.</p>
                        <a href="/courses.html" class="btn btn-primary">Learn More</a>
                        </div>
                </article>
        
                <article class="course">
                    <div class="courses__image">
                        <img src="/course2.jpg">
                    </div>
                    <div class="courses__info">
                        <h4>Responsive SmartHome Website Design</h4>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde, optio. Aut commodi repellat harum sit in.</p>
                        <a href="/courses.html" class="btn btn-primary">Learn More</a>
                    </div>
        
                </article>
        
                <article class="course">
                    <div class="courses__image">
                        <img src="/course3.jpg">
                    </div>
                        <div class="courses__info">
                            <h4>Responsive Admin Dashboard UI Design</h4>
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Unde, optio. Aut commodi repellat harum sit in.</p>
                        <a href="/courses.html" class="btn btn-primary">Learn More</a>
                        </div>
                </article>
           </div>
           </section> 
           <!--==================== END OF COURSES ===================-->
    
           <section class="faq">
            <h2>Frequent Ask Question</h2>
            <div class="container faqs__container">

                      <article class="faqs">
                          <div class="faqs__icon">
                              <i on:click={() => isOpen = !isOpen} class={`uil ${isOpen ? 'uil-minus' : 'uil-plus'}`}></i>
                          </div>
                          
                          <div class="question__answer" class:open={isOpen}>
                              <h4>How do i know the right courses for me</h4>
                              <p style="display: {isOpen ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                  Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                              </p>
                          </div>
                      </article>
                      
                      <article class="faqs">
                        <div class="faqs__icon">
                            <i on:click={() => isOpen1 = !isOpen1} class={`uil ${isOpen1 ? 'uil-minus' : 'uil-plus'}`}></i>
                        </div>
                        <div class="question__answer" class:open={isOpen1}>
                            <h4>How do i know the right courses for me</h4>
                            <p style="display: {isOpen1 ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                            </p>
                        </div>
                      </article>

                      <article class="faqs">
                        <div class="faqs__icon">
                            <i on:click={() => isOpen2 = !isOpen2} class={`uil ${isOpen2 ? 'uil-minus' : 'uil-plus'}`}></i>
                        </div>
                        <div class="question__answer" class:open={isOpen2}>
                            <h4>How do i know the right courses for me</h4>
                            <p style="display: {isOpen2 ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                            </p>
                        </div>
                      </article>

                      <article class="faqs">
                        <div class="faqs__icon">
                            <i on:click={() => isOpen3 = !isOpen3} class={`uil ${isOpen3 ? 'uil-minus' : 'uil-plus'}`}></i>
                        </div>
                        <div class="question__answer" class:open={isOpen3}>
                            <h4>How do i know the right courses for me</h4>
                            <p style="display: {isOpen3 ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                            </p>
                        </div>
                      </article>

                      <article class="faqs">
                        <div class="faqs__icon">
                            <i on:click={() => isOpen4 = !isOpen4} class={`uil ${isOpen4 ? 'uil-minus' : 'uil-plus'}`}></i>
                        </div>
                        <div class="question__answer" class:open={isOpen4}>
                            <h4>How do i know the right courses for me</h4>
                            <p style="display: {isOpen4 ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                            </p>
                        </div>
                      </article>

                      <article class="faqs">
                        <div class="faqs__icon">
                            <i on:click={() => isOpen5 = !isOpen5} class={`uil ${isOpen5 ? 'uil-minus' : 'uil-plus'}`}></i>
                        </div>
                        <div class="question__answer" class:open={isOpen5}>
                            <h4>How do i know the right courses for me</h4>
                            <p style="display: {isOpen5 ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                            </p>
                        </div>
                      </article>

                      <article class="faqs">
                        <div class="faqs__icon">
                            <i on:click={() => isOpen6 = !isOpen6} class={`uil ${isOpen6 ? 'uil-minus' : 'uil-plus'}`}></i>
                        </div>
                        <div class="question__answer" class:open={isOpen6}>
                            <h4>How do i know the right courses for me</h4>
                            <p style="display: {isOpen6 ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                            </p>
                        </div>
                      </article>

                      <article class="faqs">
                        <div class="faqs__icon">
                            <i on:click={() => isOpen7 = !isOpen7} class={`uil ${isOpen7 ? 'uil-minus' : 'uil-plus'}`}></i>
                        </div>
                        <div class="question__answer" class:open={isOpen7}>
                            <h4>How do i know the right courses for me</h4>
                            <p style="display: {isOpen7 ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                            </p>
                        </div>
                      </article>

                      <article class="faqs">
                        <div class="faqs__icon">
                            <i on:click={() => isOpen8 = !isOpen8} class={`uil ${isOpen8 ? 'uil-minus' : 'uil-plus'}`}></i>
                        </div>
                        <div class="question__answer" class:open={isOpen8}>
                            <h4>How do i know the right courses for me</h4>
                            <p style="display: {isOpen8 ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                                Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                            </p>
                        </div>
                    </article>

                    <article class="faqs">
                      <div class="faqs__icon">
                          <i on:click={() => isOpen9 = !isOpen9} class={`uil ${isOpen9 ? 'uil-minus' : 'uil-plus'}`}></i>
                      </div>
                      <div class="question__answer" class:open={isOpen9}>
                          <h4>How do i know the right courses for me</h4>
                          <p style="display: {isOpen9 ? 'block' : 'none'}">Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                              Odit illum deleniti, placeat deserunt maiores maxime quibusdam provident quos. Nisi ratione, error natus ad corporis voluptate facilis illum veritatis molestias laboriosam!
                          </p>
                      </div>
                    </article>
                </div>
           </section>
           <!--==================== END OF FAQs ===================-->
    
           <section class="container testimonias__container mySwiper">
            <h2>Testimonias</h2>
            <div class="swiper-wrapper">
                <article class="testimonia swiper-slide">
                    <div class="avata">
                        <img src="/avatar1.jpg" alt="">
                    </div>
                    <div class="testimonia__info">
                        <h5>Yusuf Adeagbo</h5>
                        <small>Student</small>
                    </div>
                    <div class="testimonia__body">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                           Ratione laudantium vero ex explicabo, maxime voluptatem adipisci aspernatur non molestias magnam recusandae nihil suscipit eos id corrupti dicta commodi! Iusto, molestias.
                        </p>
                    </div>
                </article>
    
                <article class="testimonia swiper-slide">
                    <div class="avata">
                        <img src="/avatar2.jpg" alt="">
                    </div>
                    <div class="testimonia__info">
                        <h5>Michael Johnson</h5>
                        <small>Student</small>
                    </div>
                    <div class="testimonia__body">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                           Ratione laudantium vero ex explicabo, maxime voluptatem adipisci aspernatur non molestias magnam recusandae nihil suscipit eos id corrupti dicta commodi! Iusto, molestias.
                        </p>
                    </div>
                </article>
    
                <article class="testimonia swiper-slide">
                    <div class="avata">
                        <img src="/avatar3.jpg" alt="">
                    </div>
                    <div class="testimonia__info">
                        <h5>John Smith</h5>
                        <small>Student</small>
                    </div>
                    <div class="testimonia__body">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                           Ratione laudantium vero ex explicabo, maxime voluptatem adipisci aspernatur non molestias magnam recusandae nihil suscipit eos id corrupti dicta commodi! Iusto, molestias.
                        </p>
                    </div>
                </article>
    
                <article class="testimonia swiper-slide">
                    <div class="avata">
                        <img src="/avatar4.jpg" alt="">
                    </div>
                    <div class="testimonia__info">
                        <h5>Yusuf Adeagbo</h5>
                        <small>Student</small>
                    </div>
                    <div class="testimonia__body">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                           Ratione laudantium vero ex explicabo, maxime voluptatem adipisci aspernatur non molestias magnam recusandae nihil suscipit eos id corrupti dicta commodi! Iusto, molestias.
                        </p>
                    </div>
                </article>
    
                <article class="testimonia swiper-slide">
                    <div class="avata">
                        <img src="/avatar5.jpg" alt="">
                    </div>
                    <div class="testimonia__info">
                        <h5>Adeagbo Yusuf</h5>
                        <small>Student</small>
                    </div>
                    <div class="testimonia__body">
                        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. 
                           Ratione laudantium vero ex explicabo, maxime voluptatem adipisci aspernatur non molestias magnam recusandae nihil suscipit eos id corrupti dicta commodi! Iusto, molestias.
                        </p>
                    </div>
                </article>
            </div>
            <div class="swiper-pagination"></div>
           </section>
           <!--==================== END OF TESTIMONIA ===================-->
           <footer>
            <div class="container footer__container">
                <div class="footer__01">
                    <h4><a href="/">YCMB</a></h4>
                    <span>Lorem ipsum dolor sit, amet consectetur 
                        adipisicing elit. Harum tenetur ad suscipit?
                    </span>
                </div>
    
                <div class="footer__02">
                <h4>Permalinks</h4>
                <ul class="permalinks">
                    <li><a href="/">Home</a></li>
                    <li><a href="/">About</a></li>
                    <li><a href="/">Courses</a></li>
                    <li><a href="/">Contact</a></li>
                </ul>
                </div>
    
                <div class="footer__03">
                    <h4>Primacy</h4>
                    <ul class="primacy">
                        <li><a href="/">Privacy Policy</a></li>
                        <li><a href="/">Terms and condition</a></li>
                        <li><a href="/">Refund Policy</a></li>
                    </ul>
                </div>
    
                <div class="footer__04">
                    <h4>Contact Us</h4>
                    <div>
                        <p>+234 903 161 7656</p>
                        <p>ycallmeboss@gmail.com</p>
                    </div>
                    <ul class="footer__socials">
                        <li>
                            <a href="/"><i class="uil uil-facebook-f"></i></a>
                        </li>
                        <li>
                            <a href="/"><i class="uil uil-instagram-alt"></i></a>
                        </li>
                        <li>
                            <a href="/"><i class="uil uil-twitter"></i></a>
                        </li>
                        <li>
                            <a href="/"><i class="uil uil-linkedin-alt"></i></a>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="footer__copyright">
                <small>Copyright &copy; YCMB YouTube Tutorials</small>
            </div>
           </footer>
           <!--==================== END OF FOOTER ===================-->
    
</body>