<template>
  <div class="card">
    <div class="card-wrapper">
      <div class="card-header">
        <div class="card-title">{{name}}</div>
        <img :src='require(`../assets/${this.icon}.png`)' class="card-icon" alt="icon">
      </div>
      <div class="card-body">
        <p>{{content}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: [
    'name',
    'content',
    'icon',
  ],
};
</script>

<style lang="scss" scoped>
.card{
  max-width: calc((100% - 48px)/3);
  height: 200px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  transition: all 0.24s;

  @media (max-width: 960px) {
    max-width: calc((100% - 48px)/2);
  }

  @media (max-width: 480px) {
    max-width: 100%;

    height: 280px;

    .card-wrapper{
      padding: 24px 12px;
    }
  }

  .card-wrapper{
    height: 200px;
    padding: 24px;
    margin: 8px;
    border: #7e7e7e 1px solid;

    .card-header{
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 18px;
      font-weight: bold;
      margin-bottom: 12px;

      .card-icon{
        width: 24px;
        height: 24px;
      }
    }
  }
}
</style>