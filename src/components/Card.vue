<template>
    <div class="col mb-2">
        <div class="card" style="width: 18rem;">
            <img src="pdfimg.png" class="card-img-top" alt="">
            <div class="card-body">
                <h5 class="card-title">n°: {{numero}}</h5>
                <p class="card-text">De: {{ de }}, Para: {{ para }}</p>
                <p class="card-text">{{ fecha }}</p>
                <button href="#" class="btn btn-primary" v-on:click="pdf">
                    <span class="material-icons" style="color: withe">
                        picture_as_pdf
                    </span>
                </button>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    mane:"card",
    props:{
        "indice": Number,
        "numero": Number,
        "fecha": String,
        "de": String,
        "para":String,
        "cuerpo": String,
    },
    mounted() {
        this.numero = this.format(this.numero, 3);
    },
    methods: {
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
        },
        pdf: function(){
            let data = `<h2 class="text-center">Memorandum</h2><h3>N° ${this.numero}</h3></br><p>Fecha: ${ this.fecha }</p><p>De: ${ this.de }</p><p>Para: ${ this.para }</p><p>${ this.cuerpo }</p>`;
            data += `<p class="text-right">md5sum ${CryptoJS.MD5(data)}</p>`;
            html2pdf(data, { margin: 10 , filename: `memo-${this.numero}`});
        }
    }
}
</script>