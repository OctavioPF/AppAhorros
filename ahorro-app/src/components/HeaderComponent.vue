<template>
    <header>
        <img @click="reload"
        src="@/assets/cashflow-icon.svg" alt="LOgo"/>
        <h1><span>Cash</span>Ahorro</h1>
        <span></span>
    </header>
    <div>

</div>

</template>

<script>
export default {
    methods:{
        reload(){
            location.reload();
        }
    }
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100vw;
}
img,
span {
  width: 48px;
}
img{
  transition: transform 0.3s, box-shadow 0.3s;
    box-shadow: 0 0 9px rgba(0, 0, 0, 0.5);
    border-radius: 26px;
}
h1 {
  font-size: 2rem;
  color: var(--brand-blue);
}
h1 span {
  color: var(--brand-green);
}
</style>