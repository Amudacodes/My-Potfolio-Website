<script>
// window.addEventListener('scroll', () => {
//     document.querySelector('nav').classList.toggle 
//     ('window-scroll', window.scrollY > 0)
// })

import { onMount } from 'svelte';
  let navClass = '';

  onMount(() => {
    window.addEventListener('scroll', () => {
      navClass = window.scrollY > 0 ? 'window-scroll' : '';
    });
  });

 let navMedia
 let closeBtn
 let openBtn

 function open(){
    navMedia.style.display = "flex"
    closeBtn.style.display = "block"
    openBtn.style.display = "none"
}

 function close(){
    navMedia.style.display = "none"
    closeBtn.style.display = "none"
    openBtn.style.display = "block"
}



</script>







<style>
* {
  font-family: Arial, Helvetica, sans-serif;
  margin: 0;
  padding: 0;
  list-style: none;
  outline: none;
  text-decoration: none;
  -webkit-box-sizing: border-box;
          box-sizing: border-box;
}

body {
  background-color: #FBFBFB;
}

.all {
  width: 88%;
  margin: 0 auto;
}

h1,
h2,
h3,
h4,
h5 {
  line-height: 1.2;
}

h1 {
  font-size: 4.5rem;
}

h2 {
  font-size: 2.8rem;
}

h3 {
  font-size: 1.5rem;
}

h4 {
  font-size: 1.1rem;
}

button {
  border: none;
  background: transparent;
}
.logo{
    color: #000000;
}
nav {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  width: 100%;
  position: fixed;
  background: transparent;
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
    z-index: 999;

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


/* change navbar styles on scroll using javascript*/
.window-scroll {
  background-color: white;
  -webkit-box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.2);
          box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.2);
}

.nav_el {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
      -ms-flex-direction: row;
          flex-direction: row;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  height: 4rem;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
  gap: 0.75rem;
}

.nav_form {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
      -ms-flex-direction: row;
          flex-direction: row;
  gap: 2px;
}

.nav_form button {
  font-size: 1.2rem;
}

.nav_form input {
  border: none;
  background: none;
  width: 34%;
}

.nav_media {
  display: none;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  position: absolute;
  right: 7%;
  top: 75%;
  text-align: center;
  width: 12rem;
}

.nav_media a {
  height: 4rem;
  width: 100%;
  color: #000000;
  background: #E5E5E5;
  -webkit-box-shadow: 1rem 1rem 1.5rem rgba(0, 0, 0, 0.6);
          box-shadow: 1rem 1rem 1.5rem rgba(0, 0, 0, 0.6);
  display: -ms-grid;
  display: grid;
  place-items: center;
  -webkit-animation: alternateNavItems 500ms linear forwards;
          animation: alternateNavItems 500ms linear forwards;
  -webkit-transform-origin: top right;
          transform-origin: top right;
  opacity: 0;
}

.nav_media:nth-child(2) {
  -webkit-animation-delay: 200ms;
          animation-delay: 200ms;
}

.nav_media:nth-child(3) {
  -webkit-animation-delay: 400ms;
          animation-delay: 400ms;
}

.nav_media:nth-child(4) {
  -webkit-animation-delay: 600ms;
          animation-delay: 600ms;
}

.nav_media:nth-child(5) {
  -webkit-animation-delay: 800ms;
          animation-delay: 800ms;
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

.nav_media a:hover {
  background-color: #F7FAFC;
  color: black;
}

.nav__btn {
  font-size: 1.8rem;
  cursor: pointer;
}

#close_btn {
  display: none;
}
.header_text1{
    color: #000000;
}
.header_text2{
    color: #000000;
}
header {
  padding-top: 4rem;
}

.header_left {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  padding-top: 1rem;
}

.header_left1 {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  text-align: center;
}

.header_text2 {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
      -ms-flex-direction: row;
          flex-direction: row;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
}

.header_left2 {
  text-align: center;
  padding-top: 5px;
  color: #000000;
}

