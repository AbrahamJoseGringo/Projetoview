<script setup>
import { ref } from 'vue';
import HomeIcon from 'vue-material-design-icons/Home.vue';
import Book from 'vue-material-design-icons/Book.vue'
const menuAberto = ref(false);

const toggleMenu = () => {
  menuAberto.value = !menuAberto.value;
};
</script>

<template>
  <header class="header">
    <!-- Seção do logo e nome -->
    <div class="header--left">
      <div class="logo-text">
        <span>Epic <span class="highlight">Reads</span></span>
        <small>Sempre ao dia</small>
      </div>
    </div>

    <!-- Menu de navegação -->
    <nav class="nav">
      <ul :class="menuAberto ? 'menu' : ''">
        <li>
          <a href="#" class="home-btn">
            <HomeIcon class="home-icon" /> Home
          </a>
        </li>
        <li><a href="#">Mais Informações</a></li>
        <li><a href="#">Redes Sociais</a></li>
      </ul>
    </nav>

    <!-- Barra de pesquisa e ícones -->
    <div class="header--right">
      <input type="text" placeholder="Pesquisar" class="search-bar" />
      <div class="language-select">
        <img src="https://upload.wikimedia.org/wikipedia/commons/0/05/Flag_of_Brazil.svg" alt="PT" class="flag" />
      </div>
      <a class="login-btn">Acessar</a>
      <a class="register-btn">Registrar</a>
      <button class="books-btn"><Book></Book></button>
    </div>

    <!-- Ícone do menu hambúrguer -->
    <div class="menu-hamburger" @click="toggleMenu">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </header>
</template>

<style scoped>

.header {
  background-color: #000000;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;
  box-shadow: 0px 1px 10px rgba(0, 0, 0, 0.5);
  color: white;
  position: relative;
  z-index: 10;
  font-family: Montserrat;
}


.header--left {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}


.logo-text {
  display: flex;
  flex-direction: column;
  font-family: Risque;
}

.logo-text span {
  font-size: 1.8rem;
  font-weight: bold;
  color: white;
}

.logo-text .highlight {
  color: #FF8A00; 
}

.logo-text small {
  font-size: 0.8rem;
  color: #fff;
}

/* Menu de navegação */
.nav ul {
  display: flex;
  list-style: none;
  gap: 1rem;
  margin-left: 1rem;
  align-items: center;
}

.nav ul li a {
  text-decoration: none;
  color: rgba(255, 255, 255, 0.329);
  font-size: 1rem;
  font-weight: bold;
  padding: 0.5rem 1rem;
}

.nav ul li a:hover{
  color: #FF8A00;
}



.home-btn {
  display: flex;
  align-items: center;
  background-color: #ff9500;
  color: #000000; /* Cambiar el color del texto a negro */
  padding: 0.5rem 1rem;
  border-radius: 5px;
  text-decoration: none;
  font-weight: bold;
}

.home-btn .home-icon {
  margin-right: 0.5rem;
}

/* Asegúrate de que no haya estilos adicionales que cambien el color del texto del botón Home */
.nav ul li a.home-btn {
  color: #000000; /* Asegúrate de que el color del texto sea negro para el enlace Home */
}


/* Barra de pesquisa */
.search-bar {
  padding: 0.5rem;
  border-radius: 5px;
  border: 1px solid #444;
  background-color: #333;
  color: rgb(0, 0, 0);
  outline: none;
  margin-right: 1rem;
}

/* Seletor de idioma */
.language-select {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.5rem;
}
.language-select .flag {
  width: 30px; /* Ajuste o valor conforme necessário */
  height: 20px; /* Ajuste o valor conforme necessário */
  border-radius: 0; /* Remove a borda arredondada para o formato retangular */
}

/* Ícones e botões alinhados na mesma linha */
.header--right {
  display: flex;
  align-items: center;
  gap: 1rem; /* Espaçamento entre os elementos */
}

.language-select .flag {
  width: 30px; /* Ajuste o valor conforme necessário */
  height: 20px; /* Ajuste o valor conforme necessário */
  border-radius: 0; /* Remove a borda arredondada para o formato retangular */
}

/* Botões de login e registrar */
.login-btn, .register-btn {

  border: none;
  color: rgba(255, 255, 255, 0.397);
  padding: 0.5rem 1rem;
  border-radius: 5px;
  cursor: pointer;
}

.login-btn:hover, .register-btn:hover {
  color: #FF8A00;
}

.books-btn {
  background-color: #FF8A00;
  border: none;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  cursor: pointer;
}

.books-btn:hover {
  background-color: #e68400;
}

/* Menu hambúrguer */
.menu-hamburger {
  display: none;
  flex-direction: column;
  cursor: pointer;
  gap: 5px;
}

.menu-hamburger span {
  background-color: white;
  width: 25px;
  height: 3px;
  display: block;
}


</style>
