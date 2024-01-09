<script setup>
const titulo = 'El secreto de tu cocina'
</script>

<template>
<div id="border-top" class="h_blue">
  <div class="header">
    <div class="title">{{ titulo }}</div>
    <img class="img-fluid img-header" src="./assets/head-img.png" alt="Imagen Cabecera" />
  </div>
</div>

<div class="box" style="height: 130px ">
</div>

<div class="content" style="margin-right: 8%;">
  <div class="row">
    <div class="col col-3 ">
      <div class="card">
        Menu
      </div>
    </div>
    <div class="col col-9">
      <div class="row">
        <div v-for="dat in data" class="col col-lg-4 col-12 col-md-6">
          <div class="card">
            <img src="./assets/{{dat.image}}" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Card title</h5>
              <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
            </div>
          </div>
        </div>
        <div class="col col-lg-4 col-12 col-md-6">
          <div class="card">
            <img src="./assets/head-img.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Card title</h5>
              <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
            </div>
          </div>
        </div>
        <div class="col col-lg-4 col-12 col-md-6">
          <div class="card">
            <img src="./assets/head-img.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Card title</h5>
              <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content.</p>
            </div>
          </div>
        </div>
        <div class="col col-lg-4 col-12 col-md-6">
          <div class="card">
            <img src="./assets/head-img.png" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">Card title</h5>
              <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="content" style="min-height: 150px; overflow: hidden;">
    <form name="sesion" action="validar.php" method="post" onSubmit="return validateStandard(this, 'error');">
        <table style="width: 100%;">
            <tr>
                <td style="text-align: center;" rowspan="4"><img src="img/login.png" alt="" /></td>
            </tr>
            <tr>
                <td>Usuario:<br />
                    <input type="text" name="usuario" required="1" id="usuario" style="margin-top: 4px;" />
                    Contrase&ntilde;a:<br />
                    <input type="password" name="clave" required="1" id="clave" style="margin-top: 4px;" />
                    <br />
                </td>
            </tr>
            <tr>
                <td style="text-align: right;">
                    <input name="validar" class="boton" value="Ingresar" type="submit" />
                </td>
            </tr>
        </table>
    </form>
    {{ data }}<button type="button" v-on:click="fetch">Pulsa</button>
</div>
</template>

<script>
import axios from 'axios';
let data=new Object;

function  fetch(){
  axios.get("https://5eed24da4cbc340016330f0d.mockapi.io/api/articles")
    .then((res) => (data=JSON.parset(res)))
    .catch(err => (console.log(err)));
}
</script>

<style>
@font-face {
   font-family: Caveat;
   src: url(./assets/Caveat-Regular.ttf);
}
#app {
    font-family: 'Open Sans';
    text-align: center;
    color: #24272A;
    margin: 0;
}

/* cabecera */
.header{
  margin: 0 0 232 0;
}

/* Título de la página */
.title {
    position: absolute;
    font-family: Caveat, 'Open Sans';
    font-style: normal;
    font-weight: 600;
    font-size: 110px;
    line-height: 100px;
    width: 475px;
    height: 200px;
    text-align: left;
    color: #3F454A;
    margin: 12% 0 0 132px;
    background-color: transparent;
}

/*Imagen de la cabecera */
.img-header{

}
</style>
