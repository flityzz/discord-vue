<template>
  <div class="user-container">
      <div class="avatar" :class="{'bot-avatar': isBot}"></div>
      <strong>{{nickname}}</strong>
      <div class="bot" v-if="isBot">Bot</div>
  </div>
</template>

<script>
export default {
    props:{
        nickname: String,
        isBot: Boolean
    }
}
</script>

<style scoped lang="scss">
    .user-container{
        display: flex;
        margin-top: 5px;
        padding: 5px;
        cursor: pointer;
        align-items: center;
        border-radius: 5px;
        background: transparent;
        transition: 0.2s;
        flex-direction: row;

        &:hover{
            background: rgba(255, 255, 255, 0.1)
        }

        strong {
            margin-left: 13px;
            font-weight: 500;
            color: var(--white);
            opacity: 0.7;
            white-space: nowrap;
            text-overflow: ellipsis;
            overflow: hidden;
        }

        .avatar{
            width: 32px;
            height: 32px;
            border-radius: 50%;
            flex-shrink: 0;
            background-color: var(--primary);
        }

        .bot {
            margin-left: 9px;
            background-color: var(--discord);
            color: var(--white);
            padding: 4px 5px;
            border-radius: 4px;
            text-transform: uppercase;
            font-size: 11px;
            font-weight: bold;
        }

        .bot-avatar{
        background-color: var(--mention-detail);
    }
    }
</style>