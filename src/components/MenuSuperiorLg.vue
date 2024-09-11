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
  justify-content:flex-start;
  align-items: center;
  padding: 0.2rem 1rem;
  box-shadow: 0px 1px 10px rgba(0, 0, 0, 0.5);
  color: white;
  font-family: Montserrat;
  flex-wrap: wrap;
  
}

/* Estilos para logo */
.header--logo {
  display: flex;
  align-items: center;
}

.logo-text {
  display: flex;
  flex-direction:column;
  font-family: Risque;
}

.logo-text span {
  font-size: 1.2rem;
  font-weight: bold;
  color: white;
  flex-wrap: wrap;
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
  gap: 0.1rem;
  margin-left: 2rem;
  align-items: center;
}

.nav ul li a {
  text-decoration: none;
  color: rgba(255, 255, 255, 0.329);
  font-size: 0.6rem;
  font-weight: bold;
  padding: 0.5rem 1rem;
}

.nav ul li a:hover {
  color: #FF8A00;
}

.home-btn {
  display: inline-flex; /* Mantém o ícone e o texto em linha */
  align-items: center; /* Centraliza verticalmente o ícone e o texto */
  justify-content: center; /* Centraliza horizontalmente */
  padding: 0.2rem 0.6rem; /* Ajuste para manter o botão compacto */
  background-color: #FF8A00; /* Fundo laranja */
  color: #000000; /* Texto preto */
  border-radius: 5px; /* Borda arredondada */
  font-weight: bold;
  font-size: 0.8rem; /* Fonte menor para compactação */
  text-decoration: none;
  border: none; /* Sem borda */
  gap: 0.3rem; /* Espaçamento entre o ícone e o texto */
}

.home-btn .home-icon {
  width: 16px; /* Tamanho do ícone ajustado */
  height: 16px;
  fill: #000000; /* Ícone preto */
}

.home-btn:hover {
  background-color: #e68400; /* Cor de fundo no hover */
}


/* Barra de pesquisa */
.search-bar {
  margin-left: 6.5rem;
  font-size: 0.6rem;
  padding: 0.4rem;
  border-radius: 5px;
  border: 1px solid #444;
  background-color: #333;
  color: rgb(0, 0, 0);
  outline: none;
  margin-right: 0.5rem;
}

/* Seletor de idioma */
.language-select {
  display: flex;
  align-items: center;
  gap: 0.2rem;
  padding: 0.5rem;
}

.language-select .flag {
  width: 30px;
  height: 20px;
}

/* Ícones e botões alinhados */
.header--right {
  display: flex;
  align-items: center;
  gap: 0.2rem;
}

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
  padding: 0.3rem 0.5rem;
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

@media (max-width: 768px) {
  .menu-hamburger {
    display: block;
   
  }

  .menu-hamburger span {
    background-color: white;
    display: block;
  }

  .nav ul {
    display: none;
  }

  .nav .menu {
    display: flex;
    flex-direction: column;
    position: absolute;
    background-color: rgba(255, 255, 255, 0.9);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.19), 0 6px 6px rgba(0, 0, 0, 0.23);
    border-radius: 10px;
    right: 0;
    text-align: right;
    padding: 10px 16px;
  }

  .nav .menu li {
    display: block;
    margin-top: 12px;
  }

  /* Oculta a barra de pesquisa e os botões de login/registro */
  .header--right {
    display: none;
  }

  /* Ajuste o tamanho do texto do logo */
  .logo-text span {
    font-size: 1.4rem;
  }

  .search-bar {
    width: 100%;
    margin: 0.5rem 0;
    font-size: 0.9rem;
  }

  .language-select .flag {
    width: 25px;
    height: 15px;
  }

  /* Tamanho reduzido do ícone de hambúrguer */
  .menu-hamburger span {
    width: 20px;
    height: 2.5px;
  }

  /* Ajustes no espaçamento */
  .logo-text {
    margin: 0 auto; /* Centraliza o logo em telas pequenas */
  }
  
  .header {
    flex-direction: column;
    align-items: flex-start;
  }

  .header--logo {
    justify-content: space-between;
    width: 100%;
  }
}

.home-btn {
    padding: 0.1rem 0.4rem; /* Reduz ainda mais o tamanho do botão em telas pequenas */
    font-size: 0.75rem; /* Fonte menor para telas pequenas */
    gap: 0.2rem; /* Reduz o espaçamento entre ícone e texto */
  }
  
  .home-btn .home-icon {
    width: 14px; /* Ícone menor em telas pequenas */
    height: 14px;
  }
</style>
