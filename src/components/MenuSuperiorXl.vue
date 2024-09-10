<script setup>
import { ref } from 'vue';
import HomeIcon from 'vue-material-design-icons/Home.vue';

const menuAberto = ref(false);

const toggleMenu = () => {
  menuAberto.value = !menuAberto.value;
};
</script>

<template>
  <header class="header">

    <div class="header--left">
      <div class="logo-text">
        <span>Epic <span class="highlight">Reads</span></span>
        <small>Sempre ao dia</small>
      </div>
    </div>

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
        <span>PT</span>
      </div>
      <button class="login-btn">Acessar</button>
      <button class="register-btn">Registrar</button>
      <button class="books-btn">Books</button>
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
/* Header e layout geral */
.header {
  background-color: #1a1a1a; /* Fundo preto */
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;
  box-shadow: 0px 1px 10px rgba(0, 0, 0, 0.5);
  color: white;
  position: relative;
  z-index: 10;
}

/* Logo e texto */
.header--left {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.header--left .logo {
  width: 100px;
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
  color: #ff9500; /* Cor laranja para o "Reads" */
}

.logo-text small {
  font-size: 0.8rem;
  color: #fff;
}

/* Menu de navegação */
.nav ul {
  display: flex;
  list-style: none;
  gap: 1.5rem;
}

.nav ul li a {
  text-decoration: none;
  color: white;
  font-size: 1rem;
  font-weight: bold;
}

.nav ul li a:hover {
  color: #ff9500; /* Laranja no hover */
}

/* Botão Home com ícone */
.home-btn {
  display: flex;
  align-items: center;
  background-color: #ff9500;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  text-decoration: none;
  font-weight: bold;
}

.home-btn .home-icon {
  margin-right: 0.5rem;
}

/* Barra de pesquisa */
.search-bar {
  padding: 0.5rem;
  border-radius: 5px;
  border: 1px solid #444;
  background-color: #333;
  color: white;
  outline: none;
}

/* Seletor de idioma */
.language-select {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  background-color: #444;
  padding: 0.5rem;
  border-radius: 5px;
}

.language-select .flag {
  width: 20px;
  height: 20px;
  border-radius: 50%;
}

/* Botões de login e registrar */
.login-btn, .register-btn {
  background-color: #333;
  border: none;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  margin-left: 1rem;
}

.login-btn:hover, .register-btn:hover {
  background-color: #ff9500;
}

/* Botão Books */
.books-btn {
  background-color: #ff9500;
  border: none;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 5px;
  cursor: pointer;
  margin-left: 1rem;
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

/* Responsividade */
@media (max-width: 768px) {
  .nav ul {
    display: none;
  }

  .menu-hamburger {
    display: flex;
  }

  .nav ul.menu {
    display: flex;
    flex-direction: column;
    position: absolute;
    background-color: #333;
    right: 0;
    top: 100%;
    padding: 1rem;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.23);
    border-radius: 10px;
  }

  .nav ul.menu li {
    margin-bottom: 0.5rem;
  }

  .nav ul.menu li a {
    color: white;
  }
}
</style>
