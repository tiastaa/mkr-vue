<template>
  <div>
    <shop-form @create="createShop" />
    <shop-list :shops="shops" @remove="removeShop" />
  </div>
</template>

<script>
import ShopForm from "@/components/ShopForm";
import ShopList from "@/components/ShopList";
export default {
  name: "HomePage",
  components: {
    ShopForm,
    ShopList,
  },
  data() {
    return {
      shops: [
        {
          id: 1,
          title: "Apple",
          address: "Cupertino",
          phoneNumber: "+380501222000",
          specialization: "gadgets",
          workingHours: "10am-18pm",
        },
        {
          id: 2,
          title: "Microsoft",
          address: "London",
          phoneNumber: "+380501222001",
          specialization: "OS",
          workingHours: "10am-19pm",
        },
      ],
    };
  },
  methods: {
    createShop(shop) {
      this.shops.push(shop);
    },
    removeShop(shop) {
      this.shops = this.shops.filter((s) => s.id !== shop.id);
    },
  },
};
</script>
