<template>
  <div class="card">
    <div class="card-image">
      <figure class="image is-4by3">
        <img src="http://placehold.it/300x225" alt="">
      </figure>
    </div>
    <div class="card-content">
      <div class="media">
        <div class="media-left">
          <span class="image is-32x32">
            <img src="http://placehold.it/64x64" alt="Image">
          </span>
        </div>
        <div class="media-content">
          <p class="title is-5">John Smith</p>
          <p class="subtitle is-6">@johnsmith</p>
        </div>
      </div>

      <div class="content">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit.
        Phasellus nec iaculis mauris. <a href="#">@bulmaio</a>.
        <a href="#">#css</a> <a href="#">#responsive</a>
        <br>
        <small>11:09 PM - 1 Jan 2016</small>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      message: {
        type: String
      },
      variant: {
        type: String,
        default: 'default'
      }
    },
    data () {
      return {
        show: true
      }
    },
    methods: {
      close () {
        this.$emit('close')
        this.show = false
      }
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  * {
    box-sizing: border-box;
  }

  .card {
    background-color: white;
    box-shadow: 0 2px 3px rgba(10, 10, 10, 0.1), 0 0 0 1px rgba(10, 10, 10, 0.1);
    color: #4a4a4a;
    max-width: 100%;
    position: relative;
    width: 300px;
  }

  .card-image {
    display: block;
    position: relative;
  }

  .card-content {
    padding: 20px;
  }

  .image.is-32x32 {
    height: 32px;
    width: 32px;
  }

  figure {
    margin: 0;
    padding: 0;
  }

  .media {
    -webkit-box-align: start;
    -ms-flex-align: start;
    align-items: flex-start;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    text-align: left;
  }

  .media-left {
    margin-right: 10px;
  }

  .media-content {
    -webkit-box-flex: 1;
    -ms-flex-positive: 1;
    flex-grow: 1;
    -ms-flex-negative: 1;
    flex-shrink: 1;
    text-align: left;
  }
</style>
