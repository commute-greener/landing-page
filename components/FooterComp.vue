<script setup>

</script>

<template>

    <div class="footer">
        <ul>
        <li id="hand" class="footerItem">
            <p>👋</p>
        </li>
        <li class="footerItem">
            <a href="">Twitter</a>
        </li>
        <li class="footerItem">
            <a href="">Instagram</a>
        </li>
        <li class="footerItem">
            <a href="">Facebook</a>
        </li>
        <li class="footerItem">
            <a href="mailto:">Email</a>
        </li>
        </ul>
        <span>©2024. | Designed By: Antoine Muneret & Alon Ishay. | All rights reserved.</span>
    </div>

</template>

<style scoped>

.footer {
    display: flex;
    flex-direction: column;
    height: fit-content;
    align-content: center;
    justify-content: center;
    align-items: center;
    padding: 2vh 0;
    width: 100%;
    background-color: var(--color-white);
  }

  .footer p {
    margin: 0;
    padding: 0;
  }

  .footer ul {
    display: flex;
    gap: 20px;
    list-style: none;
    list-style-type: none;
    justify-content: space-evenly;
    justify-self: end;
    padding: 0;
  }

  .footer li, a {
    --border-color: var(--color-white);
    --border-width: 2px;
    --bottom-distance: 1px;

    display: inline-block;
    text-decoration: none;
    color: var(--color-dark);
    background-image: linear-gradient(var(--border-color), var(--border-color));
    background-size: 0% var(--border-width);
    background-repeat: no-repeat;
    background-position: 50% calc(100% - var(--bottom-distance));
    transition: background-size 0.3s;
    margin: 5px 0;
  }

  .footer li:hover {
    background-size: 100% var(--border-width);
  }

  .footerItem {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 5px;
  }

  #hand {
   font-size: 24px;
   margin: 0;
   padding: 0;
   background: none;
  }

  .footer #hand p {
    animation: wave-animation .3s infinite;
  }

  .footer span {
    font-size: 12px;
    color: var(--color-dark);
    text-align: center;
  }
   
  @keyframes wave-animation {
    0%,
    100% {
      transform: rotate(0deg);
    }
    25% {
      transform: rotate(20deg);
    }
    75% {
      transform: rotate(-15deg);
    }
  }

</style>


