<template>
  <div>
    <transition name="fade" appear mode="out-in">
      <div class="ui message success" v-if="visible" key="visible">
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Impedit, rerum
        similique. Excepturi consequuntur, veniam quidem, ducimus eum sed
        facere, earum itaque architecto suscipit fuga harum rem distinctio fugit
        hic eius!
      </div>
      <div class="ui message success" v-else key="invisible">
          c'est reussi!
      </div>
    </transition>
    <button @click="toggle">toggle</button>

    <ul>
        <transition-group name="bounce" tag="ul"> 
            <li v-for="item in items" :key="item">{{ item }}</li>
        </transition-group>
       
    </ul>
    <button class="ui button" @click="add" >Ajouter un chiffre</button>
    <button class="ui button error" @click="shuffle" >Melanger</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      visible: true,
      items: [90,60,30,45,46],
    };
  },
  methods: {
      add: function(){
          this.items.push(Math.random())
      },
      shuffle:function(){
          this.items = [46,30,60,90,45]
      },
    toggle: function () {
      this.visible = !this.visible;
    },
  },
};
</script>

<style>
.bounce-move{
    transition: transform 10s;
}
.bounce-enter-active {
  animation: bounce-in .5s;
}
.bounce-leave-active {
  animation: bounce-in .5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.5);
  }
  100% {
    transform: scale(1);
  }
}

</style>