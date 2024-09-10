<script setup>
import { ref } from 'vue';
import CartPlus from 'vue-material-design-icons/CartPlus.vue';
import Account from 'vue-material-design-icons/Account.vue';
import Menu from 'vue-material-design-icons/Menu.vue';

const menuAberto = ref(false);
const toggleMenu = () => {
  menuAberto.value = !menuAberto.value;
};
</script>

<template>
  <header class="header">
    <div class="header--logo">
      <img src="@/assets/logo.png" alt="Epic Reads Logo" />
      <div class="logo-text">
      </div>
    </div>

    <nav class="nav">
      <ul :class="menuAberto ? 'menu' : ''">
        <li><a href="#">Home</a></li>
        <li><a href="#">Mais Informações</a></li>
        <li><a href="#">Redes Sociais</a></li>
      </ul>
    </nav>

    <div class="header--right">
      <input type="text" placeholder="Pesquisar" class="search-bar" />
      <select class="language-select">
        <option>PT</option>
        <option>EN</option>
      </select>
    
      <button class="books-btn">Books</button>
      <Menu class="menu-hamburger" @click="toggleMenu" />
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
}

.header--logo {
  display: flex;
}
 
  .header--logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.header--logo img {
  width: 120px;
}

.logo-text {
  display: flex;
  flex-direction: column;
}

.logo-text span {
  font-size: 1.5rem;
  font-weight: bold;
  color: #ff9500; /* Cor laranja do texto */
}

.logo-text small {
  font-size: 0.9rem;
  color: #fff;
}

/* Menu de navegação */
.nav ul {
  display: flex;
  list-style: none;
  gap: 2rem;
}

.nav ul li a {
  text-decoration: none;
  color: white;
  font-size: 1rem;
  font-weight: bold;
}

.nav ul li a:hover {
  color: #ff9500;
}

/* Ícones e barra de pesquisa */
.header--right {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.search-bar {
  padding: 0.5rem;
  border-radius: 5px;
  border: 1px solid #444;
  background-color: #333;
  color: white;
  outline: none;
}

.language-select {
  background-color: #444;
  color: white;
  border: none;
  padding: 0.5rem;
  border-radius: 5px;
}

.icon {
  color: white;
  cursor: pointer;
}

/* Botão de Books */
.books-btn {
  background-color: #ff9500;
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
  cursor: pointer;
  color: white;
}

/* Responsividade */
@media (max-width: 768px) {
  .nav ul {
    display: none;
  }

  .menu-hamburger {
    display: block;
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
