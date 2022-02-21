<template>
  <native-base-provider>
    <scrollView>
      <box p="40px">
        <text>Filas</text>
        <input type="text"/>
        <text>Columnas</text>
        <input type="text"/>
        <box pt="30px">
          <button P="10px" size="sm">GENERAR</button> 
        </box>
      </box>
      <box maxWidth="100%" alignItems="center" bg="#3aba1c"> 
          <vStack space="2.5" mt="4" px="8">     
              <box v-for="i in filas" v-bind:key="i.id">
                <stack direction="row" > 
                  <box v-for="j in columnas" v-bind:key="j.id"> 
                    <input type="text" width="50px" h="50px" m="1" defaultValue="0"/>
                  </box> 
                </stack>         
              </box>   
          <vStack>
        </box>
      <scrollView>
  </native-base-provider>
</template>
<script>
  import { NativeBaseProvider,Button, Box,Container, Text,Heading, Stack, HStack, Center, Input, ScrollView, VStack} from "native-base";
  export default{
    data:{
    filas: 4,
    columnas: 3,
    },
    components:{NativeBaseProvider,Button, Box, Container, Text, Heading, Stack, HStack, Center,Input,ScrollView, VStack}
  }
</script>