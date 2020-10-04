<template>
  <div class="container">
      <div class="messages">
          <ChannelMessage author="Joao Vitor" date="02/20/2020" hasMention> Esta é uma mensagem </ChannelMessage>
          <ChannelMessage author="Joao Vitor" date="02/20/2020" isBot>Esta é uma mensagem</ChannelMessage>

          <ChannelMessage author="Joao Vitor" date="02/20/2020" isBot hasMention>
          <Mention>Joao Vitor</Mention> Esta é uma mensagem
          </ChannelMessage>

          <ChannelMessage author="Joao Vitor" date="02/20/2020" v-for="messages in 30" :key="messages.id">
          Esta é uma mensagem
          </ChannelMessage>
            
      </div>
      <div class="input-wrapper">
          <input type="text" placeholder="Conversar em #chat-livre">
          <div class="icon">
              <At :size="24"/>
          </div>
      </div>
  </div>
</template>

<script>
import Vue from 'vue'
import At from 'vue-material-design-icons/At'
import ChannelMessage from './ChannelMessage'
export default {
    components: {
        At,
        ChannelMessage
    }
};


//componente LOCAL
Vue.component('Mention', {
    template: '<span class="mention"> @<slot/> </span>'
})

</script>

<style scoped lang="scss">
    .container{
        grid-area: CD;
        
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        background-color: var(--primary);
        flex: 1;
    }

    .messages {
        display: flex;
        flex-direction: column;
        height: calc(100vh - 46px - 68px);
        max-height: calc(100vh - 46px - 68px);
        overflow-y: scroll;

        .channel-message:first-child {
            margin-top: 0;
        }

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

    .input-wrapper {
        width: 100%;
        padding: 0 16px;
        height: 68px;

        input {
            width: 100%;
            height: 44px;
            padding: 0 10px 0 57px;
            border-radius: 5px;
            color: var(--white);
            background-color: var(--chat-input);
            position: relative;

            &::placeholder{
                color: var(--grey);
            }
        }
    }

    .icon{
            color: var(--grey);
            position: relative;
            top: -50%;
            left: 14px;
            transition: 0.2s;
            width: 24px;
    }
</style>