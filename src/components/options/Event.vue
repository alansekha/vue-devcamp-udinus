<template>
    <div>
        <h1>Event Handling</h1>

        <!-- Click Event -->
        <button @click="count++">count is: {{ count }}</button>

        <!-- Stop Event Handler -->
        <div>
            <div @click="clicked($event)">
                <button @click.stop="clicked($event)">Click Me</button>
            </div>
        </div>

        <!-- Once Event Handler -->
        <button @click.once="count++">count is: {{ count }}</button>

        <!-- Prevent Handler -->
        <form @submit.stop.prevent="log($event)">
          <button type="Submit">
            Click Me
          </button>
        </form>

        <!-- Self Handler -->
        <div class="parent" @click.self="selfLog('from parent')">
            Parent
            <div class="child" @click="selfLog('from child')">
            Child
            </div>
        </div>
    </div>

</template>

<style>
.parent {
  width: 200px;
  height: 200px;
  background: red;
  text-align: center;
  color: white;
  margin-right: auto;
  margin-left: auto;
}

.child {
  width: 100px;
  height: 100px;
  background: blue;
  margin: 50px;
  text-align: center;
  color: white;
}
</style>

<script>
export default {
    name: 'Event',
    data() {
       return {
            count: 0
        }
    },
    methods: {
        clicked: function(event) {
            alert("Click from "+event.target.tagName+"\nCurrent Target: "+event.currentTarget.tagName);
        },
        log(event) {
            console.log("Clicked ! " + event.target.tagName);
        },
        selfLog(message) {
            alert(message)
        }
    }
}
</script>

