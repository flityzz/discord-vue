<template>
  <div class="channel-list" >
    <div class="category">
      <div>Canais de Texto</div>
      <div class="category-icon">
        <AddCategoryIcon :size="21" />
      </div>
    </div>
    
    <ChannelButton selected channelName="chat-livre" @selectedchannel="selectedChannel"/>
    <ChannelButton channelName="vue-js" @selectedchannel="selectedChannel"/>
    <ChannelButton channelName="jogos" @selectedchannel="selectedChannel"/>
    <ChannelButton channelName="csgo" @selectedchannel="selectedChannel"/>
    <ChannelButton channelName="rocketleague" @selectedchannel="selectedChannel"/>
  </div>
</template>

<script>
import ChannelButton from './ChannelButton'
import AddCategoryIcon from "vue-material-design-icons/Plus";
export default {
  components: {
    AddCategoryIcon,
    ChannelButton
  },
  methods: {
    selectedChannel(name){
      let title = name
      this.$emit('channel-info-title', title)
    }
  }
};
</script>

<style scoped lang="scss">
.channel-list {
  grid-area: CL;
  display: flex;
  flex-direction: column;
  padding: 24px 10px 0 16px;
  background-color: var(--secondary);
}
.category {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 6px;
  color: var(--grey);
  font-size: 12px;
  font-weight: 500;
  text-transform: uppercase;
  .category-icon {
    color: var(--symbol);
    cursor: pointer;
  }
}
</style>