<template>
  <view class="container">
    <text class="titulo">2DO EJERCICIO</text>
    <view class="imagen">
    <image class="imagenes"
          :style="{width: 300, height: 300,}"
          :source="{uri: 'https://emprendecontuweb.com/wp-content/uploads/2018/07/web-development-1140x569.jpg'}"
    />
     </view>
     <view class="contenido">
      <text class="detalle">DETALLE:</text>
      <text class="parrafo">Este es el segundo modelo que solicito el ingeniero que pudieramos realizar, este modelo se ha realizado con puros stilos css, por lo tanto no hemos ocupado el framework native base, este framework sera ocupado para los otros ejemplos que se realizaran en esta tarea</text>
    </view>
  </view>
</template>
<script>
  import { NativeBaseProvider, Box,Center, VStack, Input, Button, HStack} from "native-base";

  export default{
    data:{

    },
    components:{NativeBaseProvider,Box, Center, VStack, Input, Button, HStack}
  }
</script>
<style>
.contenido{
  margin-left: 20px;
  margin-right: 20px;
}
.parrafo{
  padding-top: 15px;
  font-size: 15px;
}
.detalle{
  align-content: flex-start;
  font-size: 20px;
}
.titulo{
  font-size: 30px;
  padding-bottom: 15px;
}
.imagen{
  align-items: center;
  padding-bottom: 20px;
}
.imagenes{
  border-radius: 300;
}
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  color: blue;
}
</style>
