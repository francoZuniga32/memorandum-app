<template>
  <div id="app">
    <Menu v-on:addMemo="addMemo" v-bind:esLogin="esLogin"></Menu>
    <router-view v-on:login="login" v-bind:data="data" />
  </div>
</template>
<script>
import Menu from '@/components/Menu.vue'
export default {
  components:{
    Menu
  },   
  data(){
    return{
      esLogin: false,
      usuario: null,
      data:[
        {
          "id":0,
          "fecha": "02/12/2020",
          "de": "Personal 1",
          "para": "Personal 2",
          "puesto"  : "encargado", 
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        },
        {
          "id":1,
          "fecha": "01/12/2020",
          "de": "Personal 2",
          "para": "Personal 3",
          "puesto"  : "secretario de recursos humanos",
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        },
        {
          "id":2,
          "fecha": "30/11/2020",
          "de": "Personal 1",
          "para": "Personal 3",
          "puesto"  : "secretario de direccion de soporte",
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        },
        {
          "id":3,
          "fecha": "29/11/2020",
          "de": "Personal 3",
          "para": "Personal 1",
          "puesto"  : "encargado de sistemas",
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        },
        {
          "id":4,
          "fecha": "28/11/2020",
          "de": "Personal 2",
          "para": "Personal 1",
          "puesto"  : "director de contabilidad",
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        }
      ]
    }
  },
  mounted(){
    console.log(this.esLogin);
  },
  methods: {
     login: function(usuario){
       this.usuario = usuario;
       this.esLogin = true;
     },
     addMemo: function(memo){
       if(this.usuario != null){
        memo.id = this.data.length;
        memo.de = this.usuario.usuario;
        memo.puesto = this.usuario.puesto;

        this.data.push(memo);
       }
     }
  }
}
</script>
