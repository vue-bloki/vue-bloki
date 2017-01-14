<template>
  <div class="layout">
    <div class="sidebar">
      <div class="sidebar-toggle">
        <div class="burger"></div>
      </div>
      <slot name="sidebar">
        <div class="placeholder">
          sidebar slot
        </div>
      </slot>
    </div>
    <div class="content">
      <slot name="content">
        <div class="placeholder">
          content slot
        </div>
      </slot>
    </div>
  </div>
</template>

<style scoped lang="scss" rel="stylesheet/scss">
  @import "~sass-burger/_burger.scss";

  $sidebarWidth: 250px;

  .layout {
    height: 100%;
  }

  .content {
    transition: padding 0.2s;
    transition-delay: 0.1s;
    padding-left: $sidebarWidth;
    height: 100%;

    @media only screen and (max-width: 768px) {
      padding-left: 0;
    }

    &:before {
      transition: opacity 0.2s, visibility 0.2s;
      transition-delay: 0.1s;
      content: "";
      display: block;
      visibility: hidden;
      position: fixed;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      background-color: black;
      opacity: 0;
      z-index: 1;
    }
  }

  .sidebar-toggle {
    display: flex;
    width: 45px;
    height: 45px;
    right: -47px;
    top: 2px;
    background-color: lightgray;
    position: absolute;
    transition: opacity 0.2s, visibility 0.2s;
    transition-delay: 0.1s;
    border-radius: 50%;
    justify-content: center;
    align-items: center;
    visibility: hidden;
    opacity: 0;

    @media only screen and (max-width: 768px) {
      visibility: visible;
      opacity: 1;
    }
  }

  .burger {
    @include burger(
      $color: white,
      $width: 23px,
      $height: 4px,
      $gutter: 4px
    );
  }

  .sidebar {
    transition: transform 0.2s, box-shadow 0.2s;
    transition-delay: 0.1s;
    width: $sidebarWidth;
    position: fixed;
    bottom: 0;
    top: 0;
    z-index: 2;

    @media only screen and (max-width: 768px) {
      transform: translateX(-$sidebarWidth);

      &:hover {
        transform: translateX(0);
        box-shadow: 0 0 5px rgba(0, 0, 0, 0.8);

        .sidebar-toggle {
          visibility: hidden;
          opacity: 0;
        }

        & + .content:before {
          visibility: visible;
          opacity: 0.5;
        }
      }
    }
  }

  .placeholder {
    background-color: white;
    border: 5px dashed whitesmoke;
    height: 100%;
    color: lightgray;
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 130%;
  }

  @media only screen and (min-width: 769px) {
    .sidebar .placeholder {
      border-right: none;
    }
  }
</style>
