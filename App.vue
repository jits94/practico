<template>
  <native-base-provider>
    <scrollView>
      <box p="40px">
        <center><text mb="6" fontSize="2xl">Operación de Matrices</text></center>
        <vStack space="2.5">    
            <stack direction="row"> 
              <text mr="12" ml="10" fontSize="xl">Matriz A</text>
              <stack direction="row"> 
                <text ml="2" fontSize="xl">Matriz B</text>
              </stack>
            </stack> 
            <stack direction="row"> 
              <text mr="12" fontSize="md" >Fila</text>
              <input type="text" ml="1" w="12" fontSize="md" v-model="filaA"/>
              <text mr="12" ml="5" fontSize="md" >Fila</text>
              <input type="text" w="12" ml="2" fontSize="md" v-model="filaB"/>
            </stack> 
            <stack direction="row" > 
              <text mr="4" fontSize="md" >Columna</text>
              <input type="text" w="12" fontSize="md" v-model="columnaA"/>
              <text mr="4" ml="5" fontSize="md" >Columna</text>
              <input type="text" w="12" fontSize="md" v-model="columnaB"/>
            </stack> 
            <box pt="30px">
              <button pt="10px" size="sm" :on-press="generarMatriz">GENERAR MATRICES</button> 
            </box>
        <vStack>      
      </box>
      <box maxWidth="100%" alignItems="center" > 
          <vStack space="2.5" px="8">  
            <center><text>Matriz A</text>     
              <box v-for="filaA in matrizA">
                <stack direction="row" > 
                  <box v-for="columnaA in filaA"> 
                    <input type="text" fontSize="lg" width="50px" h="50px" m="1" bg="#3aba1c" v-model="columnaA.value"/>
                  </box> 
                </stack>         
              </box>   
            </center>
          <vStack>

          <vStack space="2.5" px="8">  
            <center><text>Matriz B</text>
              <box v-for="filaB in matrizB">
                <stack direction="row" > 
                  <box v-for="columnaB in filaB"> 
                    <input type="text" fontSize="lg" width="50px" h="50px" m="1" bg="#3aba1c" v-model="columnaB.value"/>
                  </box> 
                </stack>         
              </box>  
            </center>                  
          <vStack>

        <vStack space="2.5" mt="4" px="8">
          <stack direction="row" mb="4">
            <button P="10px" size="sm" :on-press="operacionSumar">SUMAR</button>
            <button P="10px" size="sm" mr="3" ml="3" :on-press="operacionRestar">RESTAR</button>
            <button P="10px" size="sm" :on-press="operacionMultiplicar">MULTIPLICAR</button>
          </stack>
        </vStack>

         <vStack space="2.5" px="8">  
            <center><text>RESULTADO</text>     
              <box v-for="filaB in matrizR">
                <stack direction="row" > 
                  <box v-for="columnaB in filaB"> 
                    <input type="text" fontSize="lg" width="50px" h="50px" m="1" bg="#3aba1c" readOnly v-model="columnaB.valor"/>
                  </box> 
                </stack>         
              </box>   
            </center>
          <vStack>
            
        </box>
      <scrollView>
  </native-base-provider>
</template>
<script>
  import { NativeBaseProvider,Button, Box,Container, Text,Heading, Stack, HStack, Center, Input, ScrollView, VStack} from "native-base";
  export default{
    data:{
      filaA: 0,
      filaB: 0,
      columnaA: 0,
      columnaB: 0,
      matrizA:[],
      matrizB:[],
      matrizR:[],
      newFilaA: 0,
      newColumnaA: 0,
      newFilaB: 0,
      newColumnaB: 0,
    },
    components:{NativeBaseProvider,Button, Box, Container, Text, Heading, Stack, HStack, Center,Input,ScrollView, VStack},
    methods:{
      generarMatriz(){ 
        if(this.filaB == this.filaA && this.columnaA == this.filaA && this.columnaB == this.filaA ){

          this.matrizA=[];
          this.matrizR=[];
          this.newFilaA = this.filaA;
          this.newColumnaA = this.columnaA;

          this.matrizB=[];
          this.newFilaB = this.filaB;
          this.newColumnaB = this.columnaB;

            var auxiliarA =[];
            var cont= 0;
            for(var i = 0; i<this.newFilaA; i++){
              for(var j = 0; j<this.newColumnaA; j++){
                auxiliarA.push({id: cont,value:'0'});
                cont++;
              }
              this.matrizA.push(auxiliarA);
              auxiliarA=[]
            }  


            var auxiliarB =[];        
            for(var i = 0; i<this.newFilaB; i++){
              for(var j = 0; j<this.newColumnaB; j++){
                auxiliarB.push({id: cont,value:'0'});
                cont++;
              }
              this.matrizB.push(auxiliarB);
              auxiliarB=[]
            } 
        }
        else{
          if(this.filaA <= 1 || this.filaB <= 1 || this.columnaB <= 1 || this.columnaB <= 1){
            alert("Las dimensiones deben ser mayor a 1");
          }
          else{
            alert("Las Matriz A debe ser del mismo tamaño que la Matriz B");
          }
        } 
      },
      operacionSumar(){
        this.matrizR=[];

          var auxiliar =[];
          var x = 0;
          var y = 0;
          var cont = 0;
          for (x=0; x < this.newFilaB; x++) {
            for (y=0; y < this.newColumnaB; y++) {                                
              var result = (Number(this.matrizA[x][y].value) + Number(this.matrizB[x][y].value)).toString();
              
              auxiliar.push({id: cont,valor: result}); 
              cont++;
            }
            this.matrizR.push(auxiliar);
            auxiliar=[]
          };         
      },
         operacionRestar(){
        this.matrizR=[];

          var auxiliar =[];
        
          var cont = 0;
          for (var x=0; x < this.newFilaB; x++) {
            for (var y=0; y < this.newColumnaB; y++) {                                
              var result = (Number(this.matrizA[x][y].value) - Number(this.matrizB[x][y].value)).toString();
              
              auxiliar.push({id: cont,valor: result}); 
              cont++;
            }
            this.matrizR.push(auxiliar);
            auxiliar=[]
          };
                
      },
       operacionMultiplicar(){
        this.matrizR=[];

          var auxiliar =[];
          var x = 0;
          var y = 0;
          var cont = 0;
          for (x=0; x < this.newFilaB; x++) {
            for (y=0; y < this.newColumnaB; y++) {                                
              var result = (Number(this.matrizA[x][y].value) * Number(this.matrizB[x][y].value)).toString();
              
              auxiliar.push({id: cont,valor: result}); 
              cont++;
            }
            this.matrizR.push(auxiliar);
            auxiliar=[]
          };
                
      }
    }
  }
  
</script>