.header_right {
  display: -ms-grid;
  display: grid;
  place-items: center;
  padding-top: 2rem;
}

.header_right img {
  display: block;
  width: 100%;
  padding-left: 0.5rem;
  padding-right: 0.5rem;
}

.page1-all {
  overflow-x: hidden;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  margin-top: 3rem;
  border: 2px solid #E2E2E2;
}

.page1-text {
  padding-left: 2rem;
  padding-right: 1rem;
  margin-top: 3rem;
}

.page1-text-h3 {
  margin-bottom: 1.5rem;
  color: #2D3748;
}

.page1-text-p1 {
  margin-bottom: 3rem;
  color: #718096;
}

.page1-text-p2 {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
}

.page1-text-p2 p {
  color: #718096;
}

.page1-text-p2 h5 {
  color: #2D3748;
  cursor: pointer;
}

.page1-img img {
  width: 100%;
  height: 100%;
  padding-top: 3rem;
  display: block;
  -o-object-fit: cover;
     object-fit: cover;
}

.page2-all {
  margin-top: 3rem;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  gap: 2rem;
}

.page2-img img {
  width: 100%;
}

.page2-box {
  border: 1px solid #E2E2E2;
}

.page2-text {
  margin-top: 1rem;
  padding-left: 1rem;
  padding-right: 2rem;
}

.page2-text h4 {
  margin-bottom: 1rem;
  color: #2D3748;
}

.page2-text p {
  line-height: 1.4rem;
  color: #718096;
}

.page2-text1 {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
  padding-right: 1rem;
  padding-left: 1rem;
  padding-top: 1.2rem;
  padding-bottom: 1.5rem;
}

.page2-text1 p {
  color: #718096;
}

.page2-text1 h5 {
  color: #2D3748;
}

.about-all {
  margin-top: 2.5rem;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  background-color: #F7FAFC;
  padding-bottom: 1rem;
}

.about-left1 h2 {
  margin-bottom: 2rem;
  font-weight: bold;
  font-size: 2.8rem;
  color: #000000;
}

.about-left1 p {
  margin-bottom: 2rem;
  color: #718096;
}

.about-left2 {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
}

.about-left2 p {
  color: #718096;
}

.about-left2 h5 {
  color: #000000;
}

.about-right img {
  padding-top: 3rem;
  display: block;
  width: 100%;
}

.footer-all {
  padding-top: 2rem;
  padding-bottom: 2rem;
  
}

.footer-btn {
  background-color: #6B46C1;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  padding: 0.8rem;
  border: 1px solid #fff;
  border-radius: 12px;
  gap: 0.5rem;
  position: relative;
  float: right;
}

.footer-btn button {
  background: transparent;
  border: none;
  color: #fff;
}

.footer-btn button h3 {
  font-size: 1rem;
}

.footer-socials {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  -webkit-box-pack: justify;
      -ms-flex-pack: justify;
          justify-content: space-between;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  margin-top: 3rem;
  height: 5rem;
  border-top: 2px solid #E8E8E8;
  gap: 10px;
  
}

.footer-socials-text {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  padding-top: 14px;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  gap: 0.5rem;
  
}

.footer-socials-text h5 {
  font-weight: bold;
}

.footer-socials-link {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  font-size: 1.5rem;
  gap: 5px;
}
.footer-socials-text{
  color: black;
}
.footer-socials-link a {
  color: #000000;
}

