<template>
  <header class="header" id="home">
    <div class="container">
      <div class="row">

        <div class="header__content">

          <div class="header__content-desc">
            <h1 class="header__title">
              enjoy <span>reserved</span> overhead bin space
            </h1>

            <a href="#!" class="explore-link"
              >explore now <i class="far fa-arrow-right"></i
            ></a>
          </div>

        </div>

        <div class="header__booking-box" id="booking">

          <div class="header__booking-content">

            <div class="booking__dropdowns">
              <div class="booking__dropdown" v-for="(dropdown, idx) in dropdowns" :key="idx">
                <button class="dropdown-btn">
                  {{ dropdown.dropdownTitle }} <i class="fas fa-caret-down"></i>
                </button>

                <ul class="booking__dropdown-menu">
                  <li>
                    <a class="booking__dropdown-item" href="#!" v-for="(droplink, idx) in dropdown.dropdownLinks" :key="idx">{{ droplink }}</a>
                  </li>
                </ul>
              </div>
            </div>

            <div class="booking__flight-setup">

              <div class="flight-from-to-setup">
                <div class="flight-from-setup" :class="{change: changed }">
                  <p class="flight-setup-title">
                    {{ changed ? "to" : "from" }}
                  </p>
                  <p class="flight-direction">lax</p>
                  <p class="flight-address">
                    los angeles intl arpt, los Angeles
                  </p>
                </div>

                <button class="change-direction-btn" @click="changed = !changed">
                  <i class="far fa-exchange"></i>
                </button>

                <div class="flight-to-setup" :class="{change: changed }">
                  <p class="flight-setup-title">
                    {{ changed ? "from" : "to" }}
                  </p>
                  <p class="flight-direction">mia</p>
                  <p class="flight-address">miami intl,miami</p>
                </div>
              </div>

              <div class="flight-date-setup">
                <div v-for="(date, idx) in flightDate" :key="idx" :class="`${date.title}-date`">
                  <p class="date-title">{{ date.title }}</p>
                  <p class="flight-date">{{ date.flightDay }} {{ date.flightDateNum <= 9 ? `0${date.flightDateNum}` : date.flightDateNum }} {{ date.flightMonth }} <button class="calendar-btn"><i class="fas fa-calendar-alt"></i></button></p>
                  
                  <div class="prev-next-btns">
                    <button class="prev-btn" @click="date.flightDateNum >= 2 ? date.flightDateNum-- : ''">prev</button>
                    <button class="next-btn" @click="date.flightDateNum <= 30 ? date.flightDateNum++ : ''">next</button>
                  </div>
                </div>
              </div>

            </div>

            <a href="#!" class="add-require-link">add requirements</a>
          </div>

          <a href="#!" class="booking-link"
            >booking flights <i class="far fa-arrow-right"></i
          ></a>

        </div>
      </div>
    </div>

    <img :src="header[0].bgImg" alt="" class="header__bg-img" />
    <span class="bg-gradient"></span>
  </header>

</template>

