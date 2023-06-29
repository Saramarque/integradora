<script setup>
  import { ref } from 'vue';
  let array=ref (["-","-","-","-","-","-","-","-","-"])
  let turno= ref("X")
  let msge=ref(false)
  let partidas= ref(0)
  let px= ref(0)
  let po= ref(0)
  let pe= ref(0)
  let empate=ref(false)
  var valoresActuales = [];
  let lista = ref ([])
  let part = ref ([])
  let pcont= ref(1)
  let nombrex = ref("")
  let nombreo= ref ("")
  let turno2=ref ("")

  

  function reiniciar() {
    // Guardar los valores actuales en el arreglo
    valoresActuales.push(array.value[0]);
    valoresActuales.push(array.value[1]);
    valoresActuales.push(array.value[2]);
    valoresActuales.push(array.value[3]);
    valoresActuales.push(array.value[4]);
    valoresActuales.push(array.value[5]);
    valoresActuales.push(array.value[6]);
    valoresActuales.push(array.value[7]);
    valoresActuales.push(array.value[8]);

    // Reiniciar los valores a sus valores iniciales
    array.value[0] ="-";
    array.value[1]="-";
    array.value[2]="-";
    array.value[3] ="-";
    array.value[4]="-";
    array.value[5]="-";
    array.value[6] ="-";
    array.value[7]="-";
    array.value[8]="-";

    document.getElementById("Button1").disabled = false;
    document.getElementById("Button2").disabled = false;
    document.getElementById("Button3").disabled = false;
    document.getElementById("Button4").disabled = false;
    document.getElementById("Button5").disabled = false;
    document.getElementById("Button6").disabled = false;
    document.getElementById("Button7").disabled = false;
    document.getElementById("Button8").disabled = false;
    document.getElementById("Button9").disabled = false;

    msge.value=false
    empate.value=false
    pcont.value++

  }
  const cambiar=(i)=>
  {
    if (turno.value =="X")
    {
     array.value[i]="X"
     turno.value ="O"
    }
    else
    {
     array.value[i] ="O"
     turno.value="X" 
    }
    ganador()
    bloquear()
  }
  function reiniciarjuego() {

   
   msge.value=(false)
   partidas.value=0
   px.value= 0
   po.value= 0
   pe.value=0
   empate.value=(false)
   lista.value = ([])
   part.value = ([])
   pcont.value =1

   array.value[0] ="-";
    array.value[1]="-";
    array.value[2]="-";
    array.value[3] ="-";
    array.value[4]="-";
    array.value[5]="-";
    array.value[6] ="-";
    array.value[7]="-";
    array.value[8]="-";

   document.getElementById("Button1").disabled = false;
    document.getElementById("Button2").disabled = false;
    document.getElementById("Button3").disabled = false;
    document.getElementById("Button4").disabled = false;
    document.getElementById("Button5").disabled = false;
    document.getElementById("Button6").disabled = false;
    document.getElementById("Button7").disabled = false;
    document.getElementById("Button8").disabled = false;
    document.getElementById("Button9").disabled = false;
    nombreo.value=""
    nombrex.value=""

  }
 

  const ganador=()=>
  {
    if(array.value[0] == array.value[1] && array.value[1] == array.value[2] && array.value[0] !== "-" && array.value[1] !=="-" && array.value[2] !== "-")
    {
     msge.value=true
     turno.value=array.value[0]
     partidas.value++
      if(array.value[0]=="X")
      {
        turno2.value=nombrex.value
       px.value++
      }
      else
      {
       po.value++
      turno2.value=nombreo.value
       }
      if(msge.value)
      {
       lista.value.push(turno.value == 'X'? nombrex.value: nombreo.value)   
       part.value.push(pcont.value) 
      }
    }
    if(array.value[3] == array.value[4] && array.value[4] == array.value[5] && array.value[3] !== "-" && array.value[4] !=="-" && array.value[5] !== "-")
    {
     msge.value=true
     turno.value=array.value[3]
     partidas.value++
      if(array.value[3]=="X")
      {
        turno2.value=nombrex.value
       px.value++
      }
      else
      {
       po.value++
      turno2.value=nombreo.value
       }
      if(msge.value)
      {
       lista.value.push(turno.value == 'X'? nombrex.value: nombreo.value)   
       part.value.push(pcont.value) 
      }
    }
    if(array.value[6] == array.value[7] && array.value[7] == array.value[8] && array.value[6] !== "-" && array.value[7] !=="-" && array.value[8] !== "-")
    {
     msge.value=true
     turno.value=array.value[6]
     partidas.value++
      if(array.value[6]=="X")
      {
        turno2.value=nombrex.value
       px.value++
      }
      else
      {
       po.value++
      turno2.value=nombreo.value
       }
      if(msge.value)
      {
       lista.value.push(turno.value == 'X'? nombrex.value: nombreo.value)   
       part.value.push(pcont.value) 
      }
    }
    if(array.value[0] == array.value[3] && array.value[3] == array.value[6] && array.value[0] !== "-" && array.value[3] !=="-" && array.value[6] !== "-")
    {
     msge.value=true
     turno.value=array.value[0]
     partidas.value++
      if(array.value[0]=="X")
      {
        turno2.value=nombrex.value
       px.value++
      }
      else
      {
       po.value++
      turno2.value=nombreo.value
       }
      if(msge.value)
      {
       lista.value.push(turno.value == 'X'? nombrex.value: nombreo.value)   
       part.value.push(pcont.value) 
      }
    }
    if(array.value[1] == array.value[4] && array.value[4] == array.value[7] && array.value[1] !== "-" && array.value[4] !=="-" && array.value[7] !== "-")
    {
     msge.value=true
     turno.value=array.value[1]
     partidas.value++
      if(array.value[1]=="X")
      {
        turno2.value=nombrex.value
       px.value++
      }
      else
      {
       po.value++
      turno2.value=nombreo.value
       }
      if(msge.value)
      {
       lista.value.push(turno.value == 'X'? nombrex.value: nombreo.value)   
       part.value.push(pcont.value) 
      }
    }
    if(array.value[2] == array.value[5] && array.value[5] == array.value[8] && array.value[2] !== "-" && array.value[5] !=="-" && array.value[8] !== "-")
    {
     msge.value=true
     turno.value=array.value[2]
     partidas.value++
      if(array.value[2]=="X")
      {
        turno2.value=nombrex.value
       px.value++
      }
      else
      {
       po.value++
      turno2.value=nombreo.value
       }
      if(msge.value)
      {
       lista.value.push(turno.value == 'X'? nombrex.value: nombreo.value)   
       part.value.push(pcont.value) 
      }
    }
    if(array.value[0] == array.value[4] && array.value[4] == array.value[8] && array.value[0] !== "-" && array.value[4] !=="-" && array.value[8] !== "-")
    {
     msge.value=true
     turno.value=array.value[0]
     partidas.value++
     if(array.value[0]=="X")
      {
        turno2.value=nombrex.value
       px.value++
      }
      else
      {
       po.value++
      turno2.value=nombreo.value
       }
      if(msge.value)
      {
         lista.value.push(turno.value == 'x'? nombrex.value: nombreo.value)   
         part.value.push(pcont.value) 
      }
    }
    if(array.value[2] == array.value[4] && array.value[4] == array.value[6] && array.value[2] !== "-" && array.value[4] !=="-" && array.value[6] !== "-")
    {
     msge.value=true
     turno.value=array.value[2]
     partidas.value++
     if(array.value[0]=="X")
      {
        turno2.value=nombrex.value
       px.value++
      }
      else
      {
       po.value++
      turno2.value=nombreo.value
       }
      if(msge.value)
      {
         lista.value.push(turno.value == 'x'? nombrex.value: nombreo.value)   
         part.value.push(pcont.value) 
      }
    }
    if ( array.value[0] !== "-" && array.value[1] !== "-" && array.value[2] !== "-" && array.value[3] !=="-" && array.value[4] !== "-" && array.value[5] !== "-" && array.value[6] !== "-" && array.value[7] !== "-" && array.value[8] !== "-" && msge.value==(false))
    {
     pe.value++
     empate.value=(true)
     part.value.push(pcont.value) 
     lista.value.push("nadie gano")
    }
  }

  const bloquear=()=>
  {
    if (msge.value==true)
    {
     document.getElementById("Button1").disabled = true;
     document.getElementById("Button2").disabled = true;
     document.getElementById("Button3").disabled = true;
     document.getElementById("Button4").disabled = true;
     document.getElementById("Button5").disabled = true;
     document.getElementById("Button6").disabled = true;
     document.getElementById("Button7").disabled = true;
     document.getElementById("Button8").disabled = true;
    document.getElementById("Button9").disabled = true;
  } 
  }
  
  
