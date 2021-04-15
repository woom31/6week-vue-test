<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ name }}</h1>
    <ul>
      <li v-for="(item, idx) in items" :key="idx">
        {{ item.text }}
        <button @click="removeItem(idx)">Remove Item</button>
      </li>
    </ul>
    <!-- <button @click="addItem">Add Item</button> -->
    <button @click="changeName">Change Name</button>
    <button @click="clearName">Clear Name</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      name : 'WOOM' ,
      items : [
        {
          value : 1,
          text : 'item 1'
        },
        {
          value : 2,
          text : 'item 2'
        },
        {
          value : 3,
          text : 'item 3'
        }
      ]
    }
  },
  methods : {
    // addItem(){
    //   let idx = this.items.length + 1;
    //   this.items.push({
    //     value : idx ,
    //     text : 'item ' + idx
    //   });
    // },
    removeItem(idx){
      this.items.splice(idx , 1);
    },
    changeName(){
      console.log(this.name);
      var arr = ['omenn', 'jeong woomin', 'woomin', 'wamoovi', 'woom'];
      function randomName(a){
        return a[Math.floor(Math.random() * a.length)];
      }
      this.name = randomName(arr);
    },
    clearName(){
      this.name = '';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>