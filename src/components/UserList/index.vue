<template>
  <div class="userlist-container">

        <div class="status">Disponível - 1</div>
        <User nickname="David Guetta dos santos" isBot/>
        <div class="status">Offline - 18 </div>
        <User nickname="Usuario" v-for="users in 24" :key="users.id"/>
  </div>
</template>

<script>
import User from './User'
export default {
  components: {
    User
  }
}
</script>

<style scoped lang="scss">
    .userlist-container {
        grid-area: UL;
        display: flex;
        flex-direction: column;
        background-color: var(--secondary);
        padding: 3px 6px 10px 16px;
        max-height: calc(100vh - 46px);
        overflow-y: scroll;

         &::-webkit-scrollbar{
            width: 8px;
            height: 50px;
        }

        &::-webkit-scrollbar-thumb{
            background-color: var(--tertiary);
            border-radius: 4px;
            
        }

        &::-webkit-scrollbar-track{
            background-color: var(--secondary);
            
        }
    }
    
    .status {
      margin-top: 20px;
      color: var(--grey);
      font-weight: 500;
      font-size: 12px;
      text-transform: uppercase;
    }
    
</style>