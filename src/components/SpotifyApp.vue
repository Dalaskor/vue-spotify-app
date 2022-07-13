<template>
<div class="container">
  <div class="app__content">
    <div class="app__header">
      <div class="app__profile">
        <img src="./../static/img/profile.png" alt="Profile image" class="profile_img">
      </div>
      <p class="header__text">
        Your Feed
      </p>
    </div>
    <div class="app__tracklist">
      <div class="app__trackcard cardtrack">
        <img src="./../static/img/track-1.jpg" alt="Image for card track" class="cardtrack__img">
        <div class="cardtrack__body">
          <p class="cardtrack__title">
            Summer Can Last More
          </p>
          <p class="cardtrack__author">
            Vlad Gluschenko
          </p>
        </div>
        <div class="cardtrack__button">
          <button class="playbutton">
            <img src="./../static/img/play.png" alt="" class="playbutton__img">
          </button>
        </div>
      </div>
      <div class="app__trackcard cardtrack">
        <img src="./../static/img/track-1.jpg" alt="Image for card track" class="cardtrack__img">
        <div class="cardtrack__body">
          <p class="cardtrack__title">
            Summer Can Last More
          </p>
          <p class="cardtrack__author">
            Vlad Gluschenko
          </p>
        </div>
        <div class="cardtrack__button">
          <button class="playbutton">
            <img src="./../static/img/play.png" alt="" class="playbutton__img">
          </button>
        </div>
      </div>
      <div class="app__trackcard cardtrack">
        <img src="./../static/img/track-1.jpg" alt="Image for card track" class="cardtrack__img">
        <div class="cardtrack__body">
          <p class="cardtrack__title">
            Summer Can Last More
          </p>
          <p class="cardtrack__author">
            Vlad Gluschenko
          </p>
        </div>
        <div class="cardtrack__button">
          <button class="playbutton">
            <img src="./../static/img/play.png" alt="" class="playbutton__img">
          </button>
        </div>
      </div>
      <div class="app__trackcard cardtrack">
        <img src="./../static/img/track-1.jpg" alt="Image for card track" class="cardtrack__img">
        <div class="cardtrack__body">
          <p class="cardtrack__title">
            Summer Can Last More
          </p>
          <p class="cardtrack__author">
            Vlad Gluschenko
          </p>
        </div>
        <div class="cardtrack__button">
          <button class="playbutton">
            <img src="./../static/img/play.png" alt="" class="playbutton__img">
          </button>
        </div>
      </div>
      <div class="app__trackcard cardtrack">
        <img src="./../static/img/track-1.jpg" alt="Image for card track" class="cardtrack__img">
        <div class="cardtrack__body">
          <p class="cardtrack__title">
            Summer Can Last More
          </p>
          <p class="cardtrack__author">
            Vlad Gluschenko
          </p>
        </div>
        <div class="cardtrack__button">
          <button class="playbutton">
            <img src="./../static/img/play.png" alt="" class="playbutton__img">
          </button>
        </div>
      </div>
      <div class="app__trackcard cardtrack">
        <img src="./../static/img/track-1.jpg" alt="Image for card track" class="cardtrack__img">
        <div class="cardtrack__body">
          <p class="cardtrack__title">
            Summer Can Last More
          </p>
          <p class="cardtrack__author">
            Vlad Gluschenko
          </p>
        </div>
        <div class="cardtrack__button">
          <button class="playbutton">
            <img src="./../static/img/play.png" alt="" class="playbutton__img">
          </button>
        </div>
      </div>
      <div class="app__trackcard cardtrack">
        <img src="./../static/img/track-1.jpg" alt="Image for card track" class="cardtrack__img">
        <div class="cardtrack__body">
          <p class="cardtrack__title">
            Summer Can Last More
          </p>
          <p class="cardtrack__author">
            Vlad Gluschenko
          </p>
        </div>
        <div class="cardtrack__button">
          <button class="playbutton">
            <img src="./../static/img/play.png" alt="" class="playbutton__img">
          </button>
        </div>
      </div>
      <div class="app__trackcard cardtrack">
        <img src="./../static/img/track-1.jpg" alt="Image for card track" class="cardtrack__img">
        <div class="cardtrack__body">
          <p class="cardtrack__title">
            Summer Can Last More
          </p>
          <p class="cardtrack__author">
            Vlad Gluschenko
          </p>
        </div>
        <div class="cardtrack__button">
          <button class="playbutton">
            <img src="./../static/img/play.png" alt="" class="playbutton__img">
          </button>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.container {
  width: 420px;
  padding: 0px 15px;
  margin: 0 auto;
}
.app{
  &__content {
    padding-top: 15px;
  }
  &__header{
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: 8px;
  }
  &__profile{
    width: 25px;
    height: 25px;
    border: 1px solid #1ED760;
    border-radius: 100px;
    display: flex;
    justify-content: center;
    align-content: center;
    transition: 0.4s;
    &:hover {
      opacity: 0.8;
    }
  }
  &__text{
    font-style: normal;
    font-weight: 700;
    font-size: 25px;
    line-height: 30px;
  }
  &__tracklist{
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    gap: 19px;
    padding: 0 5px;
    margin-top: 25px;
    overflow: auto;
    height: 500px;
  }
  &__trackcard{
  }
}
.profile_img{
  width: 25px;
  height: 25px;
}
.cardtrack{
  background: rgba(52, 52, 52, 0.6);
  border-radius: 0px 5px 5px 0px;
  display: flex;
  align-items: center;
  justify-content: start;

  &__img{
    display: block;
    width: 100px;
    height: 100px;
  }
  &__body{
    margin-left: 14px;
    height: 100%;
    // padding: 15px 0px 48px 0px;
    display: flex;
    flex-direction: column;
  }
  &__title{
    margin: 10px 0px 4px 0px;
    font-weight: 700;
    font-size: 16px;
    line-height: 19px;
  }
  &__author{
    margin: 0px;
    font-size: 12px;
    line-height: 14px;
  }
  &__button{
    margin: 0px 14px 0px auto;
  }
}
.playbutton{
  width: 45px;
  height: 45px;
  filter: drop-shadow(0px 1px 1px rgba(0, 0, 0, 0.25));
  background: #1ED760;
  border-radius: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: 0.4s;
  &__img{
    display: block;
    width: 15px;
    height: 15px;
  }
  &:hover{
    opacity: 0.8;
  }
}
</style>
