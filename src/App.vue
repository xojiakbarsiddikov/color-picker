<template>
    <div class="content">
        <div class="radio">
            <input type="checkbox" id="toggle" class="toggle-item">
            <label for="toggle"></label>
        </div>
        <color-picker v-bind="color" @input="onInput"/>
        <div class="color-wrap">
            <div class="color" @click="click" style="background: #00FFFF"></div>
            <div class="color" @click="click1" style="background: red"></div>
            <div class="color" @click="click2" style="background: #0000FF"></div>
            <div class="color" @click="click3" style="background: #BF00FF"></div>
            <div class="color" @click="click4" style="background: yellow"></div>
            <div class="color" @click="click5" style="background: orange"></div>
            <div class="color" @click="click6" style="background: #00FF00"></div>
            <div class="color" @click="click7" style="background: #8000FF"></div>
        </div>
        <input type="range" class="range" min="20" max="200" v-model="color.luminosity" id="weight">
        <input type="range"  class="range" min="20" max="200" v-model="color.saturation" id="weight">
        <h1 v-text="msg"></h1>
        <pre v-text="JSON.stringify(color, null, 4)"></pre>
    </div>

</template>

<script>
    import ColorPicker from '../src/ColorPicker.vue';

    export default {
        components: { ColorPicker },
        data() {
            return {
                color1: '',
                color: {
                    hue: 50,
                    saturation: 100,
                    luminosity: 50,
                    alpha: 1,
                },
            };
        },
        methods: {
            onInput(hue) {
                this.color.hue = hue;
            },
            click() {
                this.color.hue = 180
            },
            click1() {
                this.color.hue = 0
            },
            click2() {
                this.color.hue = 240
            },
            click3() {
                this.color.hue = 285
            },
            click4() {
                this.color.hue = 60
            },
            click5() {
                this.color.hue = 45
            },
            click6() {
                this.color.hue = 120
            },
            click7() {
                this.color.hue = 270
            },
        },
        mounted() {
            let inp = document.querySelector('.range')
            inp.addEventListener('input', () => {

            })
            let rcp__palette = document.querySelector('.rcp__palette')
            let rcp__well = document.querySelector('.rcp__well')
            let body = document.querySelector('#app')
            let h1 = document.querySelector('pre')
            let radio = document.querySelector('.toggle-item')
            let range = document.querySelector('.range')
            let js = document.querySelector('.js')
            let js1 = document.querySelector('.js1')
            let js2 = document.querySelector('.js2')
            let js3 = document.querySelector('.js3')
            let js4 = document.querySelector('.js4')
            let js5 = document.querySelector('.js5')
            let js6 = document.querySelector('.js6')
            let js7 = document.querySelector('.js7')

            radio.addEventListener('change', () => {
                body.classList.toggle('color1')
                h1.classList.toggle('color')
            })

            range.addEventListener('change', ()=> {
                rcp__palette.style.opacity = range.value
            })

            js.addEventListener('click', () => {
                rcp__palette.style.background = 'white'
                rcp__well.style.background = 'white'
            })
            js1.addEventListener('click', () => {
                rcp__palette.style.background = 'red'
                rcp__well.style.background = 'red'
            })
            js2.addEventListener('click', () => {
                rcp__palette.style.background = 'royalblue'
                rcp__well.style.background = 'royalblue'
            })
            js3.addEventListener('click', () => {
                rcp__palette.style.background = '#797474'
                rcp__well.style.background = '#797474'
            })
            js4.addEventListener('click', () => {
                rcp__palette.style.background = 'yellow'
                rcp__well.style.background = 'yellow'
            })
            js5.addEventListener('click', () => {
                rcp__palette.style.background = 'orange'
                rcp__well.style.background = 'orange'
            })
            js6.addEventListener('click', () => {
                rcp__palette.style.background = 'green'
                rcp__well.style.background = 'green'
            })
            js7.addEventListener('click', () => {
                rcp__palette.style.background = 'chartreuse'
                rcp__well.style.background = 'chartreuse'
            })
        }
    };
</script>
<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    color: #ffff;
}
#app {
    background: #000000;
    height: 99vh;
}
input {
    display: block;
    margin: 20px 0;
}
*,
*:before,
*:after{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
.color {
    color: #000!important;
}
.color1 {
    background: #ffffff !important;
}

.container{
    background-color: #ffffff;
    padding: 40px 30px;
    width: 50%;
    min-width: 400px;
    position: absolute;
    transform: translate(-50%,-50%);
    top: 50%;
    left: 50%;
    border-radius: 5px;
    font-family: 'Poppins',sans-serif;
    box-shadow: 25px 25px 30px rgba(0,0,0,0.15);
}
.row{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 40px;
}
.row span{
    font-weight: 500;
}
input[type="range"]{
    width: 70%;
    height: 3.5px;
    -webkit-appearance: none;
    appearance: none;
    background-color: #dcdcdc;
    border-radius: 3px;
    outline: none;
}

input[type="range"]::-webkit-slider-thumb{
    -webkit-appearance: none;
    appearance: none;
    height: 15px;
    width: 15px;
    background-color: #1c1c1c;
    border-radius: 50%;
    cursor: pointer;
}
#result{
    font-size: 30px;
    font-weight: 700;
    letter-spacing: 1px;
    text-align: center;
    color: #0be881;
}
#category{
    font-size: 18px;
    text-align: center;
    letter-spacing: 1px;
}

.toggle-item + label {
    display: flex;
    width: 5em;
    height: 2em;
    background: #aaa;
    border-radius: 50px;
    position: relative;
    transition: all .3s ease;
    cursor: pointer;
    box-shadow: inset 0 0 5px #222;
}
.toggle-item + label:after {
    content: '';
    position: absolute;
    width: 1.5em;
    height: 1.5em;
    background: #fff;
    border-radius: 50%;
    top: 0.25em;
    left: 0.25em;
    transition: all .2s ease;
}
.toggle-item:checked + label {
    background: #000;
}
.toggle-item:checked + label:after {
    left: 3.1em;
}

.btn[disabled] {
    cursor: not-allowed;
}

.fa-solid {
    cursor: pointer!important;
}

.btn-wrapper button {
    width: 200px;
    padding: 15px;
    border: none;
    border-radius: 3px;
    background: deepskyblue;
    margin: 10px 30px 30px;
}
#toggle {
    display: none;
}
.content {
    width: 15%;
    margin: 0 auto;
    padding: 70px 0;
}
@media(max-width: 500px) {
    input[type="range"] {
        width: 70%;
    }
    .content {
        width: 55%;
    }
}
</style>
