<template>
  <LayoutComponent>
    <template #header>
      <HeaderComponent></HeaderComponent>
    </template>

    <template #resume>
      <Resume
        :total-label="'Ahorro total'"
        :label="label"
        :total-amount="500"
        :amount="amount"
      >
        <template #graphic> grapic </template>
        <template #action>
          <Action/>
        </template>
      </Resume>
    </template>
    <template #movementsComponent>
      <MovementsComponent 
      :movements="movements">
    
    </MovementsComponent>
    </template>
  </LayoutComponent>
</template>

<script>
import LayoutComponent from "./LayoutComponent.vue";
import HeaderComponent from "./HeaderComponent.vue";
import Resume from "./Resume/IndexResume.vue";
import MovementsComponent from "./Movements/IndexMovements.vue";
import Action from "./ActionComponent.vue";

export default {
  components: {
    LayoutComponent,
    HeaderComponent,
    Resume,
    MovementsComponent,
    Action,
  },
  data() {
    return{
    amount: null,
    label:null,
    movements: [{
                id: 0,
                title: "Movimiento 1",
                description: "Lorem ipsum dolor sit amet",
                amount: 1000,
            }, {
                id: 1,
                title: "Movimiento 2",
                description: "Lorem ipsum dolor sit amet",
                amount: -1000,
            }, {
                id: 2,
                title: "Movimiento 3",
                description: "Lorem ipsum dolor sit amet",
                amount: 1000,
            }, {
                id: 3,
                title: "Movimiento 4",
                description: "Lorem ipsum dolor sit amet",
                amount: -1000,
            }, {
                id: 4,
                title: "Movimiento 5",
                description: "Lorem ipsum dolor sit amet",
                amount: -1000,
            }, {
                id: 6,
                title: "Movimiento 7",
                description: "Lorem ipsum dolor sit amet",
                amount: 1000,
            }, {
                id: 7,
                title: "Movimiento 8",
                description: "Lorem ipsum dolor sit amet",
                amount: 1000,
            }, {
                id: 8,
                title: "Movimiento 9",
                description: "Lorem ipsum dolor sit amet",
                amount: 1000,
            }]
        }
    },
};

</script>
