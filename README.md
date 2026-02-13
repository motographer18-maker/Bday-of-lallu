<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>For My Erumaaa 🫶🏻</title>

<style>
body{
  margin:0;
  font-family:Arial, sans-serif;
  overflow:hidden;
}

/* ===== COMMON PAGE STYLE ===== */
.page{
  position:absolute;
  width:100%;
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  flex-direction:column;
}

/* ===== PAGE 1 ===== */
#page1{
  background:#f8c8dc;
  cursor:pointer;
}

.gift{
  width:180px;
  height:180px;
  background:#f5e6d3;
  position:relative;
  opacity:0;
  animation:fadeIn 2s forwards;
}

.lid{
  width:180px;
  height:40px;
  background:#800000;
  position:absolute;
  top:-40px;
}

.ribbon-vertical{
  width:30px;
  height:180px;
  background:#800000;
  position:absolute;
  left:75px;
}

.ribbon-horizontal{
  width:180px;
  height:30px;
  background:#800000;
  position:absolute;
  top:75px;
}

.message{
  margin-top:40px;
  font-size:28px;
  opacity:0;
  animation:fadeIn 3s forwards;
  animation-delay:2s;
}

/* ===== PAGE 2 ===== */
#page2{
  background:#ffe6f0;
  display:none;
  cursor:pointer;
  overflow:hidden;
}

.plane{
  position:absolute;
  font-size:22px;
  padding:10px 20px;
  background:white;
  border-radius:30px;
  box-shadow:0 5px 15px rgba(0,0,0,0.2);
  transition:1s ease;
}

#plane1{ left:-300px; top:30%; }
#plane2{ right:-300px; top:50%; }
#plane3{ bottom:-200px; left:40%; }

.flyLeft{ left:40%; }
.flyRight{ right:40%; }
.flyUp{ bottom:40%; }

.exitLeft{ left:-400px; }
.exitRight{ right:-400px; }
.exitUp{ bottom:-300px; }

/* ===== PAGE 3 ===== */
#page3{
  background:#f8c8dc;
  display:none;
}

.envelope{
  width:300px;
  height:200px;
  background:#f5e6d3;
  position:relative;
  transform:scale(0);
  animation:zoomIn 1.5s forwards;
  cursor:pointer;
}

.flap{
  width:100%;
  height:100px;
  background:#e5d3bd;
  position:absolute;
  top:0;
  clip-path:polygon(0 0,100% 0,50% 100%);
  transition:1s;
  transform-origin:top;
}

.paper{
  width:260px;
  height:0;
  background:white;
  position:absolute;
  left:20px;
  top:60px;
  overflow:hidden;
  text-align:center;
  padding:0 10px;
  transition:1.5s;
}

.paper p{
  margin-top:20px;
  font-size:18px;
}

.open .flap{
  transform:rotateX(180deg);
}

.open .paper{
  height:180px;
  padding-top:20px;
}

/* ===== ANIMATIONS ===== */
@keyframes fadeIn{
  to{opacity:1;}
}

@keyframes zoomIn{
  to{transform:scale(1);}
}
</style>
</head>

<body>

<!-- PAGE 1 -->
<div id="page1" class="page" onclick="goToPage2()">
  <div class="gift">
    <div class="lid"></div>
    <div class="ribbon-vertical"></div>
    <div class="ribbon-horizontal"></div>
  </div>

  <div class="message">
    happy b'day my erumaaa🫶🏻🐃
  </div>
</div>


<!-- PAGE 2 -->
<div id="page2" class="page" onclick="handleClick()">

  <div id="plane1" class="plane">✈️ mera motti🫶🏻</div>
  <div id="plane2" class="plane">✈️ mera buffalo 🐃🫶🏻</div>
  <div id="plane3" class="plane">✈️ mera paagal 🫶🏻</div>

</div>


<!-- PAGE 3 -->
<div id="page3" class="page">

  <div class="envelope" onclick="openLetter(this)">
    <div class="flap"></div>
    <div class="paper">
      <p>
        Another year hotter? This is getting unfair😌.<br><br>
        Save some attraction for the rest of the world.<br><br>
        Happy Birthday mera motti 🫶🏻🐃.
      </p>
    </div>
  </div>

</div>


<script>
let count=0;

function goToPage2(){
  document.getElementById("page1").style.display="none";
  document.getElementById("page2").style.display="flex";
}

function handleClick(){
  count++;

  if(count===1){
    document.getElementById("plane1").classList.add("flyLeft");
  }
  else if(count===2){
    document.getElementById("plane2").classList.add("flyRight");
  }
  else if(count===3){
    document.getElementById("plane3").classList.add("flyUp");
  }
  else if(count===4){
    document.getElementById("plane1").classList.add("exitLeft");
    document.getElementById("plane2").classList.add("exitRight");
    document.getElementById("plane3").classList.add("exitUp");

    setTimeout(()=>{
      document.getElementById("page2").style.display="none";
      document.getElementById("page3").style.display="flex";
    },1500);
  }
}

function openLetter(el){
  el.classList.add("open");
}
</script>

</body>
</html>
