<template>
  <div>
    <h4>Додати магазин</h4>
    <label>
      Назва:
      <input type="text" v-model="shop.title" />
    </label>
    <label>
      Адреса:
      <input type="text" v-model="shop.address" />
    </label>
    <label>
      Номер телефону:
      <input type="text" v-model="shop.phoneNumber" />
    </label>
    <label>
      Спеціалізація:
      <input type="text" v-model="shop.specialization" />
    </label>
    <label>
      Робочі години:
      <input type="text" v-model="shop.workingHours" />
    </label>
    <button @click="createShop">Додати магазин</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      shop: {
        title: "",
        address: "",
        phoneNumber: "",
        specialization: "",
        workingHours: "",
      },
    };
  },
  methods: {
    createShop() {
      this.shop.id = Date.now();
      this.$emit("create", this.shop);
      this.shop = {
        title: this.title,
        address: this.address,
        phoneNumber: this.phoneNumber,
        specialization: this.specialization,
        workingHours: this.workingHours,
      };
    },
  },
};
</script>

<style lang="less" scoped></style>
