<body>

   <header>
       <img class="logo" src="image/moha.logo1.jpg" alt="Logo">
       <button id="abrir" class="abrir-menu"><i class="bi bi-list"></i></button>
       <nav class="nav" id="nav">
           <button class="cerrar-menu" id="cerrar"><i class="bi bi-x"></i></button>
           <ul class="nav-list">
               <li><a href="#">Inicio</a></li>
               <li><a href="#">productos</a></li>
               <li><a href="#">quienes somos</a></li>
               <li><a href="#">Contacto</a></li>
           </ul>
       </nav>
   </header>

   <script src="./js/main.js"></script>
</body>
</html>

css:

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: sans-serif;
}

header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 2rem;
    background-color: #151515;
}

.logo {
    max-width: 5rem;
}

.nav-list {
    list-style-type: none;
    display: flex;
    gap: 1rem;
}

.nav-list li a {
    text-decoration: none;
    color: greenyellow;
}

.abrir-menu,
.cerrar-menu {
    display: none;
}

@media screen and (max-width: 550px) {
    .abrir-menu,
    .cerrar-menu {
        display: block;
        border: 0;
        font-size: 1.25rem;
        background-color: transparent;
        cursor: pointer;
    }

    .abrir-menu {
        color: #1c1c1c;
    }

    .cerrar-menu {
        color: #ececec;
    }

    .nav {
        opacity: 0;
        visibility: hidden;
        display: flex;
        flex-direction: column;
        align-items: end;
        gap: 1rem;
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        background-color: #1c1c1c;
        padding: 2rem;
        box-shadow: 0 0 0 100vmax rgba(0, 0, 0, .5);
    }

    .nav.visible {
        opacity: 1;
        visibility: visible;
    }

    .nav-list {
        flex-direction: column;
        align-items: end;
    }

    .nav-list li a {
        color: #ecececec;
    }
}

java:

const nav = document.querySelector("#nav");
const abrir = document.querySelector("#abrir");
const cerrar = document.querySelector("#cerrar");

abrir.addEventListener("click", () => {
    nav.classList.add("visible");
})

cerrar.addEventListener("click", () => {
    nav.classList.remove("visible");
})
