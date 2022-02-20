<template>
  <view class="container">
    <view class="imagen">
    <image
          :style="{width: 300, height: 300,}"
          :source="{uri: 'https://emprendecontuweb.com/wp-content/uploads/2018/07/web-development-1140x569.jpg'}"
    />
     </view>
     <view class="contenido">
      <button title="Learn More" color="#841584" />
       
    </view>
    <view>
      <button class="boton" title="Learn More" color="#841584" />
    </view>
  </view>
</template>

<style>
.boton{
 
}
.contenido{
 padding-bottom: 10px;
}
.imagen{
  align-items: center;
  padding-bottom: 20px;
  padding-top: 20px;
}
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
}
</style>
