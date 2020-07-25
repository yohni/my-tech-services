<template>
  <div class="notif-wrapper" :class="!openNotif? ' notif-hide': ''">
    <div class="notif-ctx">
      <p class="notif-text">
      By accessing and using this website, you acknowledge that you have read and
understand our <a href="#">Policy</a>, <a href="#">Privacy Policy</a>, and our <a href="#">Terms of Service.</a>
      </p>
      <button @click="closeNotif">Got It</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      openNotif: true,
    };
  },
  methods: {
    closeNotif() {
      this.openNotif = false;
    },
  },
};

</script>

<style lang="scss" scoped>
@import '../styles/theme.scss';
.notif-wrapper{
  background: #fff;
  overflow: hidden;
  display: flex;
  justify-content: center;
  box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
  transition: all 0.25s;
  visibility: visible;
  max-height: 160px;

  &.notif-hide{
    transform: translateY(-100%);
    visibility: hidden;
    max-height: 0;
  }

  .notif-ctx{
    display: flex;
    max-width: 720px;
    align-items: center;
    padding: 12px 24px;

    @media (max-width: 360px) {
      flex-direction: column;
      align-items: flex-start;

      .notif-text{
        margin: 12px 0 !important;
      }
    }

    .notif-text{
      margin-right: 24px;
    }

    button{
      padding: 12px;
      background-color:$MyBlue;
      width: 100px;
      border-radius: 2.5px;
      color: #fff;
    }
  }
}
</style>