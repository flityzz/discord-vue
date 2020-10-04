<template>
  <div id="grid">
    <ServerList />
    <ServerName />
    <ChannelList @channel-info-title="getTitle" />
    <UserInfo />
    <ChannelInfo :title="channelTitle ? channelTitle : 'chat-livre'"/>
    <ChannelData />
    <UserList />
  </div>
</template>

<script>
import ServerList from "./ServerList";
import ServerName from "./ServerName";
import ChannelList from "./ChannelList";
import UserInfo from './UserInfo';
import UserList from './UserList';
import ChannelInfo from './ChannelInfo';
import ChannelData from './ChannelData';
export default {
  data: function (){
    return {
      channelTitle: ''
    }
  },
  components: {
    ServerList,
    ServerName,
    ChannelList,
    UserInfo,
    ChannelInfo,
    ChannelData,
    UserList
  },
  
  methods:{
    getTitle(title){
      this.channelTitle = title
    }
  }
  
};
</script>

<style scoped>
#grid {
  display: grid;
  grid-template-columns: 71px 240px auto 240px;
  grid-template-rows: 46px auto 52px;
  grid-template-areas:
    "SL SN CI CI"
    "SL CL CD UL"
    "SL UI CD UL";
  height: 100vh;
}
</style>