</script>

<template>
  <div class="container1 justify-content-column">
    <h2 class="d-flex" style="height: 80px; width: 1420px; font-size:10vh; border: 3px solid rgb(15, 15, 15);"> ¡tres en linea!  </h2>
    <br>
    <br>
    <br>
    <div class="container2" >
      <div id="button"> <button id="button" class="btn btn-primary rounded-pill fs-7 text-center" @click="reiniciar()" style="width: 140px; height: 50px;">Reiniciar ronda </button> </div>
      <div id="button"> <button id="button2" class="btn btn-primary rounded-pill fs-7 text-center" @click="reiniciarjuego()" style="width: 140px; height: 50px;">Reiniciar juego </button> </div>
     
      <div class="container3">
        <div class="d-flex "  style="margin-block-end: 10px;">
          <button id="Button1" :class="array[0] != '-'? 'btn btn-outline-info disabled':'btn btn-info'" style="height: 90px; width: 90px; margin-right: 10px;" @click="cambiar(0)">{{ array[0] }}</button>
          <button id="Button2" :class="array[1] != '-'? 'btn btn-outline-info disabled':'btn btn-info'" style="height: 90px; width: 90px; margin-right: 10px;" @click="cambiar(1)">{{ array[1] }}</button>
          <button id="Button3" :class="array[2] != '-'? 'btn btn-outline-info  disabled':'btn btn-info'" style="height: 90px; width: 90px; margin-right: 10px;" @click="cambiar(2)">{{ array[2] }}</button>
        </div>
        <div class="d-flex " style="margin-block-end: 10px;">
          <button id="Button4" :class="array[3] != '-'? 'btn btn-outline-info  disabled':'btn btn-info'" style="height: 90px; width: 90px; margin-right: 10px;" @click="cambiar(3)">{{ array[3] }}</button>
          <button id="Button5" :class="array[4] != '-'? 'btn btn-outline-info  disabled':'btn btn-info'" style="height: 90px; width: 90px; margin-right: 10px;" @click="cambiar(4)">{{ array[4] }}</button>
          <button id="Button6" :class="array[5] != '-'? 'btn btn-outline-info  disabled':'btn btn-info'" style="height: 90px; width: 90px; margin-right: 10px;" @click="cambiar(5)">{{ array[5] }}</button>
        </div>
        <div class="d-flex " style="margin-block-end: 10px;">
          <button id="Button7" :class="array[6] != '-'? 'btn btn-outline-info  disabled':'btn btn-info'" style="height: 90px; width: 90px; margin-right: 10px;" @click="cambiar(6)">{{ array[6] }}</button>
          <button id="Button8" :class="array[7] != '-'? 'btn btn-outline-info  disabled':'btn btn-info'" style="height: 90px; width: 90px; margin-right: 10px;" @click="cambiar(7)">{{ array[7] }}</button>
          <button id="Button9" :class="array[8] != '-'? 'btn btn-outline-info  disabled':'btn btn-info'" style="height: 90px; width: 90px; margin-right: 10px;" @click="cambiar(8)">{{ array[8] }}</button>
        </div>
        <br>
      </div>
        <div id="th1" style="margin-block-end: 10px;">
          <table class="table text-center ">
            <thead>
             <tr>
               <th  class="align-middle" scope="col">PUNTOS DE {{ nombrex }}</th>
              </tr>
            </thead>
              <tbody>
                <tr>
                 <th class="align-middle" scope="row">{{ px }}</th>
                </tr>
               <!-- Agrega más filas según sea necesario -->
              </tbody>
          </table>
        </div>
        <div id="th2">
          <table class="table text-center">
            <thead>
             <tr>
               <th  class="align-middle" scope="col">PUNTOS DE {{ nombreo }}</th>
              </tr>
            </thead>
              <tbody>
                <tr>
                 <th class="align-middle" scope="row">{{ po }}</th>
                </tr>
               <!-- Agrega más filas según sea necesario -->
              </tbody>
          </table>
        </div>
        <div id="th3" >
          <table class="table text-center ">
            <thead>
             <tr>
               <th class="align-middle" scope="col">NADIE GANO </th>
              </tr>
            </thead>
              <tbody>
                <tr>
                 <th class="align-middle" scope="row">{{ pe }}</th>
                </tr>
               <!-- Agrega más filas según sea necesario -->
              </tbody>
          </table>
        </div>
    </div>
    <div></div>                               
    <marquee style="height:80px; width: 53%; font-size:7vh;" v-show="msge">  el ganador es {{turno2}} </marquee>
    <marquee style="height: 80px; width: 53%; font-size:7vh;" v-show="empate">  sigan intentando </marquee>
    <div id="part">
      <li v-for="cre in part" :key="cre">partida {{cre}} </li>
    </div> 
    <div id="lista">
      <li v-for="crear in lista" :key="crear"> {{ crear }}</li>
    </div>  
    <input id="i1" type="text" class="align-middle; text-align-center" placeholder="nombre del jugador X" v-model="nombrex"/>
