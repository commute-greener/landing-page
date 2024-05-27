<script setup>
  import { ref } from 'vue'


  const burgerShow = ref(false);
  const mobileNav = ref(false);

</script>

<template>
  <div class="nav-wrapper">
      <nav class="navbar">
        <img src="/Logo/commute-black.png" alt="Company Logo">
        <div @click="burgerShow = !burgerShow; mobileNav = !mobileNav" :class="{ isActive: burgerShow }"  class="menu-toggle" id="mobile-menu">
          <span class="bar"></span>
          <span class="bar"></span>
          <span class="bar"></span>
        </div>
        <ul :class="{mobileNav: mobileNav}" class="nav nav-items">
          <li class="nav-item"><a href="#">Home</a></li>
          <li class="nav-item"><a href="#">About</a></li>
          <li class="nav-item"><a href="#">Work</a></li>
          <li class="nav-item"><a href="#">Careers</a></li>
        </ul>
      </nav>
  </div>
</template>

<style scoped>


    /* SETUP */
    .nav-wrapper {
    z-index: 100;
    position: relative;
    top: 0;
    width: 100%;
    background-color: var(--color-white) !important;
    }
    /* NAVIGATION */
    .navbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    overflow: hidden;
    height: 50px;
    padding: 10px 0;
    }

    .navbar img {
    width: auto;
    height: 32px;
    margin-left: 50px;
    justify-self: start;
    }

    .navbar ul {
    display: flex;
    gap: 20px;
    list-style: none;
    justify-content: space-evenly;
    justify-self: end;
    margin-right: 50px;
    }

    .nav-items {
    transform: translate(0);
    transition: transform 0.7s ease-in-out;
    }

    .nav-item a {
    color: var(--color-dark);
    padding: 0 10px;
    font-size: 1.3rem;
    font-weight: 400;
    text-decoration: none;
    transition: color .3s ease-out;
    }

    .nav-item a:hover {
    color: var(--color-red);
    }

    /* MOBILE MENU & ANIMATION */

    .menu-toggle .bar {
    width: 25px;
    height: 3px;
    margin: 5px auto;
    background-color: var(--color-dark);
            transition: all .3s ease-in-out;
    -webkit-transition: all .3s ease-in-out;
        -o-transition: all .3s ease-in-out;
    }

    .menu-toggle {
    display: none;
    margin-right: 25px;
    justify-self: end;
    }

    .menu-toggle:hover {
    cursor: pointer;
    }

    #mobile-menu.isActive .bar:nth-child(2) {
    opacity: 0;
    }

    #mobile-menu.isActive .bar:nth-child(1) {
    transform: translateY(8px) rotate(45deg);
    -webkit-transform: translateY(8px) rotate(45deg);
    -ms-transform: translateY(8px) rotate(45deg);
    -o-transform: translateY(8px) rotate(45deg);
    }

    #mobile-menu.isActive .bar:nth-child(3) {
    transform: translateY(-8px) rotate(-45deg);
    -webkit-transform: translateY(-8px) rotate(-45deg);
    -ms-transform: translateY(-8px) rotate(-45deg);
    -o-transform: translateY(-8px) rotate(-45deg);
    }

    /* Media Queries */
    /* Mobile Devices - Phones/Tablets */

    @media only screen and (max-width: 768px) {

    /* MOBILE NAVIGATION */
    .navbar ul {
        position: fixed;
        top: 55px;
        display: flex;
        flex-direction: column;
        justify-content: start;
        align-items: center;
        overflow: hidden;
        width: 100%;
        height: auto;
        text-align: center;
        background-color: var(--color-white);
        transform: translate(-110%);
        padding: 0;
    }

    .navbar li {
        padding: 10px;
        font-size: 1.3rem;
        border-bottom: 1px solid var(--color-dark);
        width: 100%;
    }

    .navbar li:hover {
        border-bottom: 1px solid var(--color-red);
    }

    .navbar li:first-child {
        margin-top: 20px;
    }

    .navbar li a {
        font-size: 1rem;
    }

    .menu-toggle,
    .bar {
        display: block;
        cursor: pointer;
    }

    .mobileNav {
        transform: translate(0%)!important;
    }
    }

</style>