@media screen and (min-width: 600px) {
  .nav_media {
    width: 16rem;
  }
  .header_all{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }
  .header_left2 {
    font-size: 1.5rem;
  }
  .header_left1 {
    -webkit-box-align: unset;
        -ms-flex-align: unset;
            align-items: unset;
    text-align: unset;
  }
  .header_left2 {
    text-align: unset;
  }
  .header_right img {
    padding-left: unset;
    padding-right: unset;
  }
  .page1-all {
    display: -ms-grid;
    display: grid;
    -ms-grid-columns: 60% 40%;
        grid-template-columns: 60% 40%;
    margin-top: 3rem;
    border: 2px solid #E2E2E2;
  }
  .page1-img {
    width: 100%;
    height: 100%;
  }
  .page1-img img {
    padding-top: unset;
  }
  .page1-text {
    padding-right: 4rem;
    padding-bottom: 2rem;
  }
  .page2-all {
    margin-top: 5rem;
    display: -ms-grid;
    display: grid;
    -ms-grid-columns: 1fr 1fr;
        grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }
  .about-all {
    display: -ms-grid;
    display: grid;
    -ms-grid-columns: 1fr 1fr;
        grid-template-columns: 1fr 1fr;
    -webkit-box-align: center;
        -ms-flex-align: center;
            align-items: center;
  }
  .about-left {
    padding-right: 3rem;
    padding-left: 1rem;
  }
  .about-right img {
    padding-top: unset;
    -o-object-fit: cover;
       object-fit: cover;
    width: 100%;
    height: 100%;
  }
  .last-btn {
    padding-top: 2rem;
  }
  .footer-socials-text{
        display: flex;
        align-self: center;
    }
    .footer-socials{
        display: flex;
        flex-direction: row;
        align-items: center;
    }
    .footer-socials-link{
      padding-bottom: unset;
    }
}

@media screen and (min-width: 1024px) {
  h2 {
    font-size: 4.5rem;
  }
  .nav_media {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-orient: horizontal;
    -webkit-box-direction: normal;
        -ms-flex-direction: row;
            flex-direction: row;
    position: unset;
    right: unset;
    top: unset;
    text-align: unset;
    width: unset;
    gap: 2rem;
  }
  #open_btn {
    display: none;
  }
  .nav_media a {
    height: unset;
    width: unset;
    font-size: 1.2em;
    color: #000000;
    background: transparent;
    -webkit-box-shadow: unset;
            box-shadow: unset;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    place-items: unset;
    -webkit-animation: unset;
            animation: unset;
    -webkit-transform-origin: unset;
            transform-origin: unset;
    opacity: unset;
  }
  .header_all{
       display: grid;
       grid-template-columns: 60% 40%;
    }
  .page2-all {
    display: -ms-grid;
    display: grid;
    -ms-grid-columns: (1fr)[3];
        grid-template-columns: repeat(3, 1fr);
    gap: 2rem;
  }
}

</style>




<head>
    <!-- ICONSCOUT CDN-->
    <link rel="stylesheet" href="https://unicons.iconscout.com/release/v2.1.6/css/unicons.css">
    <title>coffee website</title>
