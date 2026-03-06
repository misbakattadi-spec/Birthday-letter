# Birthday-letter
Birthday wishing website 
hard now that I'm insane and crazy.  I couldn't help myself from adoring u. </p>  <button class="openBox" onclick="openGallery()">💙 Open Me</button>  </div>  </section>   <!-- PHOTO BOOTH -->  <section id="galleryPage">  <div class="gallery">  <div class="polaroid"><img src="photos/pic1.jpg" onclick="kissExplosion()"></div> <div class="polaroid"><img src="photos/pic2.jpg" onclick="kissExplosion()"></div> <div class="polaroid"><img src="photos/pic3.jpg" onclick="kissExplosion()"></div> <div class="polaroid"><img src="photos/pic4.jpg" onclick="kissExplosion()"></div> <div class="polaroid"><img src=
birthday-site
│
├── index.html
├── style.css
├── script.js
│
├── photos
│   ├── pic1.jpg
│   ├── pic2.jpg
│   ├── pic3.jpg
│   ├── pic4.jpg
│   ├── pic5.jpg
│   └── pic6.jpg
│
└── paper.png
body{
margin:0;
background:#d7ecff;
font-family:Georgia;
overflow:hidden;
text-align:center;
}

section{
position:absolute;
width:100%;
height:100vh;
display:flex;
justify-content:center;
align-items:center;
flex-direction:column;
}

/* envelope */

.envelope{
width:320px;
height:220px;
background:white;
position:relative;
box-shadow:0 10px 30px rgba(0,0,0,0.2);
}

.flap{
position:absolute;
width:100%;
height:100%;
background:#f3f3f3;
clip-path:polygon(0 0,100% 0,50% 60%);
transform-origin:top;
transition:1s;
}

.seal{
position:absolute;
top:80px;
left:50%;
transform:translateX(-50%);
background:#7ab8ff;
width:50px;
height:50px;
border-radius:50%;
display:flex;
align-items:center;
justify-content:center;
cursor:pointer;
}

/* letter */

#letterPage{
display:none;
}

.letter{
background:url("paper.png");
background-size:cover;
padding:40px;
width:450px;
line-height:1.7;
box-shadow:0 10px 25px rgba(0,0,0,0.2);
}

.openBox{
margin-top:20px;
padding:10px 20px;
background:#6fb6ff;
border:none;
color:white;
font-size:16px;
cursor:pointer;
}

/* gallery */

#galleryPage{
display:none;
}

.gallery{
display:grid;
grid-template-columns:repeat(3,150px);
gap:20px;
}

.polaroid{
background:white;
padding:10px 10px 40px 10px;
box-shadow:0 6px 15px rgba(0,0,0,0.2);
transform:rotate(-2deg);
}

.polaroid img{
width:130px;
height:130px;
object-fit:cover;
cursor:pointer;
}

/* final */

#finalPage{
display:none;
font-size:30px;
}

.bouquet{
font-size:60px;
margin-top:20px;
}
function openEnvelope(){

document.querySelector(".flap").style.transform="rotateX(180deg)"

setTimeout(()=>{
document.getElementById("envelopePage").style.display="none"
document.getElementById("letterPage").style.display="flex"
},900)

}

function openGallery(){

document.getElementById("letterPage").style.display="none"
document.getElementById("galleryPage").style.display="flex"

}

function kissExplosion(){

for(let i=0;i<40;i++){

let kiss=document.createElement("div")

kiss.innerText="💋"

kiss.style.position="absolute"

kiss.style.left=Math.random()*100+"vw"
kiss.style.top="-10px"

kiss.style.fontSize="30px"

kiss.style.animation="fall 3s linear"

document.body.appendChild(kiss)

setTimeout(()=>{kiss.remove()},3000)

}

setTimeout(()=>{
document.getElementById("galleryPage").style.display="none"
document.getElementById("finalPage").style.display="flex"
},2000)

}

let style=document.createElement('style')

style.innerHTML=`

@keyframes fall{

0%{transform:translateY(0)}
100%{transform:translateY(100vh)}

}

`

document.head.appendChild(style)
