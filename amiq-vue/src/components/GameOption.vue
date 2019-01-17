<template>
  <span class="amiq-option" :data-card="`${1}`" :data-showoption="`${showNum}`">
    {{num}}
  </span>
</template>

<script>
export default {
  name: 'GameOption',
  props: {
    order: Number,
    putNum: Number,
    putOrder: Number,
    showNum: false,
  },
  mounted(){
    if( {order} == {putNum}) {
        this.showNum = true;
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .amiq-option {
        display: block;
        width: 100%;
        height: 100%;
        background: url(../assets/game/card_pattern.svg) no-repeat;
        background-size: calc(14.5vh * 6);
        border-radius: 1vh;
        /* opacity: 0; */
    }
    .amiq-option[data-showoption="1"] {
        background-position: calc( -14.5vh * 0) 100%;
        opacity: 1;
    }
    .amiq-option[data-showoption="2"] {
        background-position: calc( -14.5vh * 1) 100%;
    }
    .amiq-option[data-showoption="3"] {
        background-position: calc( -14.5vh * 2) 100%;
    }
    .amiq-option[data-showoption="4"] {
        background-position: calc( -14.5vh * 3) 100%;
    }
    .amiq-option[data-showoption="5"] {
        background-position: calc( -14.5vh * 4) 100%;
    }
    .amiq-option[data-showoption="6"] {
        background-position: calc( -14.5vh * 5) 100%;
    }
    .amiq-option[data-showoption="7"] {
        background-position: calc( -14.5vh * 0) 0;
    }
    .amiq-option[data-showoption="8"] {
        background-position: calc( -14.5vh * 1) 0;
    }
    .amiq-option[data-showoption="9"] {
        background-position: calc( -14.5vh * 2) 0;
    }
    .amiq-option[data-showoption="10"] {
        background-position: calc( -14.5vh * 3) 0;
    }
    .amiq-option[data-showoption="11"] {
        background-position: calc( -14.5vh * 4) 0;
    }
    .amiq-option[data-showoption="12"] {
        background-position: calc( -14.5vh * 5) 0;
    }
</style>
