<template>
  <form class="form-inline" v-on:submit.prevent="addNewGearItem">
      <div class="form-group">
        <label for="gearItemName">Name:</label>
        <input type="text" id="gearItemName" placeholder="New Gear Item" class="form-control" v-model.trim="newGearItem.name">
      </div>
      <div class="form-group">
        <label for="gearItemDescription">Description:</label>
        <input type="text" id="gearItemDescription" class="form-control" v-model.trim="newGearItem.description">
      </div>
      <div class="form-group">
        <label for="gearItemWeight">Weight:</label>
        <input type="number" id="gearItemWeight" class="form-control" v-model.number="newGearItem.weight">
      </div>
      <input type="submit" class="form-control btn btn-primary" value="Add Item">
  </form>
</template>

<script>
export default {
  data () {
    return {
      newGearItem: {}
    }
  },
  methods: {
    addNewGearItem () {
      if (this.newGearItem.name && this.newGearItem.weight) {
        this.$emit('newGearItem', { ...this.newGearItem })
        this.newGearItem = {}
      }
    }
  }
}
</script>