</head>
<body>
  <nav class={navClass}>
      <div class="nav_el all">
          <div class="logo"><h4>HotCoffee</h4></div>
          <form class="nav_form">
              <button type="submit"><i class="uil uil-search"></i></button>
              <input type="text" placeholder="Search...">
          </form>
          <div class="nav_media" bind:this={navMedia}>
              <a href="#" id="home"><h5>Home</h5></a>
              <a href="/page1.html" id="articles"><h5>Articles</h5></a>
              <a href="#" id="instagram"><i class="uil uil-instagram-alt"></i></a>
              <a href="#" id="twitter"><i class="uil uil-twitter"></i></a>
              <a href="#" id="linkedin"><i class="uil uil-linkedin"></i></a>
          </div>
          <button on:click={open} bind:this={openBtn} class="nav__btn" id="open_btn"><i class="uil uil-bars"></i></button>
          <button on:click={close} bind:this={closeBtn} class="nav__btn" id="close_btn"><i class="uil uil-multiply"></i></button>
      </div>
  </nav>
  <!--==================== END OF NAVBAR ===================-->

  <header>
      <div class="header_all all">
          <div class="header_left">
              <div class="header_left1">
                  <div class="header_text1">
                      <h2>Make better</h2>
                  </div> 
                  <div class="header_text2">
                      <h2>coffee</h2>
                      <img src="/image 6.png" alt="">
                  </div>
              </div>
              <div class="header_left2"><p> why learn how to blog?</p></div>
          </div>
          <div class="header_right">
              <img src="/croods 1.png" alt="">
          </div>
          <div class="close_all">
            <button id="close_all" class="popup-button"><a href="/"><i class="uil uil-multiply"></i></a></button>
          </div>
      </div>
  </header>
  <!--==================== END OF HEADER ===================-->

  <section class="page1">
      <div class="page1-all all">
          <article class="page1-text">
              <div class="page1-text-h3"><h3>long established</h3></div>
              <div class="page1-text-p1">
                  <p>
                      It is a long established fact that a reader 
                      will be distracted by the readable 
                      content of a page when looking at its layout. 
                      The point of using Lorem Ipsum is that...
                  .</p>
              </div>
              <div class="page1-text-p2">
                  <p>May 20th 2023</p>
                  <a href="/page1.html"><h5>Read more</h5></a>
              </div>
          </article>  
          <div class="page1-img">
              <img src="/image 1.png" alt="">
          </div>
      </div>
  </section>
  <!--==================== END OF PAGE1 ===================-->

  <section class="page2">
      <div class="page2-all all">
          <article class="page2-box">
              <div class="page2-img"><img src="/image 2.png" alt=""></div>
              <div class="page2-text">
                  <h4>long established</h4>
                  <p>
                      It is a long established fact that a 
                      reader will be distracted by the readable
                      content of a page when looking at its layout. 
                      The point of using Lorem Ipsum is that....
                  </p>
              </div>
              <div class="page2-text1">
                  <p>May 20th 2023</p>
                  <h5>Read more</h5>
              </div>
          </article>

          <article class="page2-box">
              <div class="page2-img"><img src="/image 4.png" alt=""></div>
              <div class="page2-text">
                  <h4>long established</h4>
                  <p>
                      It is a long established fact that a 
                      reader will be distracted by the readable
                      content of a page when looking at its layout. 
                      The point of using Lorem Ipsum is that....
                  </p>
              </div>
              <div class="page2-text1">
                  <p>May 20th 2023</p>
                  <h5>Read more</h5>
              </div>
          </article>

          <article class="page2-box">
              <div class="page2-img"><img src="/image 5.png" alt=""></div>
              <div class="page2-text">
                  <h4>long established</h4>
                  <p>
                      It is a long established fact that a 
                      reader will be distracted by the readable
                      content of a page when looking at its layout. 
                      The point of using Lorem Ipsum is that....
                  </p>
              </div>
              <div class="page2-text1">
                  <p>May 20th 2023</p>
                  <h5>Read more</h5>
              </div>
          </article>
      </div>
  </section>
  <!--==================== END OF PAGE2 ===================-->

  <section class="about">
      <div class="about-all all">
          <article class="about-left">
              <div class="about-left1">
                  <h2>What is Lorem Ipsum?</h2>
                  <p>
                      It is a long established fact that a reader will 
                      be distracted by the readable 
                      content of a page when looking at its layout. 
                      The point of using Lorem Ipsum is that 
                      it has a more-or-less normal distribution...
                  </p>
              </div>
              <div class="about-left2">
                  <p>May 20th 2023</p>
                  <h5>Read more</h5>
              </div>
          </article>
          <div class="about-right">
              <img src="/image 7.png" alt="">
          </div>     
      </div>
  </section>
  <!--==================== END OF ABOUT ===================-->

  <div class="last-btn all">
      <div class="footer-btn">
          <button><h3>See more</h3></button>
          <img src="/Vector (34).png" alt="">
      </div>
 </div>

  <footer>
      <div class="footer-all all">
      <div class="footer-socials">
          <div class="footer-socials-text">
              <h4>hotcoffee</h4>
              <small> 2023 Copyright &copy; all rights reserved</small>
          </div>
          <div class="footer-socials-link">
              <a href="#" id="instagram"><i class="uil uil-instagram-alt"></i></a>
              <a href="#" id="twitter"><i class="uil uil-twitter"></i></a>
              <a href="#" id="linkedin"><i class="uil uil-linkedin"></i></a>
          </div>
      </div>
      </div>
  </footer>
</body>
