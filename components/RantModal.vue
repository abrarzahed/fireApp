<template>
  <div>
    <b-button id="show-btn" @click="showModal">Rent</b-button>

    <b-modal ref="my-modal" hide-footer title="Using Component Methods">
      <div class="calendar-container">
        <div class="text-container">
          <p>
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Optio
            labore repellendus possimus minus harum reiciendis tenetur, nisi,
            quae voluptate facere sapiente autem, dolore asperiores atque?
            Officiis optio eligendi inventore eius repellat asperiores, rem
            ipsa, sed nemo culpa ipsum dicta animi?
          </p>
        </div>
        <vc-date-picker :value="null" color="indigo" is-dark is-range />
      </div>
      <NuxtLink to="/myItems">
        <b-button
          @click="
            () => {
              addItem(product.id);
              hideModal();
            }
          "
          variant="outline-danger"
          id="show-btn"
          >Oredr Now</b-button
        >
      </NuxtLink>
    </b-modal>
  </div>
</template>

<script>
import { mapMutations } from "vuex";
export default {
  props: ["product"],
  methods: {
    showModal() {
      this.$refs["my-modal"].show();
    },
    hideModal() {
      this.$refs["my-modal"].hide();
    },
    toggleModal() {
      // We pass the ID of the button that we want to return focus to
      // when the modal has hidden
      this.$refs["my-modal"].toggle("#toggle-btn");
    },
    ...mapMutations(["addItem"])
  }
};
</script>
<style scoped>
button {
  width: 100%;
  border: none;
  padding: 0.5rem;
  color: white;
  font-weight: 700;
  padding: 1rem 4rem;
  border-radius: 100rem;
  background-color: rgb(46, 111, 0);
  color: white;
  font-weight: 700;
  transition: 0.5s;
}
.calendar-container {
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}
p {
  color: grey;
}
.text-container {
  padding: 0.5rem;
}
</style>
