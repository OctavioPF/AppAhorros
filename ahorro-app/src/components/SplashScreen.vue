<template>
    <div class="splashscreen">
        <img src="@/assets/cashflow-icon.svg"
         alt="icono">
        <h1><span>Splash</span>Ahorros</h1>
    </div>
</template>



<style scoped>
.splashscreen {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
}
h1 {
  color: var(--brand-blue);
}
h1 span {
  color: var(--brand-green);
}
img{
  transition: transform 0.3s, box-shadow 0.3s;
    box-shadow: 0 0 9px rgba(0, 0, 0, 0.5);
    border-radius: 117px;
}
</style>