<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <div class="container-fluid">
            <a class="navbar-brand">Memorandum App</a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse text-center" id="navbarNavAltMarkup">
                <ul class="navbar-nav mr-auto">
                    <li class="nav-item">
                        <router-link class="nav-link" to="/">Home</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link class="nav-link" to="/memorandum">Memorandum</router-link>
                    </li>
                </ul>
                <form class="form-inline my-2 my-lg-0">
                    <router-link type="button" to="/login" class="btn btn-primary my-2 my-sm-0">ingresar</router-link>
                    <button v-if="esLogin" type="button" class="btn btn-primary my-2 my-sm-0" data-toggle="modal" data-target="#exampleModal2">agregar</button>
                </form>

                <!-- modal -->
                <div class="modal fade" id="exampleModal2" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
                    <div class="modal-dialog">
                        <div class="modal-content">
                            <div class="modal-header">
                                <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
                                <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                                <span aria-hidden="true">&times;</span>
                                </button>
                            </div>
                            <div class="modal-body">
                            <form action="" class="form">
                                    <div class="form-group">
                                        <label for="para">Para</label>
                                        <input v-model="para" type="email" class="form-control" id="usuario">
                                    </div>
                                    <div class="form-group">
                                        <label for="cuerpo">Cuerpo</label>
                                        <textarea v-model="cuerpo" class="form-control" id="cuerpo" rows="3"></textarea>
                                    </div>
                                </form>
                            </div>
                            <div class="modal-footer">
                                <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                                <button type="button" class="btn btn-primary" v-on:click="addMemo" data-dismiss="modal">Agregar Memorandum</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>
<script>
//import axios from "axios";

export default {
    menu: "menu",
    props:{
        esLogin: Boolean,
    },
    data() {
        return {
            para: null,
            cuerpo: null,
        }
    },
    mounted(){
        console.log(this.esLogin);
    },
    methods:{
        addMemo: function(){
            let date = new Date();
            let fecha = this.format(date.getDay(), 2)+"/"+this.format(date.getMonth(),2)+"/"+date.getFullYear();
            let data = {"fecha":fecha, "para":this.para,"cuerpo":this.cuerpo };
            this.$emit("addMemo", data);
        },
        format: function(number, width){
            var numberOutput = Math.abs(number); /* Valor absoluto del número */
            var length = number.toString().length; /* Largo del número */ 
            var zero = "0"; /* String de cero */  
            
            if (width <= length) {
                if (number < 0) {
                    return ("-" + numberOutput.toString()); 
                } else {
                    return numberOutput.toString(); 
                }
            } else {
                if (number < 0) {
                    return ("-" + (zero.repeat(width - length)) + numberOutput.toString()); 
                } else {
                    return ((zero.repeat(width - length)) + numberOutput.toString()); 
                }
            }
        }
    }
}
</script>
