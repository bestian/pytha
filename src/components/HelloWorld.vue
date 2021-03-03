<template>
  <div class="hello">
    <h1>畢氏三組數產生器</h1>
    種子一: <input class="mod" type="number" name="" v-model="n1" minimum="1" />
    <br/>
    種子二: <input class="mod" type="number" name="" v-model="n2" minimum="1" />
    <hr/>
    <h3>直邊{{p2}}和{{p3}}與斜邊{{p1}}構成一個直角三角形</h3>
    <h3>{{p2}}<sup>2</sup> + {{p3}}<sup>2</sup> = {{p2**2}} + {{ p3**2 }} = {{ p2 ** 2 + p3 ** 2}} = {{ p1 }} <sup>2</sup></h3>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      n1: 2,
      n2: 1
    }
  },
  computed: {
    p1 () {
      return (this.n1 ** 2 + this.n2 ** 2)
    },
    p2 () {
      return (this.n1 ** 2 - this.n2 ** 2)
    },
    p3 () {
      return (2 * this.n1 * this.n2)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

label {
    display: block;
    font-size: .8rem;
}

input[type="number"] {
    font-size: 26px;
    position: relative;
    margin: 0 0 1rem;
    border: 1px solid #BBB;
    border-color: #BBB #ECECEC #ECECEC #BBB;
    padding: .2rem;
}

/* Spin Buttons modified */
input[type="number"].mod::-webkit-outer-spin-button, 
input[type="number"].mod::-webkit-inner-spin-button {
    -webkit-appearance: none;
    background: #FFF url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAJCAYAAADgkQYQAAAAKUlEQVQYlWNgwAT/sYhhKPiPT+F/LJgEsHv37v+EMGkmkuImoh2NoQAANlcun/q4OoYAAAAASUVORK5CYII=) no-repeat center center;
    width: 1em;
    border-left: 1px solid #BBB;
    opacity: .5; /* shows Spin Buttons per default (Chrome >= 39) */
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
}
input[type="number"].mod::-webkit-inner-spin-button:hover,
input[type="number"].mod::-webkit-inner-spin-button:active{
    box-shadow: 0 0 2px #0CF;
    opacity: .8;
}

/* Override browser form filling */
input:-webkit-autofill {
    background: black;
    color: red;
}

</style>
