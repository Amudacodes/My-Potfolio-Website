<script>
import { onMount } from 'svelte';

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
        navMenu.style.display = "flex";
        closeBtn.style.display = "block";
        openBtn.style.display = "none";
    }

    function close(){
        navMenu.style.display = "none";
        closeBtn.style.display = "none";
        openBtn.style.display = "block";
    }
    
    let text = [    "Hi, my name is",    "Yusuf Adeagbo.",    "I am a frontend developer.",    "I specialize in creating user-friendly and visually appealing websites and web applications using technologies such as HTML, CSS, and JavaScript."];

    let typing = [];
    text.forEach(() => typing.push(""));

    function typeWriter(sentenceIndex, index) {
      if (index < text[sentenceIndex].length) {
        typing[sentenceIndex] += text[sentenceIndex][index];
        setTimeout(() => typeWriter(sentenceIndex, index + 1), 100);
      } else {
        if (sentenceIndex + 1 < text.length) {
          setTimeout(() => typeWriter(sentenceIndex + 1, 0), 100);
        }
      }
    }

    typeWriter(0, 0);

    let name = '';
    let email = '';
    let message = '';
</script>


<style>

    :root {
    --dark-navy: hsl(216, 86%, 6%);
    --navy: #020d1d;
    --light-navy: #112240;
    --lightest-navy: #233554;
    --navy-shadow: rgba(2,12,27,0.7);
    --dark-slate: #495670;
    --slate: #8892b0;
    --light-slate: #a8b2d1;
    --lightest-slate: #ccd6f6;
    --white: #e6f1ff;
    --green: #64ffda;
    --green-tint: rgba(100,255,218,0.1);
    --blue: #57cbff;
}
*{
    margin: 0;
    padding: 0;
    list-style: none;
    outline: none;
    box-sizing: border-box;
    text-decoration: none;
    font-family: Arial, Helvetica, sans-serif;
}
body{
    background-color: var(--navy);
    scroll-behavior: smooth;
    color: white;
}
.all{
    width: 90%;
    margin: 0 auto;
}
h1,
h2,
h3,
h4,
h5{
    line-height: 1.2;
}
p{
    line-height: 1.4rem;
}
button{
    color: white;
    font-size: 2.4rem;
}
/*===================NAVBAR===================*/

.logo img{
    border-radius: 50%;
    width: 25%;
} 
.window-scroll {
  background-color: var(--light-navy);
  box-shadow: 0 1rem 2rem rgba(5, 29, 65, 0.7);
}
nav{
    z-index: 999;
    position: fixed;
    width: 100%;
    height: 5rem;
    background-color: var(--light-navy);
}
.nav_el{
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100%;
    
  
  }
  .nav_menu {
    z-index: 1;
    display: none;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
    padding: 50px 10px;
    width: min(75vw, 400px);
    height: 100vh;
    animation: slideInFromLeft 700ms ;
    background-color: var(--light-navy);
  }

  @keyframes slideInFromLeft {
    from { transform: translateX(-100%); }
    to { transform: translateX(0); }
}
@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
.nav__menu1{
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 5.65rem;
    animation: fadeIn 1s;
    animation-delay: 0.8s;
}
.nav__menu1 p{
    color: var(--green);
    padding-bottom: 5px;
}
.nav__menu1 a{
    font-size: 1.3rem;
    color: var(--light-slate);
}
.nav__menu1 a:hover{
    color: var(--green);
}

.resume{
    align-self: center;
    border-radius: 10px;
    border: 1px solid var(--green);
    padding: 16px 3rem;
}
.resume a{
    color: var(--green);
}
.resume:hover{
    border: 1px solid var(--slate);
  }
  .resume a:hover{
    color: var(--slate);
  }
.nav_btn {
    background: transparent;
    border: none;
    cursor: pointer;
    color: var(--green);
  }
  #open_btn{
    display: flex;
  }
  #close_btn{
    display: none;
    position: fixed;
    top: 1.8%;
    right: 4.8%;
    z-index: 1;
  }

/*===================HEADER===================*/
.unknown{
  height: 5rem; 
  background-color: var(--light-navy);
}
.header_el{
    padding-top: 20px;
    padding-bottom: 9rem;
}
.header_me{
    color: var(--green);
    padding-top: 4rem;
    padding-bottom: 25px;
    word-spacing: 5px;
    
}
.header_name{
    color: var(--lightest-slate);
    padding-bottom: 10px;
    font-size: 2rem;
}
.header_about{
    color: var(--slate);
    padding-bottom: 10px;
    line-height: 3rem;
    font-size: 2.3rem;
}
.header_aboutp{
    color: var(--slate);
    padding-bottom: 3em;
    font-size: 1rem;
}
.header_img2{
    display: none;
  }
