<template>
  <div class="nl-wrapper">
    <div @click="$emit('close-click')">
      <IconClose class="icon-close" width="24" hight="24" />
    </div>
    <div class="nl-title">
      Get latest updates in web technologies
    </div>
    <div class="nl-ctx">
      I write articles related to web technologies, such as design trends, development tools, UI/UX case studies and reviews, and more. Sign up to my newsletter to get them all.
    </div>
    <form class="nl-form">
      <input type="email" required>
      <button type="submit">Count me in!</button>
    </form>
  </div>
</template>

<script>
import IconClose from '../components/IconClose';

export default {
  components: {
    IconClose,
  },
};
</script>

<style lang="scss" scoped>
@import '../styles/theme.scss';

.nl-wrapper{
  background: rgba($color: $MyDarkBlue, $alpha: 0.8);
  position: fixed;
  bottom: 0;
  left: 0;
  padding: 32px 32px;
  max-width: 640px;
  color: #fff;

  .icon-close{
    cursor: pointer;
    position: absolute;
    top: 12px;
    right: 12px;
  }

  .nl-title{
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 12px;
  }

  .nl-ctx{
    margin-bottom: 12px;
    line-height: 1.4rem;
  }

  .nl-form{
    width: 100%;
    display: flex;
    justify-content: space-between;

    @media (max-width: 480px) {
      flex-direction: column;
    }

    input[type="email"]{
      width: 100%;
      height: 24px;
      margin-bottom: 12px;
      
      @media (min-width: 480px) {
        margin-right: 8px;
      }
    }

    button{
      height: 30px;
      width: 200px;
      background: $MyOrange;
      color: #fff;
      transition: all 0.25s;
      font-size: 14px;
      font-weight: bold;

      &:hover{
        background: $MyDarkOrange;
        
      }

      @media (max-width: 480px) {
        width: 100%;
      }
    }

  }
}
</style>