<template>
  <div class="nav-contain">
    <div id="navbar" class="navbar">
      <!-- <img class="logo" src="../assets/logo.svg" alt="logo"> -->
      <span class="logo">codesthetics</span>
    </div>
    <div id="social" class="social">
      <ul>
        <li class="social-link" @click="menuClick()"><a href="https://www.facebook.com/tenysonpartridge">Facebook</a></li>
        <li class="social-link" @click="menuClick()"><a href="https://www.instagram.com/tenyson11">Instagram</a></li>
        <li class="social-link" @click="menuClick()"><a>Twitter</a></li>
        <li class="social-link" @click="menuClick()"><a>Github</a></li>
        <li @click="menuClick()" class="social-dropdown">Menu</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isActive: false
    }
  },
  methods: {
    menuClick(){
      var myMenu = document.querySelector('.social');
      if (this.isActive === false) {
        myMenu.style.transform = "translateY(36%)";
        this.isActive = true;
      } else {
        myMenu.style.transform = "translateY(-42%)";
        this.isActive = false;
      }
    }
  },
  mounted() {
    var prevScroll = window.pageYOffset;
    window.onscroll = function() {
      var currPosition = window.pageYOffset;
      if (prevScroll > currPosition) {
        document.getElementById('navbar').style.transform = "translateY(0%)";
        document.getElementById('social').style.transform = "translateY(-42%)";
      } else if (prevScroll < currPosition) {
        document.getElementById('navbar').style.transform = "translateY(-200%)";
        document.getElementById('social').style.transform = "translateY(-400%)";
      }
      prevScroll = currPosition;
    }
  }
}
</script>

<style lang="scss">

@keyframes slideInTop {
  0% {
    transform: translateY(-100%);
  }
  100% {
    transform: translateY(0%);
  }
}

  .navbar {
    display: flex;
    position: fixed;
    margin-left: auto;
    margin-right: auto;
    border-left: 3px solid white;
    border-right: 3px solid white;
    left: 0;
    right: 0;
    justify-content: center;
    align-items: center;
    background: #333;
    width: 30rem;
    height: 6rem;
    border-radius: 0 0 1000px 1000px;
    box-shadow: 0 3px 6px rgba(0, 0, 0, .16);
    z-index: 20;
    transition: all .65s cubic-bezier(0.175, 0.885, 0.32, 1.5);
    -webkit-transition: all .65s cubic-bezier(0.175, 0.885, 0.32, 1.5);
    animation-name: slideInTop;
    animation-duration: .45s;
    animation-timing-function: cubic-bezier(0.175, 0.885, 0.32, 1.5);
    -webkit-animation-name: slideInTop;
    -webkit-animation-duration: .45s;
    -webkit-animation-timing-function: cubic-bezier(0.175, 0.885, 0.32, 1.5);
    @media (max-width: 600px) {
      width: 100%;
    }
    .logo {
      color: white;
      font-size: 3rem;
      font-family: 'Courier New', Courier, monospace;
    }
  }
  .social {
    display: absolute;
    position: fixed;
    background-color: rgba(51, 51, 51, 1);
    border-radius: 0 0 20px 20px;
    top: 0;
    right: 0;
    left: 0;
    margin-left: auto;
    margin-right: auto;
    width: 100px;
    transform: translateY(-42%);
    z-index: 10;
    height: 160px;
    overflow: hidden;
    box-shadow: 0 3px 6px rgba(0, 0, 0, .16);
    transition: all .65s ease;
    -webkit-transition: all .65s ease;
    ul {
      display: flex;
      flex-direction: column;
      align-content: flex-end;
      height: 100%;
      li {
        display: flex;
        justify-content: center;
        align-items: center;
        // padding: 8px;
        width: 100%;
        height: 100%;
        border-top: 1px solid rgba(242, 242, 242, .35);
        color: white;
        &:hover {
          background: #444;
          cursor: pointer;
        }
        &:active {
          background: rgb(75, 75, 75);
        }
        a {
          position: relative;
          font-family: 'muliregular', sans-serif;
          color: white;
          font-size: 1.05rem;
          text-transform: uppercase;
          letter-spacing: 1px;
          text-decoration: none;

        }
        a:before {
          content: "";
          position: absolute;
          width: 100%;
          height: 1px;
          bottom: -5px;
          left: 0;
          background-color: white;
          visibility: hidden;
          -webkit-transform: scaleX(0);
          transform: scaleX(0);
          -webkit-transition: all 0.3s ease-in-out 0s;
          transition: all 0.3s ease-in-out 0s;
        }

        a:hover:before {
          visibility: visible;
          -webkit-transform: scaleX(1);
          transform: scaleX(1);
        }
      }
      .social-dropdown {
        // font-weight: bold;
        position: relative;
        font-family: 'muliregular', sans-serif;
        color: white;
        font-size: 1.4rem;
        text-transform: uppercase;
        letter-spacing: 1px;
      }
    }
  }
</style>
