<template>
  <native-base-provider>
    <scrollView>
      <box p="40px">
        <center><text mb="6">MATRICES</text></center>
        <text>Filas</text>
        <input type="text" v-model="filas"/>
        <text>Columnas</text>
        <input type="text" v-model="columnas"/>
        <box pt="30px">
          <button P="10px" size="sm" :on-press="generarMatriz">GENERAR</button> 
        </box>
      </box>
      <box maxWidth="100%" alignItems="center" > 
          <vStack space="2.5" px="8">     
              <box v-for="fila in matriz">
                <stack direction="row" > 
                  <box v-for="columna in fila"> 
                    <input type="text" width="50px" h="50px" m="1" bg="#3aba1c" v-model="columna.value"/>
                  </box> 
                </stack>         
              </box>    
               <text> {{matriz}}</text>
          <vStack>
        </box>
      <scrollView>
  </native-base-provider>
</template>
<script>
  import { NativeBaseProvider,Button, Box,Container, Text,Heading, Stack, HStack, Center, Input, ScrollView, VStack} from "native-base";
  export default{
    data:{
    idFilas: "",
    idColumnas: "",
    filas: 0,
    columnas: 0,
    matriz:[],
    fila: 0,
    columna: 0,
    },
    components:{NativeBaseProvider,Button, Box, Container, Text, Heading, Stack, HStack, Center,Input,ScrollView, VStack},
    methods:{
      generarMatriz(){
        
        this.matriz=[]
        this.fila = this.filas;
        this.columna = this.columnas;

          var auxiliar =[];
          var cont= 0;
          for(var i = 0; i<this.fila; i++){
            for(var j = 0; j<this.columna; j++){
              auxiliar.push({id: cont,value:'0'});
              cont++;
            }
            this.matriz.push(auxiliar);
            auxiliar=[]
          }
        
       
      
      }
    }
  }
</script>