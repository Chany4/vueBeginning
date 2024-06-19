<template lang="">
  <div>
    <h1>Counter -> <span>{{counter}}</span></h1>
    <button @click ="increment()">Increment</button> <br><br>
    <button @click ="decrement()">Decrement</button> <br><br>
    <button @click ="decrement_By_Two()">Decrement by 2</button> <br><br>

    <img v-bind:src= "imgURL" >
    <div>

      <!-- class styling binding -->
      <h4 :class = "{hello:check}">Conditional Renderings</h4>
      <!-- conditional rendering -->
      <h1 v-if= "check">The value is true</h1>
      <h1 v-else>The value is false</h1>
      <button @click = "change()">change state</button>
      <h1 v-show="check">This contains the v-show</h1>
      <ul>
        <li v-for="({message},index) in objects"  :key="index">{{message}}</li>
        <!-- destructurng? -->
      </ul>
      <div>
        <!-- one way binding data -->
        <h3>{{oneWayText}}</h3>
        <!-- two way binding data -->
        <h3>{{twoWayText}}</h3>
        <input type= "text" v-model ="twoWayText">
      </div>
      <!-- <info-comp first-name = "hehe" last-name = "hehhehehehe" />
        <info-comp first-name = "hehe1" />
        <info-comp :object-data = 'singleObject' /> -->
        <info-comp>
          Hehe I am using slots
        </info-comp>
        <slot-comp>
            <template #slotTitle>
              CardSlot
          </template>
          <template  #default>
              <img :src = "imgURL">
          </template>
        </slot-comp>
    </div>
  </div>
</template>
<script>
/*eslint-disable*/
import ProductComp from '@/components/ProductComp.vue';
import InfoComp from '../components/InfoComp.vue'
import SlotComp from '../components/SlotsComp.vue'

export default {
  data () {
    return {
      counter: 0,
      imgURL: 'https://chany4.github.io/ecomWEB/images/best%20sellers/best-3.png',
      check: true,
      sports: ['soccer', 'netball', 'volleyball'],
      objects: [
        { message: 'Hello There 1', id: 1 },
        { message: 'Hello There 2', id: 2 },
        { message: 'Hello There 3', id: 3 }
      ],
      singleObject: {
        name: 'Chany',
        surname: 'Davids'
      },
      oneWayText: 'hehe',
      twoWayText: 'hehe2.0'
    }
  },
  components: {
    InfoComp,
    SlotComp,
    ProductComp
  },
  methods: {
    increment () {
      this.counter++
    },
    decrement () {
      this.counter--
    },
    decrement_By_Two () {
      this.counter = this.counter - 2
    },
    change () {
      this.check = !this.check
    }
  }
}
</script>
<style scoped>
h1{
  color:blue;
}
.hello{
  color:rgb(255, 115, 0);
}

</style>
