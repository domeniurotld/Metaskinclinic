<template>
    <header class="header">
      <div class="row desktop-only align-items-center">
        <nav class="nav nav-right">
          <button class="tab-button" @click="goToRoute('/')">Acasă</button>
          <button class="tab-button" @click="scrollToSection('services')">Servicii</button>
          <button class="tab-button" @click="scrollToSection('prices')">Preturi</button>
          <button class="tab-button" @click="scrollToSection('contact')">Contact</button>
        </nav>
        <div class="col-auto logo">
          <!-- <img src="/assets/images/logo.png" alt="Logo" @click="goToRoute('/')"/> -->
        </div>
        <div class="row" style="display: flex; justify-content: end; margin-right: 9rem; width: 30%;">
          <a href="tel:+40740128833" style="width: auto;">
              <button class="tab-button" style="display: inline-flex; align-items: center; border:2px solid black; padding-top: 0.4rem; padding-bottom: 0.4rem;"> 
                  <Icon name="material-symbols:call" size="1.7rem" style="margin-right: 0.7rem;" /> 
                  <span>Contactați-ne</span>
              </button>
          </a>
        </div>
      </div>

      <div class="col mobile-only">
        <!-- <div class="logo" style="padding: 0;">
          <img src="/assets/images/logo.png" alt="Logo" @click="goToRoute('/')"/>
        </div> -->
        <nav class="nav nav-left" style="margin-top: 1rem; margin-bottom: 1rem;">
          <div style="display: flex; justify-content: center; width: 100%; gap: 1rem; padding: 0 1rem;">
            <button class="tab-button" style="width: 30%;" @click="goToRoute('/')">Acasă</button>
            <button class="tab-button" style="width: 30%;" @click="scrollToSection('services')">Servicii</button>
            <button class="tab-button" style="width: 30%;" @click="scrollToSection('prices')">Preturi</button>
            <button class="tab-button" style="width: 30%;" @click="scrollToSection('contact')">Contact</button>
          </div>
        </nav>
        <div class="row" style="display: flex; justify-content: center; margin-bottom: 1rem;">
          <a href="tel:+40740128833" style="width: auto;">
              <button class="tab-button" style="display: inline-flex; align-items: center; border:2px solid black; padding-top: 0.4rem; padding-bottom: 0.4rem;"> 
                  <Icon name="material-symbols:call" size="1.7rem" style="margin-right: 0.7rem;" /> 
                  <span>Contactați-ne</span>
              </button>
          </a>
        </div>
      </div>
    </header>
  </template>
  
<script>
  export default {
    methods: {
    goToRoute(route) {
      this.$router.push(route).then(() => {
        this.scrollToTop();
      });
    },
    goToHomeSection(section) {
      this.$router.push("/").then(() => {
        this.scrollToSection(section);
      });
    },
    goToHomeSection(section) {
      this.$router.push("/").then(() => {
        this.scrollToSection(section);
      });
    },
      scrollToSection(sectionId) {
        const section = document.getElementById(sectionId);
        if (section) {
          section.scrollIntoView({ behavior: 'smooth' });
        }
      },
      scrollToTop() {
        window.scrollTo({ top: 0, behavior: 'smooth' });
      }
    }
  }
  </script>
  
  <style scoped>
  
    .desktop-only {
      width:100%; 
      flex-direction:row; 
      display: flex;
    }
  
    .mobile-only {
      display: none; 
    }
  
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: auto;
    background: #adb5bd;
  }
  
  .logo {
    display: flex;
    height: 100px;
    align-items: center;
    margin-left: 9rem;
    width: 17%;
  }

  .logo img {
    height: 80px;
    cursor: pointer;
  }
  
  .nav {
    display: flex;
    gap: 1rem;
  }
  
  .nav-left {
    flex: 1;
    padding: 0 1.2rem;
  }
  
  .nav-right {
    flex: 1;
    justify-content: start;
    margin-left: 9rem;
  }
  
  .tab-button {
    width: auto;
    font-size: 22px;
    padding: 0px 16px;
    font-weight: 600;
    border: none;
    border-color: white;
    outline: none;
    color: black;
    background: transparent;
    text-shadow: 1px 1px 2px rgba(255, 255, 255, 0.5);
    border-radius: 10px;
    cursor: pointer;
    }

    .dropdown {
      position: relative;
      display: inline-block;
    }

    .dropdown-container {
      display: none;
      position: absolute;
      right: 0;
      background: transparent;
      z-index: 1;
    }
    .dropdown-content {
      background: linear-gradient(
        45deg,
        #e3dddd 5%,
        #fff 10%,
        #ccc 30%,
        #ddd 50%,
        #ccc 70%,
        #fff 80%,
        #bebebe 95%
      );
      min-width: 150px;
      box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
      border-radius: 5px;
      margin-top: 5px;
    }

    .dropdown-content a {
      color: black;
      padding: 5px 15px;
      text-decoration: none;
      display: block;
      font-weight: 600;
      border-radius: 5px;
      cursor: pointer;
      
    }

    .dropdown-content hr {
      margin: 0;
      height: 2px;
    }

    .dropdown-content a:hover {
      background-color: #000000;
      color: white;
      
    }

    .dropdown:hover .dropdown-container {
      display: block;
    }
  
  /* Responsive Design */
  @media (max-width: 768px) {
    .desktop-only {
      display: none;
    }
  
    .mobile-only {
      width: 100%; 
      display: flex; 
      flex-direction: column;
    }
  
    .header {
      flex-direction: column;
      align-items: center;
      padding: 0;
    }
  
    .nav {
      width: 100%;
    }
  
    .nav-left, .nav-right {
      align-items: center;
    }
  
    .tab-button {
      font-size: 1.1rem;
    }

    .logo {
      margin-left: 1rem;
      width: auto;
    }
  }
  </style>
  