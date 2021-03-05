<template>
  <div class="home">
  <ToDoCard/>
  </div>
</template>

<script>
// @ is an alias to /src

import ToDoCard from '@/components/ToDoCard'
export default {
  
  name: 'Home',
  components: {
            ToDoCard,
        },
}
</script>
