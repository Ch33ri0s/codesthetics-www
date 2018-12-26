<template>
  <div class="home">
    <Navbar/>
    <div class="home-wrapper">
      <div class="cover-wrapper">
        <div class="header-block">
          <h1>TENYSON PARTRIDGE</h1>
          <h3>UI/UX DEVELOPER</h3>
          <div class="tagline">It's my lifestyle because it's my passion.</div>
        </div>
        <img class="screen" src="../assets/screen.svg" alt="desktop-pc">
        <span class="background-text">&lt;/&gt;</span>
      </div>
      <div class="technologies-wrapper">
        <div class="content-block">
          <h2>Technologies</h2>
          <div class="tech-icon-wrapper">
            <img class="tech-icon" src="../assets/html5.svg" alt="html5-icon">
            <img class="tech-icon" src="../assets/css3.svg" alt="css3-icon">
            <img class="tech-icon" src="../assets/vuejs.svg" alt="vuejs-icon">
            <img class="tech-icon" src="../assets/react.svg" alt="react-icon">
            <img class="tech-icon" src="../assets/node-js.svg" alt="nodejs-icon">
            <img class="tech-icon" src="../assets/github.svg" alt="github-icon">
          </div>
        </div>
      </div>
      <div class="grid-gallery">
        <div class="grid-item"></div>
        <div class="grid-item"></div>
      </div>
      <div class="grid-gallery">
        <div class="grid-item"></div>
        <div class="grid-item"></div>
      </div>
      <div class="grid-gallery">
        <div class="grid-item"></div>
        <div class="grid-item"></div>
      </div>
    </div>
    <Footer/>
  </div>
</template>

<script>
import Navbar from './Navbar.vue';
import Footer from './Footer.vue';

export default {
  name: 'Home',
  components: {
    Navbar,
    Footer
  }
}
</script>

<style lang="scss">
@import '../fonts/fonts.css';
  .home {
    width: 100%;
    height: 100%;
    overflow: hidden;
    z-index: 0;
  }

  .home-wrapper {
    background: linear-gradient(to bottom, #4E00FF, #99FAFF, #00CEFF);
    width: 100%;
    position: relative;
    max-width: 100%;
    height: 200rem;
    overflow: hidden;
    z-index: 0;
    .cover-wrapper {
      display: flex;
      position: relative;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 60rem;
      overflow: hidden;
      z-index: 0;
      .header-block {
        color: white;
        z-index: 1;
        @media (max-width: 600px) {
          padding: 4rem;
        }
        h1 {
          font-family: 'Courier New', Courier, monospace;
          letter-spacing: 1.8px;
          font-size: 4.8rem;
          font-weight: bold;
          text-align: right;
        }
        h3 {
          font-family: 'Courier New', Courier, monospace;
          letter-spacing: 1.6px;
          text-align: right;
          font-size: 4rem;
          font-weight: 500;
          border-bottom: 1.8px solid;
          border-image: linear-gradient(to right, transparent, rgb(245, 245, 245)) 10;
          padding-bottom: 5rem;
        }
        .tagline {
          padding-top: 5rem;
          font-family: 'muliregular', sans-serif;
          font-size: 2.8rem;
          letter-spacing: 1.2px;
          text-align: right;
        }
        @media (max-width: 600px) {
          h1 {
            font-size: 3.6rem;
          }
          h3 {
            font-size: 2.8rem;
          }
          .tagline {
            font-size: 1.8rem;
          }
        }
      }
      .screen {
        position: sticky;
        top: 0;
        right: 0;
        left: 0;
        z-index: 1;
        align-self: center;
        margin-left: 15rem;
        width: 30rem;
        height: 30rem;
        @media (max-width: 600px) {
          display: none;
        }
      }
      .background-text {
        font-size: 80rem;
        position: fixed;
        z-index: 0;
        right: 0;
        left: 0;
        top: 0;
        margin-left: auto;
        margin-right: auto;
        -moz-user-select: -moz-none;
        -khtml-user-select: none;
        -webkit-user-select: none;
        color: rgba(0, 0, 0, .025);
        font-family: 'Courier New', Courier, monospace;
        font-weight: bolder;
        @media (max-width: 600px) {
          font-size: 40rem;
          transform: translateX(-50%);
        }
      }
    }
    .technologies-wrapper {
      display: flex;
      position: relative;
      justify-content: center;
      text-align: center;
      align-items: center;
      background: white;
      box-shadow: 3px 6px 20px rgba(0, 0, 0, .16);
      z-index: 1;
      width: 100%;
      height: 300px;
      h2 {
        font-family: 'Courier New', Courier, monospace;
        font-size: 4rem;
        color: #333;
        border-bottom: 1.8px solid;
        border-image: linear-gradient(to right, transparent, rgb(220, 220, 220), transparent) 10;
        padding-bottom: 5rem;
        z-index: 1;
        text-transform: uppercase;
        @media (max-width: 600px) {
          font-size: 2.8rem;
        }
      }
      .tech-icon-wrapper {
        display: flex;
        position: relative;
        padding-top: 5rem;
        z-index: 1;
        .tech-icon {
          width: 65px;
          height: 65px;
          padding-left: 1.5rem;
          padding-right: 1.5rem;
          &:hover {
            cursor: pointer;
            transform: scale(1.1, 1.1);
          }
        }
      }
    }
    .grid-gallery {
      display: flex;
      position: relative;
      justify-content: center;
      align-items: center;
      margin-top: 5rem;
      margin-bottom: 5rem;
      width: 100%;
      height: 36rem;
      @media (max-width: 600px) {
        flex-direction: column;
      }
      .grid-item {
        position: relative;
        border-radius: 2rem;
        margin: 2rem;
        width: 40rem;
        height: 30rem;
        background-color: rgba(255, 255, 255, 1);
        @media (max-width: 600px) {
          width: 15rem;
          height: 15rem;
        }
      }
    }
  }
</style>
