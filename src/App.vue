<template>
  <div id="app">  
      <br>
      <br>
      <div class="container-sm" style="border:0px">
          <div class="row">
              <div class="col-md-6 col-md-offset-3">
				<!-- Inicio Panel -->  
                <div class="panel panel-login shadow-lg p-3 mb-5 rounded">
					<!-- Logo e icono usuario -->
					<div class="row">
						<div class="col-md-6">
							<img src="./assets/logoFinir.png" width="50" height="50"> 
						</div>
						<div class="col-md-6">
							<label class="label" type="text"> 
								<i class='fas fa-user-alt' style='font-size: 48px; color:#59B2E0'></i>
							</label>
						</div>	  	  
					</div>
					<!-- Fin -->
						<hr style="width:100%; text-align:left; margin-left:0">
					<!-- Inicio cabecera del Panel -->
                  <div class="panel-heading">
                    <div class="row">
                      <div class="col-xs-6">
                        <a href="#" class="active" id="login-form-link">Iniciar Sesión</a>
                      </div>
                      <div class="col-xs-6">
                        <a href="#" id="register-form-link">Registrarse</a>
                      </div>
                    </div>

                    <hr >

                  </div>
				    <!-- Fin cabecera del Panel -->
					<!-- Inicio body del Panel -->
                  <div class="panel-body">
                    <div class="row">
                      <div class="col-lg-12">
						  <!-- Formulario Ingreso-->
                        <form id="login-form" action="#" method="post" role="form" style="display: block;">
                          <div class="form-group">
                            <input type="text" name="username" id="username" tabindex="1" class="form-control" placeholder="Usuario" value="">
                          </div>
                          <div class="form-group">
                            <input type="password" name="password" id="password" tabindex="2" class="form-control" placeholder="Contraseña">
                          </div>
                          <div class="form-group text-center">
                            <input type="checkbox" tabindex="3" class="" name="remember" id="remember">
                            <label for="remember"> Recordarme</label>
                          </div>
                          <div class="form-group">
                            <div class="row">
                              <div class="col-sm-6 col-sm-offset-3">
                                <input type="submit" name="login-submit" id="login-submit" tabindex="4" class="form-control btn btn-login" value="Ingresar">
                              </div>
                            </div>
                          </div>
                          <div class="form-group">
                            <div class="row">
                              <div class="col-lg-12">
                                <div class="text-center">
                                  <a href="#" tabindex="5" class="forgot-password">¿Se te olvidó tu contraseña?</a>
                                </div>
                              </div>
                            </div>
                          </div>
                        </form>
						<!-- Formulario Registro-->
                        <form id="register-form" action="#" method="post" role="form" style="display: none;">
                          <div class="form-group">
                            <input type="text" name="nombres" id="nombres" tabindex="1" class="form-control" placeholder="Nombres" value="">
                          </div>
                          <div class="form-group">
                            <input type="text" name="apellidos" id="apellidos" tabindex="1" class="form-control" placeholder="Apellidos" value="">
                          </div>
                          <div class="form-group">
                            <input type="email" name="email" id="email" tabindex="1" class="form-control" placeholder="E-mail" value="">
                          </div>
						  <div class="form-group">
                            <input type="text" name="username" id="username" tabindex="1" class="form-control" placeholder="Usuario" value="">
                          </div>
                          <div class="form-group">
                            <input type="password" name="password" id="password" tabindex="2" class="form-control" placeholder="Contraseña">
                          </div>
                          <div class="form-group">
                            <input type="password" name="confirm-password" id="confirm-password" tabindex="2" class="form-control" placeholder="Confirmar contraseña">
                          </div>
                          <div class="form-group">
                            <div class="row">
                              <div class="col-sm-6 col-sm-offset-3">
                                <input type="submit" name="register-submit" id="register-submit" tabindex="4" class="form-control btn btn-register" value="Registrarme ahora">
                              </div>
                            </div>
                          </div>
                        </form>
                      </div>
                    </div>
                  </div>
					<!-- fin body del Panel -->
                  <footer class="page-footer font-small blue pt-4"> 
                      <!-- Copyright -->
                    <div class="footer-copyright text-center py-3">© 2020 Copyright:<a href="#"> Finir</a>
                    </div>
                    <!-- Copyright -->
                  </footer> 

                </div>
            </div>
          </div>
      </div>
  </div> 
</template>

<script>

export default {
  name: "App",
  data() {
    return {
      user: {
		errors:[],
        username: "",
        password: ""
      },
      submitted: false
    };
  },
  methods: {
    checkForm: function (e) {
      if (this.username && this.password) {
        return true;
      }

      this.errors = [];

      if (!this.username) {
        this.errors.push('Ingrese el usuario');
      }
      if (!this.password) {
        this.errors.push('Ingrese la contraseña');
      }

      e.preventDefault();
    }
  }
};

  
  $(function() {

    $('#login-form-link').click(function(e) {
		$("#login-form").delay(100).fadeIn(100);
 		$("#register-form").fadeOut(100);
		$('#register-form-link').removeClass('active');
		$(this).addClass('active');
		e.preventDefault();
	});
	$('#register-form-link').click(function(e) {
		$("#register-form").delay(100).fadeIn(100);
 		$("#login-form").fadeOut(100);
		$('#login-form-link').removeClass('active');
		$(this).addClass('active');
		e.preventDefault();
	});

});

