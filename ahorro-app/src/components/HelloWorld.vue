<template>
  <LayoutComponent>
    <template #header>
      <HeaderComponent></HeaderComponent>
    </template>

    <template #resume>
        <Resume></Resume>
    </template>
    <template #movementsComponent>
      <MovementsComponent></MovementsComponent>
    </template>
  </LayoutComponent>
</template>

<script>
import LayoutComponent from "./LayoutComponent.vue";
import HeaderComponent from "./HeaderComponent.vue";
import Resume from "./Resume/IndexResume.vue";
import MovementsComponent from "./MovementsComponent.vue";

export default {
  components: {
    LayoutComponent,
    HeaderComponent,
    Resume,
    MovementsComponent,
  },
};
</script>