<script>
export default {
  name: "Header",
  data() {
    return {
      header: [
        {
          bgImg: require("@/assets/images/header/bg.png"),
        },
      ],
      dropdowns: [
        {
          dropdownTitle: "round trip",
          dropdownLinks: ["action", "another action", "something else here"],
        },
        {
          dropdownTitle: "flight type",
          dropdownLinks: ["action", "another action", "something else here"],
        },
        {
          dropdownTitle: "person",
          dropdownLinks: ["action", "another action", "something else here"],
        },
      ],
      flightDate: [
        {
          title: 'departure',
          flightDay: 'fri',
          flightDateNum: 15,
          flightMonth: "oct"
        },
        {
          title: 'return',
          flightDay: 'tue',
          flightDateNum: 19,
          flightMonth: "oct"
        }
      ],
      changed: false,
    };
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  position: relative;

  .row {
    row-gap: 35px;
  }

  &__bg-img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    max-height: 750px;
    object-fit: cover;
    object-position: left;
  }

  .bg-gradient {
    width: 100%;
    height: 100%;
    max-height: 750px;
    position: absolute;
    top: 0;
    left: 0;
    background: linear-gradient(180deg, #eaf7f6 0%, #eaf7f6 100%);
    opacity: 0.6;
    z-index: 2;
  }

  &__content {
    width: 100%;
    z-index: 3;
    display: flex;
    justify-content: space-between;
    padding: 150px 0;

    &-desc {
      max-width: 600px;
      width: 100%;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      row-gap: 40px;

      .header__title {
        font-size: calc(30px + 35 * (100vw / 1920));
        color: var(--primary-color);
        font-weight: 500;
        line-height: 77px;
        text-transform: capitalize;

        & > span {
          color: var(--secondary-color);
          font-weight: 600;
        }
      }

      .explore-link {
        font-size: 17px;
        font-weight: 500;
        color: var(--primary-color);
        text-transform: capitalize;
        display: flex;
        align-items: center;
        column-gap: 5px;
        transition: 0.4s;
        
        & > i {
          font-size: 14px;
          padding-top: 3px;
          animation: movingLink 2s ease-in-out infinite;
        }
        
        &:hover {
          color: var(--secondary-color);
        }
      }
    }

    &-window {
      max-width: 360px;
      width: 100%;
      min-height: 450px;
      height: 100%;
      border: 15px solid #ffffff;
      box-shadow: inset 0px 0px 8px rgba(0, 0, 0, 0.25),
        0px 0px 10px rgba(0, 0, 0, 0.25);
      border-radius: 120px;
      overflow: hidden;
      
      & > img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: right;
      }
    }
  }

  &__booking-box {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    z-index: 3;
    transform: translateY(-40%);
  }

  &__booking-content {
    width: 100%;
    z-index: 3;
    background: #ffffff;
    box-shadow: 0px 30px 84px rgba(19, 10, 46, 0.08),
      0px 8px 32px rgba(19, 10, 46, 0.07), 0px 3px 14px rgba(19, 10, 46, 0.03),
      0px 1px 3px rgba(19, 10, 46, 0.13);
    border-radius: 12px;
    padding: 35px 30px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    row-gap: 20px;

    .booking__dropdowns {
      width: 100%;
      display: flex;
      column-gap: 15px;
      align-items: center;

      .booking__dropdown {
        width: max-content;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding-left: 5px;
        position: relative;

        & > button {
          padding: 5px;
          padding-left: 0;
          cursor: pointer;
          display: flex;
          align-items: center;
          column-gap: 8px;
          text-transform: capitalize;
          font-size: 15px;
          font-weight: 600;
          background: var(--third-color);
          border: none;
        }

        &-menu {
          width: max-content;
          position: absolute;
          top: 0;
          left: 0;
          transform: translateY(30px);
          display: flex;
          flex-direction: column;
          align-items: flex-start;
          background: var(--third-color);
          z-index: 3;
          border: solid 1px var(--text-color);
          box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.25);
          border-radius: 10px;
          overflow: hidden;
          opacity: 0;
          transition: .3s;

          & > li {
            width: 100%;
          }
        }

        &-item {
          width: 100%;
          display: block;
          padding: 5px 10px;
          font-size: 15px;
          color: var(--primary-color);
          font-weight: 600;
          transition: 0.2s;
          text-transform: capitalize;

          &:hover {
            background: var(--secondary-color);
            color: var(--third-color);
          }
        }
      }
    }

    .booking__flight-setup {
      width: 100%;
      display: flex;
      align-items: center;
      column-gap: 20px;

      .flight-from-to-setup {
        width: 100%;
        display: flex;
        column-gap: 5px;
        align-items: center;
        row-gap: 10px;

        .flight-from-setup,
        .flight-to-setup {
          max-width: 300px;
          min-width: 250px;
          width: 100%;
          padding: 15px 20px;
          display: flex;
          flex-direction: column;
          align-items: flex-start;
          row-gap: 5px;
          border: 1px solid #aaaaaa;
          border-radius: 10px;
          transition: 0.5s;
          background: var(--third-color);
          z-index: 4;

          .flight-setup-title {
            text-transform: uppercase;
            color: var(--text-color);
            font-weight: 600;
            font-size: 15px;
          }

          .flight-direction {
            color: var(--primary-color);
            text-transform: capitalize;
            font-weight: 600;
            font-size: 24px;
          }

          .flight-address {
            width: 100%;
            font-size: 15px;
            color: var(--text-color);
            font-weight: 600;
            text-transform: capitalize;
            overflow: hidden;
            white-space: nowrap;
            text-overflow: ellipsis;
          }
        }

        .flight-from-setup.change {
          transform: translateX(113%);
        }
          
        .flight-to-setup.change {
          transform: translateX(-113%);
        }

        .change-direction-btn {
          min-width: 30px;
          max-width: 30px;
          min-height: 30px;
          max-height: 30px;
          display: grid;
          place-items: center;
          border-radius: 50%;
          cursor: pointer;
          background: var(--third-color);
          font-size: 15px;
          color: var(--primary-color);
          border: 1px solid #aaaaaa;
          padding-top: 3px;
          z-index: 3;
        }
      }

      .flight-date-setup {
        max-width: 400px;
        width: 100%;
        display: flex;
        justify-content: space-between;
        column-gap: 20px;
        align-items: center;
        padding: 15px 20px;
        border: 1px solid #aaaaaa;
        border-radius: 10px;
        background: var(--third-color);
        
        .departure-date, 
        .return-date {
          width: 100%;
          display: flex;
          flex-direction: column;
          align-items: flex-start;
          row-gap: 2px;          
        }
        
        .date-title {
          font-size: 15px;
          text-transform: uppercase;
          color: var(--text-color);
          font-weight: 600;  
        }
        
        .flight-date {
          width: 100%;
          display: flex;
          column-gap: 3px;
          align-items: center;
          text-transform: capitalize;
          color: var(--primary-color);
          font-weight: 600;
          font-size: 24px;
        }
        
        .calendar-btn {
          border: none;
          background: var(--third-color);
          min-width: 25px;
          min-height: 25px;
          padding: 5px 6px;
          display: grid;
          place-items: center;
          border-radius: 50%;
          color: var(--primary-color);
          font-size: 18px;
          margin-left: 5px;
          cursor: pointer;
        }
        
        .prev-next-btns {
          display: flex;
          column-gap: 30px;
          align-items: center;
          
          & > button {
            border: none;
            background: var(--third-color);
            color: var(--text-color);
            font-size: 15px;
            text-transform: capitalize;
            font-weight: 500;
            cursor: pointer;
            padding: 3px 4px;
            outline: none;
            
            &:hover {
              text-decoration: underline;
            }
          }
        }
        
      }
    }
  }

  .booking-link {
    padding: 25px 30px;
    display: flex;
    align-items: center;
    column-gap: 30px;
    text-transform: capitalize;
    background: var(--secondary-color);
    border-radius: 10px;
    color: var(--third-color);
    transform: translateY(-45%);
    z-index: 4;
  }

  .add-require-link {
    font-size: 15px;
    color: var(--primary-color);
    text-transform: capitalize;
    text-decoration: underline;
    transition: 0.4s;
    font-weight: 500;

    &:hover {
      color: var(--secondary-color);
    }
  }

  .fade-enter-active,
  .fade-leave-active {
    transition: .4s ease-out;
  }

  .fade-enter-from,
  .fade-leave-to {
    opacity: 0;
  }

  .fade-enter-to,
  .fade-leave-from {
    opacity: 1;
  }

  .dropdown-btn:focus ~ .booking__dropdown-menu {
    opacity: 1;
    z-index: 6;
  }
}