$(document).ready(function(){
	var altura = $('.menu').offset().top;
	
	$(window).on('scroll', function(){
		if ( $(window).scrollTop() > altura ){
			$('.menu').addClass('menu-fixed');
		} else {
			$('.menu').removeClass('menu-fixed');
		}
	});
 
});

 </script>
<style>


.panel-login {
	border-color: #ccc;
	-webkit-box-shadow: 0px 2px 3px 0px rgba(0,0,0,0.2);
	-moz-box-shadow: 0px 2px 3px 0px rgba(0,0,0,0.2);
	box-shadow: 0px 2px 3px 0px rgba(0,0,0,0.2);
}
.panel-login>.panel-heading {
	color: #00415d;
	background-color: #fff;
	border-color: #fff;
	text-align:center;
}
.panel-login>.panel-heading a{
	text-decoration: none;
	color: #666;
	font-weight: bold;
	font-size: 15px;
	-webkit-transition: all 0.1s linear;
	-moz-transition: all 0.1s linear;
	transition: all 0.1s linear;
}
.panel-login>.panel-heading a.active{
	color: #59B2E0;
	font-size: 20px;
}
.panel-login>.panel-heading hr{
	margin-top: 10px;
	margin-bottom: 0px;
	clear: both;
	border: 0;
	height: 1px;
	background-image: -webkit-linear-gradient(left,rgba(0, 0, 0, 0),rgba(0, 0, 0, 0.15),rgba(0, 0, 0, 0));
	background-image: -moz-linear-gradient(left,rgba(0,0,0,0),rgba(0,0,0,0.15),rgba(0,0,0,0));
	background-image: -ms-linear-gradient(left,rgba(0,0,0,0),rgba(0,0,0,0.15),rgba(0,0,0,0));
	background-image: -o-linear-gradient(left,rgba(0,0,0,0),rgba(0,0,0,0.15),rgba(0,0,0,0));
}
.panel-login input[type="text"],.panel-login input[type="email"],.panel-login input[type="password"] {
	height: 45px;
	border: 1px solid #ddd;
	font-size: 16px;
	-webkit-transition: all 0.1s linear;
	-moz-transition: all 0.1s linear;
	transition: all 0.1s linear;
}
.panel-login input:hover,
.panel-login input:focus {
	outline:none;
	-webkit-box-shadow: none;
	-moz-box-shadow: none;
	box-shadow: none;
	border-color: #ccc;
}
.btn-login {
	background-color: #59B2E0;
	outline: none;
	color: #fff;
	font-size: 14px;
	height: auto;
	font-weight: normal;
	padding: 14px 0;
	text-transform: uppercase;
	border-color: #59B2E6;
}
.btn-login:hover,
.btn-login:focus {
	color: #fff;
	background-color: #53A3CD;
	border-color: #53A3CD;
}
.forgot-password {
	text-decoration: underline;
	color: #888;
}
.forgot-password:hover,
.forgot-password:focus {
	text-decoration: underline;
	color: #666;
}

.btn-register {
	background-color: #53A3CD;
	outline: none;
	color: #fff;
	font-size: 14px;
	height: auto;
	font-weight: normal;
	padding: 14px 0;
	text-transform: uppercase;
	border-color: #53A3CD;
}
.btn-register:hover,
.btn-register:focus {
	color: #fff;
	background-color: #53A3CD;
	border-color:#53A3CD;
}

.row {
  padding-top: 40px;
}

.contenedor {
	width: 95%;
	max-width:1000px;
	margin:auto;
}
 
.contenedor p {
	margin-bottom:40px;
}
 
header nav {
	background:#3498db;
	margin-bottom:10px;
}
 
header nav ul {
	list-style: none;
	overflow: hidden;
}
 
header nav ul li {
	float: left;
}
 
header nav ul li a {
	display: block;
	padding:20px;
	color:#fff;
	text-decoration: none;
}
 
header nav ul li a:hover {
	background:#2980b9;
}
 
 
/* --- Clase que agregaremos cuando el usuario haga scroll --- */
.menu-fixed {
	position:fixed;
	z-index:1000;
	top:0;
	max-width:1000px;
	width:100%;
	box-shadow:0px 4px 3px rgba(0,0,0,.5);
}

.label{
	color: #59B2E0;
	font-weight: bold;
	font-size: 40px;	
}

.col-xs-6 a.active{
	box-shadow: 0px 2px 0px 0px rgba(0,0,0,0.1);
}
</style>