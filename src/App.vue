<template>
  <div id="app">
    <Menu></Menu>
    <router-view v-bind:data="data"/>
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
      data:[
        {
          "id":0,
          "fecha": "02/12/2020",
          "de": "Personal 1",
          "para": "Personal 2",
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        },
        {
          "id":1,
          "fecha": "01/12/2020",
          "de": "Personal 2",
          "para": "Personal 3",
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        },
        {
          "id":2,
          "fecha": "30/11/2020",
          "de": "Personal 1",
          "para": "Personal 3",
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        },
        {
          "id":3,
          "fecha": "29/11/2020",
          "de": "Personal 3",
          "para": "Personal 1",
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        },
        {
          "id":4,
          "fecha": "28/11/2020",
          "de": "Personal 2",
          "para": "Personal 1",
          "cuerpo": "<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc metus tortor, hendrerit a bibendum nec, dictum ac turpis. Sed metus tortor, convallis at ante posuere, commodo venenatis mauris. Nulla finibus imperdiet massa eget rhoncus. Cras dolor tellus, aliquet eget est vitae, facilisis feugiat massa. Morbi ultrices eros ut ex auctor, vitae dignissim orci aliquam.</p><p>Vivamus et imperdiet augue, ac vestibulum neque. Praesent a nisl at eros consequat dapibus interdum non risus. In et leo in ante sagittis mollis. Ut dapibus vestibulum semper. Ut ornare, mi a mollis suscipit, ipsum nunc consequat mi, non mollis ipsum tortor non quam.</p>"
        }
      ]
    }
  }
}
</script>