@media (max-width: 1200px){
  .header__title {
    line-height: unset !important;
  }
}

@media (max-width: 1080px){

  .header {

    &__content {
      padding-bottom: 50px;
    }

    &__booking-box {
      transform: translateY(0);

      .booking__flight-setup {
        flex-direction: column;
        row-gap: 20px;
      }

      .flight-from-to-setup {
        justify-content: center;
      }
    }
  }

  
}
@media (max-width: 1024px){}
@media (max-width: 992px){
  .booking__dropdowns {
    justify-content: center;
  }
}
@media (max-width: 850px){}
@media (max-width: 768px){
  .booking-link {
    transform: translateY(-30%) !important;
  }
}
@media (max-width: 736px){}
@media (max-width: 734px){}
@media (max-width: 684px){
 .flight-from-to-setup {
    flex-direction: column;

    .flight-from-setup.change {
      transform: translateY(140%) !important;
    }

    .flight-to-setup.change {
      transform: translateY(-140%) !important;
    }

    .change-direction-btn {
      padding-top: 0 !important;
      padding-right: 3px;

      & i {
        transform: rotate(90deg);
      }
    }
 }
}
@media (max-width: 667px){}
@media (max-width: 576px){
  .booking__dropdowns {
    display: none !important;
  }
}
@media (max-width: 480px){
  .flight-date-setup {
    max-width: 300px !important;
    flex-direction: column;

    .departure-date,
    .return-date {
      max-width: max-content;
    }
  }
}
@media (max-width: 414px){}
@media (max-width: 412px){}
@media (max-width: 375px){}
@media (max-width: 360px){}
@media (max-width: 320px){
  .header__title {
    font-size: calc(30px + (35 + 35 * 0.7) * ((100vw - 320px)/ 1920));
  }
}

</style>
