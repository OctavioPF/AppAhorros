<template>
  <LayoutComponent>
    <template #header>
      <HeaderComponent></HeaderComponent>
    </template>

    <template #resume>
      <Resume
        :total-label="'Ahorro total'"
        :label="label"
        :total-amount="totalAmount"
        :amount="amount"
      >
        <template #graphic>
            <Graphic :amounts="amounts"/>
        </template>
        <template #action>
          <Action @create="create"/>
        </template>
      </Resume>
    </template>
    <template #movementsComponent>
      <MovementsComponent 
      :movements="movements"
      @remove= "remove">
    
    </MovementsComponent>
    </template>
  </LayoutComponent>
</template>

<script>
import LayoutComponent from "./LayoutComponent.vue";
import HeaderComponent from "./HeaderComponent.vue";
import Resume from "./Resume/IndexResume.vue";
import Action from "./ActionComponent.vue";
import MovementsComponent from "./Movements/IndexMovements.vue";
import Graphic from "./Resume/GraphicAhorro.vue";
export default {
  components: {
    LayoutComponent,
    HeaderComponent,
    Resume,
    Action,
    MovementsComponent,
    Graphic,
  
  },
  data() {
    return {
      label: null,
      amount: null,
      movements: [],
    };
  },
  computed: {
    amounts() {
      const lastDays = this.movements
        .filter(m => {
          const today = new Date();
          const oldDate = today.setDate(today.getDate() - 30);

          return m.time > oldDate;
        })
        .map(m => m.amount);
      
      return lastDays.map((m, i) => {
        const lastMovements = lastDays.slice(0, i);

        return lastMovements.reduce((suma, movement) => {
          return suma + movement
        }, 0);
      });
    },
    totalAmount() {
      return this.movements.reduce((suma, m) => {
        return suma + m.amount;
      }, 0);
    }
  },
  mounted() {
    const movements = JSON.parse(localStorage.getItem("movements"));
    console.log(movements);

    if (Array.isArray(movements)) {
      this.movements = movements.map(m => {
        return { ...m, time: new Date(m.time) };
      });
    }
  },
  methods: {
    create(movement) {
      this.movements.push(movement);
      this.save();
    },
    remove(id) {
      const index = this.movements.findIndex(m => m.id === id);
      this.movements.splice(index, 1);
      this.save();
    },
    save() {
      localStorage.setItem("movements", JSON.stringify(this.movements));
    }
  }
};


</script>
<style>
</style>