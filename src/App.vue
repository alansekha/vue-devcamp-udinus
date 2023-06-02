<template>
  <ConditionalRendering />
  <Event />
  <Looping />
  <Binding />
  <ParentComponent />
  <Computed />
</template>

<script>
import ConditionalRendering from './components/options/ConditionalRendering.vue'
import Event from './components/options/Event.vue'
import Looping from './components/options/Looping.vue'
import Binding from './components/options/Binding.vue'
import ParentComponent from './components/options/ParentComponent.vue'
import Computed from './components/options/Computed.vue'

export default {
  name: 'App',
  components: {
    ConditionalRendering,
    Event,
    Looping,
    Binding,
    ParentComponent,
    Computed
  }
}
</script>
