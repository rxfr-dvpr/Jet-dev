<template>
   <nav class="nav">
      <div class="container">
         <div class="row">
            
            <a href="" class="logo">
               <img :src="logoImg" alt="" class="logo-img">
            </a>
            
            <div class="nav__collapse" :class="{'nav__opened': mobileActive}">
               <ul class="nav__list">
                  <li class="nav__list-item" v-for="(link, idx) in navLinks" :key="idx"><a :href="`#${link}`" class="nav__list-link">{{ link }}</a></li>
               </ul>

               <div class="nav__links">
                  <a href="#!" class="register-link">register</a>
                  <a href="#!" class="sign-link">sign in</a>
               </div>
            </div>
            
            <button class="nav__collapse-btn" @click="navBtnClick" :class="{nav__opened: mobileActive}">
               <span class="nav-btn-line"></span>
               <span class="nav-btn-line"></span>
               <span class="nav-btn-line"></span>
            </button>

         </div>
         
      </div>
   </nav>
</template>

<script>

export default {
   name: "Nav", 
   data() {
      return {
         logoImg: require('@/assets/images/logo.svg'),
         navLinks: [
            "home", 
            "booking", 
            "private jet", 
            "specification", 
            "luxury charters",
            "membership"
         ],
         mobileActive: false
      }
   },
   methods: {
      navBtnClick() {
         this.mobileActive = !this.mobileActive
      }
   }
}

</script>

<style lang="scss" scoped>
.nav {
   width: 100%;
   background: transparent;
   padding: 35px 0;
   position: fixed;
   top: 0;
   left: 0;
   z-index: 999;
   background: transparent;
   backdrop-filter: blur(50px);
   
   .row {
      align-items: center;
      justify-content: space-between;
   }

   .logo {
      max-width: 130px;
      width: 100%;
      display: grid;
      place-items: center;

      img {
         width: 100%;
      }
   }

   
   &__collapse {
      max-width: 850px;
      width: 100%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      column-gap: 15px;
   }

   &__list {
      max-width: max-content;
      width: 100%;
      display: flex;
      column-gap: 20px;
      align-items: center;

      &-link {
         font-size: 15px;
         color: var(--primary-color);
         font-weight: 500;
         text-transform: capitalize;
         transition: .3s;

         &:hover {
            color: var(--secondary-color);
         }
      }
   }

   .nav__links {
      max-width: max-content;
      width: 100%;
      display: flex;
      column-gap: 20px;
      align-items: center;

      .register-link {
         font-size: 15px;
         color: var(--primary-color);
         font-weight: 500;
         text-transform: capitalize;
         transition: .4s;

         &:hover {
            color: var(--secondary-color);
         }
      }

      .sign-link {
         font-size: 15px;
         color: var(--third-color);
         font-weight: 500;
         text-transform: capitalize;
         background: var(--secondary-color);
         padding: 5px 20px;
         border-radius: 5px;
      }
   }

   &__collapse-btn {
      display: none;
   }
}

@media (max-width: 1070px){

.nav {
   padding: 15px 0;

   &__collapse {
      max-width: max-content;
      position: fixed;
      top: 0;
      right: 0;
      flex-direction: column;
      align-items: flex-end;
      justify-content: center !important;
      height: 100vh;
      row-gap: 15px;
      padding: 15px;
      padding-top: 70px;
      z-index: 20021;
      background: var(--third-color);
      overflow-y: auto;
      box-shadow: -10px 0px 15px rgba($color: #000000, $alpha: 0.2);
      transition: .4s;
      transform: translateX(120%);

      &.nav__opened {
         transform: translateX(0);
      }
   }

   &__list {
      flex-direction: column;
      align-items: flex-end;
      row-gap: 10px;
   }

   &__links {
      flex-direction: column;
      align-items: flex-end;
      row-gap: 10px;
   }

   &__collapse-btn {
      display: flex;
      flex-direction: column;
      align-items: flex-end;
      justify-content: center;
      width: 40px;
      height: 40px;
      row-gap: 4px;
      border: none;
      background: transparent;
      border-radius: 50%;
      padding: 5px;
      overflow: hidden;
      z-index: 20222;

      .nav-btn-line {
         width: 100%;
         height: 3px;
         background: var(--secondary-color);
         border-radius: 6px;
         transition: .4s;
      }

      .nav-btn-line:last-of-type {
         width: 60%;
      }

      .nav-btn-line:nth-of-type(2) {
         width: 80%;
      }

      &.nav__opened {
         .nav-btn-line:last-of-type {
            width: 100%;
         }

         .nav-btn-line:nth-of-type(2) {
            width: 100%;
         }
      }
   }
}

}

@media (max-width: 1024px){}
@media (max-width: 992px){}
@media (max-width: 850px){}
@media (max-width: 768px){}
@media (max-width: 736px){}
@media (max-width: 734px){}
@media (max-width: 684px){}
@media (max-width: 667px){}
@media (max-width: 576px){}
@media (max-width: 480px){}
@media (max-width: 414px){}
@media (max-width: 412px){}
@media (max-width: 375px){}
@media (max-width: 360px){}
@media (max-width: 320px){}

</style>