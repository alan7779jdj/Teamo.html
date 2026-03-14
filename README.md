<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Te Amo</title>

<style>

body{
  margin:0;
  overflow:hidden;
  background:black;
  font-family:"Brush Script MT","Lucida Handwriting",cursive;
}

/* TE AMO */

.teamo{
  position:absolute;
  color:#ff2a8a;
  font-size:38px;
  animation:mover linear infinite;
  opacity:0.9;
}

/* MUCHOS "MUCHO" */

.mucho{
  position:absolute;
  color:#ff2a8a;
  font-size:48px;
  animation:mover linear infinite;
}

/* movimiento */

@keyframes mover{
  from{ transform:translateY(110vh); }
  to{ transform:translateY(-10vh); }
}

/* corazones */

.corazon{
  position:absolute;
  width:40px;
  height:40px;
  background:#ff2a8a;
  transform:rotate(45deg);
  animation:flotar linear infinite;
}

.corazon::before,
.corazon::after{
  content:"";
  position:absolute;
  width:40px;
  height:40px;
  background:#ff2a8a;
  border-radius:50%;
}

.corazon::before{
  top:-20px;
}

.corazon::after{
  left:-20px;
}

/* animación corazones */

@keyframes flotar{
  from{ transform:translateY(110vh) rotate(45deg); }
  to{ transform:translateY(-10vh) rotate(45deg); }
}

</style>
</head>

<body>

<script>

/* muchos TE AMO */

for(let i=0;i<170;i++){

  let t=document.createElement("div");
  t.className="teamo";
  t.innerText="te amo";

  t.style.left=Math.random()*100+"vw";
  t.style.animationDuration=(6+Math.random()*10)+"s";

  document.body.appendChild(t);
}

/* corazones de fondo */

for(let i=0;i<220;i++){

  let c=document.createElement("div");
  c.className="corazon";

  c.style.left=Math.random()*100+"vw";
  c.style.animationDuration=(5+Math.random()*8)+"s";
  c.style.opacity=0.5;

  document.body.appendChild(c);
}

/* interacción */

document.body.onclick=function(){

  /* muchos "mucho" */

  for(let i=0;i<70;i++){

    let m=document.createElement("div");
    m.className="mucho";
    m.innerText="mucho";

    m.style.left=Math.random()*100+"vw";
    m.style.animationDuration=(5+Math.random()*9)+"s";

    document.body.appendChild(m);
  }

  /* explosión */

  for(let i=0;i<160;i++){

    let c=document.createElement("div");
    c.className="corazon";

    let x=window.innerWidth/2;
    let y=window.innerHeight/2;

    c.style.left=x+"px";
    c.style.top=y+"px";

    document.body.appendChild(c);

    let dx=(Math.random()-0.5)*1000;
    let dy=(Math.random()-0.5)*1000;

    c.animate([
      {transform:"translate(0,0) rotate(45deg)",opacity:1},
      {transform:`translate(${dx}px,${dy}px) rotate(45deg)`,opacity:0}
    ],{
      duration:1500
    });

  }

}

</script>

</body>
  
</html>
