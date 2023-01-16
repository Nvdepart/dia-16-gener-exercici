<template>
<v-container fluid>
    <v-row class="block block1">
        <v-col>
          <h2>Hola</h2>
        </v-col>
    </v-row>
    <v-row class="block block2">
        <v-col align="center">
            <h2>Com es duis</h2>
            <v-text-field
            v-model="nom"
            clearable
            outlined
            style="max-width:400px"
            hide-details="auto"
            label="nom"
            ></v-text-field>
        </v-col>
    </v-row>
    <v-row class="block block3">
        <v-col align="center">
            <h2>Edat</h2>
            <v-text-field
            v-model="edat"
            clearable
            outlined
            style="max-width:400px"
            hide-details="auto"
            label="Edat"
            ></v-text-field>
        </v-col>
    </v-row>
    <v-row class="block block4">
        <v-col align="center">
            <h2>Email</h2>
            <v-text-field
            v-model="email"
            :rules="[required]"
            class="mb-2"
            outlined
            style="max-width:400px"
            clearable
            label="Email"
            append-inner-icon="mdi-At"
        ></v-text-field>

        </v-col>
    </v-row>
    <v-row class="block block5">
        <v-col align="center">
            <h2>Telefon</h2>
            <v-text-field
            v-model="telefon"
            :rules="[required]"
            class="mb-2"
            clearable
            outlined
            style="max-width:400px"
            label="Telefon"
            placeholder="600 00 00 00"
            append-inner-icon="mdi-mobil"
        ></v-text-field>
        </v-col>
    </v-row>
    <v-row class="block block6">
        <v-col align="center">
            <h2>Feina</h2>
            <v-text-field
            v-model="feina"
            clearable
            outlined
            style="max-width:400px"
            hide-details="auto"
            label="Feina"
            ></v-text-field>
        </v-col>
    </v-row>
    <v-row class="block block7">
        <v-col align="center">
            <p v-if="totPle" style="max-width:800px; font-size:50px">
                En {{nom}} es {{feina}} i té {{edat}} anys.
                Podeu contactar amb ell a través del telefon {{telefon}} o bé a través de l'email {{email}}
            </p>
            <p v-else style="max-width:800px; font-size:50px">
               Cal que emplinis el formulari 
            </p>
            <p style="max-width:800px; font-size:50px">
                {{ elTextFinal }}
            </p>
        </v-col>
    </v-row>
</v-container>
   
</template>

<script>
    export default {
        data(){
            return{
                nom: null,
                edat: null,
                email: null,
                telefon:null,
                feina:null,
            }
        }, 
        methods:{
            required(v){
                return !!v  || 'Field is required'
            }
        },
        computed:{
            elTextFinal(){
                return this.nom 
                        + " és "
                        + this.feina
                        +" i té "
                        + this.edat
                        + ". Podeu contactar-hi a través del telefon "
                        + this.telefon
                        +" o bé a través de l'email"
                        + this.email
                        +"."
                
            },
            totPle(){
                return this.nom != null
                    && this.edat != null
                    && this.email != null
                    && this.feina != null
                    && this.telefon != null
            }
        }

    }
</script>

<style scoped>
.block{
    min-height:50vh;
    padding-top: 20vh;
    padding-bottom: 20vh;
    text-align: center;
    font-size: 10vh;
    color: white;
}
.block1{
    background-color:#118499;
    color: white;
}
.block2{
    background-color: #9c5b46;
    color: white;
}
.block3{
    background-color: #4b94a4;
    color: white;
}
.block4{
    background-color: #156775;
    color: white;
}
.block5{
    background-color: #118499;
    color: white;
}
.block6{
    background-color: #9c5b46;
    color: white;
}
.block7{
    background-color: #4b94a4;
    color: white;
}

</style>