.header_btn{
    background: transparent;
    border: 1px solid var(--green);
    font-size: 20px;
    padding: 1rem;
    cursor: pointer;
}
.header_btn a{
    color: var(--green);
}
.header_btn:hover{
  border: 1px solid var(--light-slate);
}
.header_btn a:hover{
    color: var(--slate);
}
/*===================ABOUT===================*/

.about_el {
    animation: slideInFromLeft 1s;
}

.about_head{
    display: flex;
    align-items: center;
    gap: 10px;
}
.about_head h3{
    color: var(--green);
}
.about_head:after {
    content: "";
    width: 100%;
    height: 1px;
    background-color:var(--slate);
}
.about_abt{
    padding-top: 3rem;
    color: var(--slate);
}
/*===================EXPERIENCE===================*/
.experience_head{
    display: flex;
    align-items: center;
    gap: 10px;
    padding-top: 6rem;
}
.experience_head h3{
    color: var(--green);
}
.experience_head h2 {
    white-space: nowrap;
}
.experience_head:after {
    content: "";
    width: 100%;
    height: 1px;
    background-color:var(--slate);
}
.experience_abt{
    padding-top: 3rem;
    color: var(--slate);
}
.experience_subhead{
    padding-top: 2rem;
    padding-bottom: 10px;
    border-bottom: 1px solid var(--slate);
    color: var(--green);
    font-weight: bold;
}
/*===================WORK===================*/
.work_head{
    display: flex;
    align-items: center;
    gap: 10px;
    padding-top: 5rem;
}
.work_head h3{
    color: var(--green);
}
.work_all{
    background-color: var(--light-navy);
    border: 1px solid var(--green);
    margin-bottom: 2rem;
    margin-top: 3rem;
}
.work_all:hover{
    background-color: transparent;
    border: 1px solid var(--slate);
}
.work_all-abt{
    text-align: center;
    gap: 2rem;
    color: var(--slate);
}
.work_all-abt h4{
    padding-top: 2rem;
    padding-bottom: 2rem;
    font-size: 1.4rem;
}
.work_all-abt p{
    padding-bottom: 3rem;
}
.gradient-image {
    filter: brightness(50%) grayscale(100%);
    transition: filter 0.3s ease;
}

