<template>
  <div class="nav-contain">
    <div id="navbar" class="navbar">
      <!-- <img class="logo" src="../assets/logo.svg" alt="logo"> -->
      <span class="logo">codesthetics</span>
    </div>
    <div id="social" class="social">
      <ul>
        <li @click="menuClick()"><a>Facebook</a></li>
        <li @click="menuClick()"><a>Instagram</a></li>
        <li @click="menuClick()"><a>Twitter</a></li>
        <li @click="menuClick()"><a>Github</a></li>
        <li @click="menuClick()" class="dropdown"><a><icon style="font-size: 1.3rem" class="dropdown-icon" icon="caret-down"/> Social</a></li>
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
      var myIcon = document.querySelector('.dropdown-icon');
      if (this.isActive === false) {
        myMenu.style.transform = "translateY(40%)";
        myIcon.style.transform = "rotate(180deg)";
        this.isActive = true;
      } else {
        myMenu.style.transform = "translateY(-42%)";
        myIcon.style.transform = "rotate(0deg)";
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
    animation-name: slideInTop;
    animation-duration: .45s;
    animation-timing-function: cubic-bezier(0.175, 0.885, 0.32, 1.5); 
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
    width: 10rem;
    transform: translateY(-42%);
    z-index: 10;
    height: 15rem;
    overflow: hidden;
    box-shadow: 0 3px 6px rgba(0, 0, 0, .16);
    transition: all .45s ease;
    ul {
      li {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: .8rem;
        border-bottom: 1px solid;
        border-image: linear-gradient(to right, transparent, rgb(245, 245, 245), transparent) 10;
        width: 100%;
        height: 100%;
        color: white;
        &:hover {
          background: #444;
          cursor: pointer;
        }
        &:active {
          background: rgb(75, 75, 75);
        }
        a {
          font-family: 'muliregular', sans-serif;
          color: white;
          font-size: 1.05rem;
          text-transform: uppercase;
          letter-spacing: 1px;
        }
      }
    }
  }
</style>
