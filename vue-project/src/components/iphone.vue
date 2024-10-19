<script setup>
import display from './display.vue';
import keypad from './keypad.vue';
import { reactive } from 'vue';

const data = reactive({
  hours: '',
})
setInterval(()=> {
  const now = new Date();
  const hours = now.getHours().toString().padStart(2, '0');
  const minutes = now.getMinutes().toString().padStart(2, '0');
  return data.hours = `${hours}:${minutes}`
}, 1000)

</script>

<template>
    <section class="iphoneMock">
    <div class="container">
      <div class="iphone">
        <div class="bordeColor">
          <div class="botones">
            <div class="switch"></div>
            <div class="vol up"></div>
            <div class="vol down"></div>
            <div class="touchID"></div>
          </div>
          <div class="bordeNegro">
            <div class="notch">
              <div class="bocina"></div>
              <div class="camara"></div>
            </div>
            <div class="mainScreen">
              <div class="statusBar">
                <div class="leftSide">
                  <div class="hours">{{ data.hours }}</div>
                  <div class="hora hidden"></div>
                  <div class="widgetPlus"></div>
                </div>
                <div class="rightSide">
                  <div class="signal mid"><i class="bar"></i></div>
                  <div class="datos">4G</div>
                  <div class="bateria mid"></div>
                  <div class="exitShake">Listo</div>
                </div>
              </div>
              <div class="calc">
                <display />
                <keypad />
                <div class="unlockBar"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!-- Créditos ao criador do código do Iphone  -->
  <!-- https://codepen.io/JorgeAguilar/pen/MWeXVZg -->
</template>

<style scoped>
.iphoneMock {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  align-content: center;
  width: 100%;
  min-height: 100vh;
}
.iphoneMock .container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  align-content: center;
  width: 90%;
  margin: 0 auto;
  padding: 50px 0;
  overflow: hidden;
}

.iphoneMock .container .iphone {
  width: 320px;
  height: 640px;
  border-radius: 45px;
  position: relative;
  user-select: none;
  transition: ease all 1s;
}

