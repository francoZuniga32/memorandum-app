<template>
<div class="container-fluid d-flex justify-content-center align-items-center">
    <form action="" class="border" style="margin-top: 5%; padding: 3%">
        <h1 class="text-primary text-center">Login</h1>
        <div v-for="(item, i) in error" v-bind:key="i" class="alert alert-danger" role="alert">
            {{ item }}
        </div>
        <div class="form-group">
            <label for="usuario">Email</label>
            <input v-model="usuario" type="email" class="form-control" id="usuario">
        </div>
        <div class="form-group">
            <label for="contrasenia">Password</label>
            <input v-model="password" type="password" class="form-control" id="contrasenia">
        </div>
        <div class="form-group" style="margin-top: 10px;">
            <button type="button" class="btn btn-primary" v-on:click="login">Ingresar</button>
        </div>
    </form>
</div>
</template>
<script>
export default {
    name: "login",
    data() {
        return {
            usuario: "",
            password: "",
            error: ""
        }
    },
    methods: {
        login: function(){
            this.error = [];

            //login
            /*
            const options = {
                method: 'POST',
                url: 'http://localhost:1337/auth/local',
                headers:{
                    cookie: 'strapi.sid=eyJncmFudCI6e30sIl9leHBpcmUiOjE2MDMyMzk0MTk0ODYsIl9tYXhBZ2UiOjg2NDAwMDAwfQ%3D%3D; strapi.sid.sig=Wb0bhQAPakQmWeG82WhF3_5auXg',
                    'Content-Type': 'application/json'
                },
                data: {
                    identifier: this.usuario, 
                    password: this.password
                }
            };

            axios.request(options).then(function (response) {
                console.log(response.data);
            }).catch(function (error) {
                console.error(error);
            });
            */

            if(this.usuario == "admin" && this.password == "admin"){
                this.esLogin = true;
                this.$emit("login", {"usuario":this.usuario,"password":this.password, "puesto":"Administrator de la Demo" });
                this.$router.push('/memorandum');
            }else{
                this.error.push("usuario incorrecto!!");
            }
        },
    }
}
</script>