<p>{{ answer }}</p>
<input id="i2" type="text" class="align-middle; text-align-center" placeholder="nombre del jugador O" v-model="nombreo"/>
<p>{{ answer2 }}</p>
    
  </div>
</template>


<style scoped>
 *{
   padding: 0;
   margin-top: 0;
  }
  .container1{
   height:100vh;
   width:196vh;
  }

  .container2{
   height:55vh;
   width:200px;
   
  }
  .container3{
   height:360px;
   width:300px;
   position: absolute;
  left: 58%;
  top: 50%;
  transform: translate(-50%, -50%);
  align-items: center;
  }

  #button{
    position: absolute;
  left:185px;
  top:93%;
  transform: translate(-50%, -50%);
  }
  #button2{
    position: absolute;
  left:5px;
  top:93%;
  transform: translate(-50%, -50%);
  }

 

  table{
    width: 200px;
    border: 2px solid #000;
    margin-top: 60px;
    border-collapse: collapse;
    text-align: center;
    
  
  }

  thead{
    background-color: rgb(208, 240, 250);
    height: 60px;
  }

  tbody{
    border-top: 2px solid rgb(7, 7, 12);
    height: 50px;
    
  }

 
  marquee{
    display: flex;
    position: absolute;
  left: 1003px;
  top: 88%;
  transform: translate(-50%, -50%);
  background-color: rgb(185, 215, 250);
  border-radius: 10px;
  border: 3px solid #000;
  align-items: center;
  
  }

  h2{
    position: absolute;
  left: 48%;
  top: 7%;
  transform: translate(-50%, -50%);
  background-color: rgb(185, 215, 250);
  align-items: center;
  justify-content:center ;
  
  }

  #lista{
  
    position: absolute;
  left: 90%;
  top: 50%;
  transform: translate(-50%, -50%);
  font-size:130%;
  }

  #part{
  
  position: absolute;
left: 78%;
top: 50%;
transform: translate(-50%, -50%);
font-size:130%;
}

#th1{
  position: absolute;
left: 11%;
top:40%;
transform: translate(-50%, -50%);
}

#th2{
  position: absolute;
left: 30%;
top: 40%;
transform: translate(-50%, -50%);
}
#th3{
  position: absolute;
left: 21%;
top: 65%;
transform: translate(-50%, -50%);
}
#i1{
  position: absolute;
left:11%;
top: 25%;
transform: translate(-50%, -50%);
border:2px solid rgb(9, 9, 10);
text-align: center;
width: 220px;
height:40px;
}
#i2{
  position: absolute;
left: 30%;
top: 25%;
transform: translate(-50%, -50%);
border:2px solid rgb(9, 9, 10);
text-align: center;
width: 220px;
height:40px;
}


</style>