.gradient-image:hover {
    filter: brightness(100%) grayscale(0%);
}
img{
    width: 100%;
    background-size: contain;
    display: block;
}
.work_all-abt{
  color: var(--slate);
  padding-left: 5px;
  padding-right: 5px;
}
.work_all-abt a{
  color: white;
}
/*===================CONTACT===================*/
.contact{
    padding-top: 6rem;
    padding-bottom: 6rem;
      /* The image used */
  background: linear-gradient(to right, #112240c0, #112240c0), url("/mmm.png");

/* Set a specific height */
min-height: 500px;

/* Create the parallax scrolling effect */
background-attachment: fixed;
background-position: center;
background-repeat: no-repeat;
background-size: cover;
}


.contact_head1{
    text-align: center;
    color: var(--green);
    padding-bottom: 1rem;
    font-weight: bold;
    font-size: 1rem;
}
.contact_head2{
    text-align: center;
    padding-bottom: 10px;
    font-size:1.8rem;
    font-weight: bold;
}
.contact_headp{
    text-align: center;
    color: var(--slate);
    padding-left: 3.5rem;
    padding-right: 3.5rem;
    padding-bottom: 3rem;
    font-weight: bold;
    font-size: 1rem;
}

form {
  
  width: 400px;
  margin: 0 auto;
  padding: 20px;
  background-color: #f5f5f5;
  margin-bottom: 2rem;
  border: 1px solid var(--green);
  border-radius: 20px;
}

label {
  /* styling for the labels */
  font-weight: bold;
  display: block;
  margin-bottom: 10px;
  color: var(--navy);
}

input[type="text"],
input[type="email"],
textarea {
  width: 100%;
  padding: 12px;
  margin-bottom: 20px;
  border: 1px solid var(--navy);
}
textarea{
    height: 9rem;
}
input[type="submit"] {
  background-color: var(--navy);
  color: white;
  padding: 12px 20px;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: var(--green);
  border: 1px solid var(--navy);
}

/*===================FOOTER===================*/
.footer_el{
  padding-top: 2rem;
  padding-bottom: 2rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
.footer_socials a{
    padding-left: 6px;
    padding-right: 6px;
    font-size: 35px;
    gap: 3rem;
    color: var(--green);
}
.footer_socials a:hover{
  color: var(--green);
}
.footer_socials a:hover:nth-child(1){
  color: #00aced;
}
.footer_socials a:hover:nth-child(2){
  color: #FF0000;
}
.footer_socials a:hover:nth-child(3){
  background-image: linear-gradient(to right, #405de6, #5851db, #833ab4, #c13584, #e1306c, #fd1d1d);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}
.footer_socials a:hover:nth-child(4){
  color: #181717;
}
.footer_socials a:hover:nth-child(5){
  color:  #0077B5;
}
.small{
  padding-top: 1rem;
}





@media screen and (min-width: 767px){
    .all{
    width: 86%;
  }
  .logo img{
    width: 40%;
}

    .nav_el{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    height: 5rem;
    /* position: fixed; */
  }
  .nav_menu {
    z-index: 1;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    position: unset;
    top: unset;
    bottom: unset;
    right: 0;
    padding: unset;
    width: unset;
    height: 100%;
    animation: slideInFromLeft 800ms;
    /* opacity: 0;
    transition: 4ms all ease-in-out; */
    /* box-shadow: -10px 0px 30px 15px var(--navy-shadow); */
  }
  .nav__menu1{
    display: flex;
    flex-direction: row;
    align-items: center;
    height: inherit;
    gap: 10rem;
    justify-content: center;
  }
  .nav__menu1 p{
    display: none;
  }
  .nav__menu1 a{
    padding-left: 1rem;
    padding-right: 1rem;
  }
  
  .nav__menu1 a:hover::after {
    content: "";
    display: inline-block;
    border-bottom: 3px solid var(--green);
    width: 100%;
    border-top: 0;
    margin-bottom: 30px;
}

  .resume{
    padding-left: 2rem;
    border-radius: 10px;
    border: 1px solid var(--green);
    padding: 12px 16px;
  }
  .resume:hover{
    border: 1px solid var(--slate);
  }
  .resume a:hover{
    color: var(--slate);
  }
  button nav_btn{
    display: none;
  }
  #open_btn{
    display: none;
  }
  .nav_btn{
    display: none;
  }
  /*===================HEADER===================*/
  .header_cool{
    display: grid;
    grid-template-columns: 40% 60%;
    align-items: center;
    justify-content: center;
  }

  .header_img{
    display: none;
  }
  .header_img2{
    display: flex;
    margin-bottom: 2rem;
  }
.contact_all{
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-items: center;
  justify-content: space-between;
}
  .work_el{
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 2rem;
  }  
  .work_all{
    margin-bottom: 1rem;
  }  
  .footer_el{
    display: flex;
    position: relative;
  }
  .footer_socials{
    display: flex;
    flex-direction: column;
    position: fixed;
    top: 55%;
    left: 1%;
    gap: 1rem;
  }
  .footer_socials a{
    font-size: 30px;
  }
 

}
@media screen and (min-width: 1024px){
  .logo{
    max-width: 8%;
} 
  .header_cool{
        display: grid;
        grid-template-columns: 1fr 1fr;
    }
    .work_el{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    }  
    
    .footer_socials a:hover{
        color: var(--slate);
    }
    .contact_all{
        gap: 5rem;
    }
    .footer_socials a{
    font-size: 35px;
  }
}

</style>
<header>
    <link href='https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css' rel='stylesheet'>
</header>
<body>
    
    <nav class={navClass}> 
        <div class="nav_el all">
        <div class="logo">
          <h1>Y.A</h1>
          <!-- <img src="logo1.png" alt=""> -->
        </div>
        <ul bind:this={navMenu} class="nav_menu">
            
            <li class="nav__menu1">
                <p>01.</p>
                <a href="#about" on:click={close} bind:this={closeBtn}>About</a>
            </li>
            
            <li class="nav__menu1">
                <p>02.</p>
                <a href="#experience" on:click={close} bind:this={closeBtn}>Experience</a>
            </li>
            <li class="nav__menu1">
                <p>03.</p>
                <a href="#work" on:click={close} bind:this={closeBtn}>Work</a>
            </li>
            <li class="nav__menu1">
                <p>04.</p>
                <a href="#Contact" on:click={close} bind:this={closeBtn}>Contact</a>
            </li>
            <div class="resume"><a href="/resume">Resume</a></div>
        </ul>
        <button on:click={open} bind:this={openBtn} class="nav_btn" id="open_btn"><i class='bx bx-menu-alt-right'></i></button>
        <button on:click={close} bind:this={closeBtn} class="nav_btn" id="close_btn"><i class='bx bx-x'></i></button>
    </div>
    </nav>
<!--==================== END OF NAVBAR ===================-->
<div class="unknown"></div>
<header>
    <div class="header_el all">
        <div class="header_cool">
        <div class="header_img">
            <img src="o.png" class="animated_img">
        </div>
        <div class="header_text">
          <div>
            <p class="header_me" in:fade={{duration: 500}}>{typing[0]}</p>
          </div>
          <div>
            <p class="header_name" in:fade={{duration: 500}}>{typing[1]}</p>
          </div>
          <div>
            <p class="header_about" in:fade={{duration: 500}}>{typing[2]}</p>
          </div>
          <div>
            <p class="header_aboutp" in:fade={{duration: 500}}>{typing[3]}</p>
          </div>
        </div>
        
        <div class="header_img2">
            <img src="o.png" class="animated_img">
        </div>
    </div>    
        <button class="header_btn"><a href="/resume">Check out my Resume!</a></button>
    </div>
</header>
<!--==================== END OF HEADER ===================-->
<!-- <canvas id="canvas"></canvas>
<section class="my_pic">
    <div class="pic_el">
        
    </div>
</section> -->
<section class="about" id="about" >
    <div class="about_el all">
        <div class="about_head">
            <h3>01.</h3>
            <h2>About</h2>
        </div>
        <p class="about_abt">
          Hey there, am a frontend development. But I'm on a mission to become a Fullstack Developer, but currently, I'm focusing on frontend development.

          I've been learning various frontend technologies, including HTML, CSS, and JavaScript, as well as popular frameworks like Sveltekit. I'm always looking for ways to improve my skills and deliver great user experiences.
          
          Aside from my technical skills, I'm a team player with strong communication and collaboration skills. I love working with others to solve complex problems and create innovative solutions.
          
          I'm eager to continue expanding my knowledge and experience in both frontend and backend development. I'm excited about taking on new challenges and contributing to the creation of impactful digital solutions.
          
          Thanks for taking the time to get to know me a little better!
        </p>
        <img src="" alt="">
    </div>
</section>
<!--==================== END OF ABOUT ===================-->
<section class="experience" id="experience">
    <div class="experience_el all">
        <div class="experience_head">
            <h3>02.</h3>
            <h2>Career Objetive</h2>
        </div>
        <!-- <h3 class="experience_subhead">[Codesideacademy]</h3> -->
        <p class="experience_abt">
          As an aspiring Frontend Developer, I am enthusiastic about utilizing my developing skills to contribute to the creation of dynamic and user-friendly web applications. I have gained foundational knowledge in various frontend development technologies, such as HTML, CSS, and JavaScript, and I am constantly expanding my expertise in the field.

          I am eager to gain real-world experience in the industry and am actively seeking opportunities to intern or work as a Junior Developer. I am highly coachable, with a strong desire to learn and grow as a developer. I have completed relevant coursework and/or online courses in frontend development, and I am eager to apply my knowledge in a professional setting.
          
          In addition to my technical skills, I possess strong communication and collaboration skills, and I am able to work effectively in a team environment. I am highly organized, detail-oriented, and committed to delivering quality work.
          
          I am also familiar with various tools and platforms used in frontend development, such as Git, GitHub, and popular frameworks like sveltekit. I am eager to further develop my skills and contribute to projects that make a positive impact on users' experiences.
          
          Overall, I am a passionate and dedicated individual who is eager to jumpstart their career as a Frontend Developer. I believe that an internship or Junior Developer position would provide me with the opportunity to further develop my skills and gain valuable real-world experience in the industry.
          
        </p>
    </div>
</section>
<!--==================== END OF EXPERIENCE ===================-->
<section class="work" id="work">
    <div class="work_head all">
        <h3>03.</h3>
        <h2>Some Things Have Built</h2>
    </div>
    <div class="work_el all">
        <article class="work_all">
            <div class="work_all-img">
                <img src="/pk4.png" class="gradient-image">
            </div>
                <div class="work_all-abt">
                    <h4><a href="/project1">A Coffee Website</a></h4>
                    <p>A Coffee Website that is fully responsive and user-friendly, built with technologies such as HTML, CSS, JavaScript and Sveltekit,</p>
                    <!-- <a href="#" class="work_btn btn-primary">See Full Website</a> -->
                </div>
        </article>

        <article class="work_all">
            <div class="work_all-img">
                <img src="/pk3.png" class="gradient-image">
            </div>
                <div class="work_all-abt">
                  <div class="work_all-abt">
                    <h4><a href="/project2">A Education website</a></h4>
                    <p> Built an educational website with responsive design, built using technologies such as HTML, CSS, JavaScript, and Sveltekit.</p>
                    <!-- <a href="#" class="work_btn btn-primary">See Full Website</a> -->
                </div>
        </article>

        <article class="work_all">
            <div class="work_all-img">
                <img src="/pk5.png" class="gradient-image">
            </div>
                <div class="work_all-abt">
                  <h4><a href="/project3">A Basic Calculator</a></h4>
                    <p> Built this basic calculator using HTML, CSS, JavaScript and Sveltekit. It is a fully functional for  basic arithmetic operations</p>
                    <!-- <a href="#" class="work_btn btn-primary">See Full Website</a> -->
                </div>
        </article>

        <article class="work_all">
            <div class="work_all-img">
                <img src="/twitter.png" class="gradient-image">
            </div>
                <div class="work_all-abt">
                  <h4><a href="/">A Twitter Prototype</a></h4>
                    <p>COMING!!!!!!!!!!!</p>
                    <!-- <a href="#" class="work_btn btn-primary">See Full Website</a> -->
                </div>
        </article>
    </div>
</section>
<!--==================== END OF MY WORK ===================-->
<section class="contact" id="Contact">
  <div class="contact_all all">
    <div class="contact_text">
    <p class="contact_head1">04. What's Next?</p>
    <h2 class="contact_head2">Get In Touch</h2>
    <p class="contact_headp">
        I am open for any web development job, my skills 
        include proficiency in various technologies and frameworks.
    </p>
  </div>

    <form class="all">
      <label for="name">Name:</label>
      <input type="text" id="name" name="name" bind:value={name} required>
    
      <label for="email">Email:</label>
      <input type="email" id="email" name="email" bind:value={email} required>
    
      <label for="message">Message:</label>
      <textarea id="message" name="message" bind:value={message} required></textarea>
    
      <input type="submit" value="Submit">
    </form>

</div>
</section>
<!--==================== END OF CONTACT ===================-->
<section class="footer">
    <div class="footer_el all">
        <div class="footer_socials">
            <a href="https://twitter.com/AmudaCodes?s=20&t=QPnPLnKYq-z5qUXeyKcwQQ"><i class='bx bxl-twitter'></i></a>
            <a href="https://www.youtube.com/@amudacodes"><i class='bx bxl-youtube'></i></a>
            <a href="#"><i class='bx bxl-instagram-alt'></i></a>
            <a href="https://github.com/Amudacodes"><i class='bx bxl-github'></i></a>
            <a href="https://www.linkedin.com/in/yusuf-adeagbo-56b235263/"><i class='bx bxl-linkedin'></i></a>
        </div>
        <div class="small">
        <small>Copyright &copy; Designed & Built by Yusuf Adeagbo.</small>
        </div>
      </div>
</section>
</body>






























































<!-- 
<button class="contact_btn" on:click={showForm}>Contact Me</button>


<div class="contact all">
  <form action="submit" method="post" class="{showFormVisible ? 'show' : 'hide'}">
      <label for="name">Name:</label>
      <input type="text" id="name" name="name" required>
    
      <label for="email">Email:</label>
      <input type="email" id="email" name="email" required>
    
      <label for="message">Message:</label>
      <textarea id="message" name="message" required></textarea>
    
      <input type="submit" value="Submit">
  </form>
</div> -->


















<!-- <div>
    <canvas id="canvas"
      on:mousedown={startDrawing}
      on:mousemove={draw}
      on:mouseup={stopDrawing}
      on:mouseleave={stopDrawing}
    ></canvas>
  </div>

 


  let isDrawing = false;
  let x = 0;
  let y = 0;

  function startDrawing(event) {
    isDrawing = true;
    x = event.clientX;
    y = event.clientY;
  }

  function draw(event) {
    if (!isDrawing) return;
    let ctx = canvas.getContext("2d");
    ctx.beginPath();
    ctx.moveTo(x, y);
    ctx.lineTo(event.clientX, event.clientY);
    ctx.stroke();
    x = event.clientX;
    y = event.clientY;
  }

  function stopDrawing() {
    isDrawing = false;
  } -->










  <!-- <html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="card">
      <div class="imgBx">
        <img
          src="https://i.pinimg.com/564x/3e/b2/f7/3eb2f70bbd7cbc175f2ae3ffa7a6486d.jpg"
          alt=""
        />
      </div>
      <div class="details">
        <h3>Nike Air Max<br /><span>Men's Shoe</span></h3>
        <h4>Products Details</h4>
        <p>
          Lorem ipsum dolor sit amet consectetur, adipisicing elit. Minus,
          atque.
        </p>
        <h4>Size</h4>
        <ul class="size">
          <li>36</li>
          <li>38</li>
          <li>40</li>
          <li>42</li>
          <li>44</li>
        </ul>
        <div class="group">
          <h2>$199<small>.99</small></h2>
          <a href="#">Buy Now</a>
        </div>
      </div>
    </div>
    <p class="tag">@junaidcoder</p>
  </body>
</html>


 -->
















<!-- 
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800;900&display=swap');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

body {
  display: flex;
  justify-content: center;
  position: relative;
  align-items: center;
  min-height: 100vh;
  /* background: linear-gradient(#3591ce, #3591ce 50%, #fff 50%, #fff 100%); */
  background: linear-gradient(#003355, #003355 50%, #FFF8F3 50%, #FFF8F3 100%);
}

.card {
  position: relative;
  width: 300px;
  height: 350px;
  background: #000;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.220);
  display: flex;
  overflow: hidden;
  transition: 0.5s ease-in-out;
  border-radius: 10px;
}

.card:hover {
  width: 600px;
}

.card .imgBx {
  position: relative;
  min-width: 300px;
  height: 100%;
  background: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  z-index: 2;
}

.card .imgBx img {
  max-width: 250px;
  transition: 0.5s ease-in-out;
}

.card:hover .imgBx img {
  transform: rotate(-35deg) translate(-20px);
}

.card .details {
  position: absolute;
  left: 0;
  min-width: 300px;
  height: 100%;
  background: #003355;
  display: flex;
  justify-content: center;
  /* align-items: center; */
  padding: 20px;
  flex-direction: column;
  z-index: 1;
  transition: 0.5s ease-in-out;
}

.card:hover .details {
  left: 300px;
}

.card .details::before {
  content: '';
  position: absolute;
  left: 0;
  width: 0;
  height: 0;
  border-top: 10px solid transparent;
  border-bottom: 10px solid transparent;
  border-left: 10px solid #fff;
}

.card .details h3 {
  color: #fff;
  text-transform: uppercase;
  font-weight: 600;
  font-size: 1.5em;
  line-height: 1em;
}

.card .details h3 span {
  font-size: 0.65em;
  font-weight: 300;
  text-transform: none;
  opacity: 0.85;
}

.card .details h4 {
  color: #fff;
  text-transform: uppercase;
  font-weight: 600;
  font-weight: 0.9em;
  margin-top: 20px;
  margin-bottom: 10px;
  line-height: 1em;
} 

.card .details p {
  color: #fff;
  opacity: 0.35;
  font-size: 0.8em;
}

.card .details .size {
  display: flex;
  gap: 10px;
}

.card .details .size li {
  list-style: none;
  color: #fff;
  font-size: 0.9em;
  width: 40px;
  height: 40px;
  border: 2px solid #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  font-weight: 500;
  opacity: 0.65;
  border-radius: 8px;
  cursor: pointer;
  transition: 0.1s;
}

.card .details .size li:hover {
  color: #003355;
  background: #fff;
  opacity: 1;
}

.card .details .group {
  position: relative;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
}

.card .details .group h2 {
  color: #fff;
  font-weight: 600;
  font-size: 2em;
}

.card .details .group h2 sup {
  font-weight: 300;
}

.card .details .group h2 small {
  font-size: 0.75em;
}

.card .details .group a {
  display: inline-flex;
  padding: 10px 25px;
  background: #fff;
  text-decoration: none;
  text-transform: uppercase;
  font-weight: 500;
  border-radius: 8px;
  color: #003355;
  box-shadow: 0 15px 15px rgba(0, 0, 0, 0.288);
  transition: 0.3s;
}

.card .details .group a:hover {
  background: #095ea3;
  color: #fff;
}

.tag {
  position: absolute;
  bottom: 8px;
  right: 10px;
  color: rgba(151, 150, 150, 0.781);
  font-size: 10px;
} -->