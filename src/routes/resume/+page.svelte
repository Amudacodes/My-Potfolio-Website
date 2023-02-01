<style>
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


body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: white;
    padding: 0;
    margin: 0;
    list-style: none;
    outline: none;
    box-sizing: border-box;
    text-decoration: none;
    background-color: #020d1d;
    width: 90%;
    margin: 0 auto;
}

h1, h2, h3 {
    font-weight: 600;
    margin-top: 0;
}

h1 {
    font-size: 36px;
    padding-top: 2rem;
}

h2 {
    font-size: 24px;
    margin-bottom: 16px;
    padding-top: 1rem;
    color: #8892b0;
}

h3 {
    font-size: 18px;
    margin-bottom: 8px;
    color: #8892b0;
}

p {
    margin-bottom: 16px;
}

ul {
    margin: 0;
    padding: 0;
    list-style: none;
}
.references li{
    padding-bottom: 2rem;
}
@media only screen and (min-width: 1024px) {
    body{
        width: 85%;
    }
}
</style>



<head>
    <title>My Resume</title>
    <!-- ICONSCOUT CDN-->
    <link rel="stylesheet" href="https://unicons.iconscout.com/release/v2.1.6/css/unicons.css">
      <title>My Calculator</title>
    </head>
<body>
    <div>
        <h1>Yusuf Adeagbo</h1>
        <h3>Contact Information</h3>
        <p>Email: amudacodes@gmail.com</p>
        <p>Phone: +2348175704527</p>
        <p>Address: Opposite Global Model Academy, Bagusa Dei-Dei, F.C.T Abuja</p>
        <h2>Objective</h2>
        <p>A highly motivated and skilled web developer with 5 months of experience in building dynamic websites and web applications utilizing HTML, CSS, and JavaScript. Proficient in responsive web design, with a strong understanding of user experience and user interface design principles. A passionate technologist seeking to leverage my skills and experience to make a positive impact in a challenging and dynamic work environment.</p>
        <h2>Education</h2>
        <ul>
          <li>O-level qualification in Science, Global Model Academy</li>
        </ul>
        <h2>Work Experience</h2>
        <ul>
          <li>
            <h3>Web Developer, 5 months</h3>
            <p>- Worked on a team to develop and maintain multiple websites and web applications utilizing HTML, CSS, and JavaScript</p>
            <p>- Collaborated with cross-functional teams to ensure projects were completed on time and to the satisfaction of clients.</p>
          </li>
        </ul>
        <h2>Skills</h2>
        <ul>
          <li>Proficient in HTML, CSS, and JavaScript, with strong knowledge of web development best practices</li>
          <li>Experience with responsive web design and user interface development</li>
          <li>Proficient in Inshort Creative Suite and video editing software</li>
          <li>Strong problem-solving and debugging skills</li>
          <li>Excellent communication and teamwork skills</li>
        </ul>
        <h2>References</h2>
        <ul class="references">
          <li>Mr AbdulKareem</li>
        </ul>
      </div>
      <div class="close_all">
        <button id="close_all" class="popup-button"><a href="/"><i class="uil uil-multiply"></i></a></button>
    </div> 
</body>