.iphoneMock .container .iphone:before, .iphoneMock .container .iphone:after {
  content: "";
  position: absolute;
  background-color: rgba(255, 255, 255, 0.1);
  width: 6px;
  height: 7px;
  z-index: 1;
}
.iphoneMock .container .iphone:before {
  top: 1px;
  right: 70px;
}
.iphoneMock .container .iphone:after {
  bottom: -1px;
  left: 70px;
}
.iphoneMock .container .iphone .bordeColor {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  align-content: center;
  height: 100%;
  width: 100%;
  background-color: #152839;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 0 3px 1px #494949;
  border-radius: 45px;
  position: relative;
}
.iphoneMock .container .iphone .bordeColor:before, .iphoneMock .container .iphone .bordeColor:after {
  content: "";
  position: absolute;
  top: 65px;
  background-color: rgba(255, 255, 255, 0.1);
  width: 7px;
  height: 6px;
  z-index: 1;
}
.iphoneMock .container .iphone .bordeColor:before {
  left: 0px;
}
.iphoneMock .container .iphone .bordeColor:after {
  right: 0px;
}
.iphoneMock .container .iphone .bordeColor .botones:before, .iphoneMock .container .iphone .bordeColor .botones:after {
  content: "";
  position: absolute;
  bottom: 65px;
  background-color: rgba(255, 255, 255, 0.1);
  width: 7px;
  height: 6px;
  z-index: 1;
}
.iphoneMock .container .iphone .bordeColor .botones:before {
  left: 0px;
}
.iphoneMock .container .iphone .bordeColor .botones:after {
  right: 0px;
}
.iphoneMock .container .iphone .bordeColor .botones > * {
  position: absolute;
  left: -3px;
  width: 3px;
  background: linear-gradient(90deg, transparent, #152839);
  border-radius: 20px 10px 10px 20px;
}
.iphoneMock .container .iphone .bordeColor .botones .touchID {
  top: 160px;
  right: -3px;
  left: auto;
  height: 80px;
  background: linear-gradient(90deg, #152839, transparent);
  border-radius: 10px 20px 20px 10px;
}
.iphoneMock .container .iphone .bordeColor .botones .switch {
  top: 100px;
  height: 25px;
}
.iphoneMock .container .iphone .bordeColor .botones .vol {
  top: 150px;
  height: 45px;
}
.iphoneMock .container .iphone .bordeColor .botones .vol.down {
  top: 210px;
}

.iphoneMock .container .iphone .bordeColor .bordeNegro {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  align-content: center;
  width: calc(100% - 14px);
  height: calc(100% - 14px);
  border-radius: 40px;
  background-color: #000;
  position: relative;
  overflow: hidden;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro:after {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-radius: 40px;
  border: 7px solid #000;
  box-sizing: border-box;
  pointer-events: none;
  z-index: 100;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  align-content: center;
  position: absolute;
  top: 0;
  width: 150px;
  height: 32px;
  border-bottom-left-radius: 17px;
  border-bottom-right-radius: 17px;
  background-color: #000;
  z-index: 100;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch:before, .iphoneMock .container .iphone .bordeColor .bordeNegro .notch:after {
  content: "";
  position: absolute;
  top: 0;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  border: 7px solid transparent;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch:before {
  left: -17px;
  border-right-color: #000;
  transform: rotate(-50deg);
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch:after {
  right: -17px;
  border-left-color: #000;
  transform: rotate(50deg);
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch .bocina {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: flex-start;
  align-content: center;
  width: 40px;
  height: 4px;
  border-radius: 20px;
  background-color: #1b1b1b;
  border: 0.7px solid #171717;
  box-shadow: inset 0px -0.3px 1px 0px #8c8c8c;
  position: relative;
  overflow: hidden;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch .bocina:before, .iphoneMock .container .iphone .bordeColor .bordeNegro .notch .bocina:after {
  content: "";
  position: absolute;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch .bocina:before {
  width: 0;
  height: 60%;
  transform: skew(-10deg);
  box-shadow: 1px 0 0px 0.2px #313131, 2px 0 0px 0.2px #313131, 3px 0 0px 0.2px #313131, 4px 0 0px 0.2px #313131, 5px 0 0px 0.2px #313131, 6px 0 0px 0.2px #313131, 7px 0 0px 0.2px #313131, 8px 0 0px 0.2px #313131, 9px 0 0px 0.2px #313131, 10px 0 0px 0.2px #313131, 11px 0 0px 0.2px #313131, 12px 0 0px 0.2px #313131, 13px 0 0px 0.2px #313131, 14px 0 0px 0.2px #313131, 15px 0 0px 0.2px #313131, 16px 0 0px 0.2px #313131, 17px 0 0px 0.2px #313131, 18px 0 0px 0.2px #313131, 19px 0 0px 0.2px #313131, 20px 0 0px 0.2px #313131, 21px 0 0px 0.2px #313131, 22px 0 0px 0.2px #313131, 23px 0 0px 0.2px #313131, 24px 0 0px 0.2px #313131, 25px 0 0px 0.2px #313131, 26px 0 0px 0.2px #313131, 27px 0 0px 0.2px #313131, 28px 0 0px 0.2px #313131, 29px 0 0px 0.2px #313131, 30px 0 0px 0.2px #313131, 31px 0 0px 0.2px #313131, 32px 0 0px 0.2px #313131, 33px 0 0px 0.2px #313131, 34px 0 0px 0.2px #313131, 35px 0 0px 0.2px #313131, 36px 0 0px 0.2px #313131, 37px 0 0px 0.2px #313131, 38px 0 0px 0.2px #313131, 39px 0 0px 0.2px #313131;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch .bocina:after {
  width: 95%;
  height: 0;
  box-shadow: 1px -0.8px 0px 0.2px #313131, 1px 0px 0px 0.2px #313131, 1px 0.8px 0px 0.2px #313131;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch .camara {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  align-content: center;
  position: absolute;
  right: 35px;
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background-color: #1b1b1b;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch .camara:before, .iphoneMock .container .iphone .bordeColor .bordeNegro .notch .camara:after {
  content: "";
  position: absolute;
  border-radius: 50%;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch .camara:before {
  width: calc(100% - 4px);
  height: calc(100% - 4px);
  background: radial-gradient(#000, #152839 60%);
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .notch .camara:after {
  width: 4px;
  height: 4px;
  margin-top: 2px;
  margin-right: 2px;
  background-color: rgba(255, 255, 255, 0.1);
}

.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen {
  background-color: #000;
  width: calc(100% - 14px);
  height: calc(100% - 14px);
  border-radius: 32px;
  position: relative;
  overflow: hidden;
}

.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  align-content: center;
  height: 20px;
  padding: 5px 20px 0px 20px;
  padding-right: 12px;
  position: relative;
  z-index: 1;
}

.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .leftSide {
  color: #fff;
  font-size: 10px;
  text-transform: uppercase;
  position: relative;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: flex-end;
  align-content: center;
  position: relative;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .signal {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  align-content: center;
  width: 18px;
  height: 10px;
  position: relative;
  overflow: hidden;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .signal:before, .iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .signal:after {
  content: "";
  position: absolute;
  bottom: 0;
  width: 3px;
  border-radius: 5px;
  background-color: #fff;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .signal:before {
  right: 0;
  height: 100%;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .signal:after {
  right: 4px;
  height: 80%;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .signal .bar:before, .iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .signal .bar:after {
  content: "";
  position: absolute;
  bottom: 0;
  width: 3px;
  border-radius: 5px;
  background-color: #fff;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .signal .bar:before {
  right: 8px;
  height: 60%;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .signal .bar:after {
  right: 12px;
  height: 40%;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .datos {
  margin: 0 3px;
  color: #fff;
  font-size: 10px;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .bateria {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  align-content: center;
  width: 15px;
  height: 8px;
  border-radius: 2px;
  border: 1px solid rgba(255, 255, 255, 0.5);
  position: relative;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .bateria.mid:after {
  width: 50%;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .bateria.low:after {
  width: 20%;
  background-color: #ffe600;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .bateria:before, .iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .bateria:after {
  content: "";
  position: absolute;
  background-color: #fff;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .bateria:before {
  right: -2px;
  width: 2px;
  height: 50%;
  border-top-right-radius: 1px;
  border-bottom-right-radius: 1px;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .bateria:after {
  left: 1px;
  width: 100%;
  height: 6px;
  border-radius: 1px;
  max-width: calc(100% - 2px);
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .statusBar .rightSide .exitShake {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  align-content: center;
  position: absolute;
  top: 0;
  right: 0;
  width: 40px;
  height: 17px;
  font-size: 10px;
  font-weight: 600;
  border-radius: 20px;
  background-color: rgba(255, 255, 255, 0.5);
  transform: scale(0);
  overflow: hidden;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .calc {
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  align-items: center;
  justify-content: end;
  align-content: center;
  position: absolute;
  width: 100%;
  height: calc(100% - 25px);
  padding: 30px 0 30px 0;
  box-sizing: border-box;
}
.iphoneMock .container .iphone .bordeColor .bordeNegro .mainScreen .calc .unlockBar {
  position: absolute;
  bottom: 8px;
  width: 40%;
  height: 4px;
  border-radius: 20px;
  background-color: rgba(255, 255, 255, 0.7);
  opacity: 1;
}
</style>