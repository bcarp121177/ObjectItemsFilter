<template>
  <div class="hello"></div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      firstArray: [{ id: 2 }, { id: 5 }, { id: 6 }],
      secondArray: [{ id: 2 }, { id: 3 }, { id: 4 }]
    };
  },
  beforeMount() {
    this.getIdsInFirstArrayNotInSecondArray();
  },
  methods: {
    getIdsInFirstArrayNotInSecondArray() {
      var firstArrayResults = [];
      firstArrayResults = this.firstArray.filter(
        o => !this.secondArray.some(i => i.id === o.id)
      );

      console.log(
        firstArrayResults.map(o => {
          return { id: o.id };
        })
      );
    }
  }
};
</script>

<style scoped>
</style>
