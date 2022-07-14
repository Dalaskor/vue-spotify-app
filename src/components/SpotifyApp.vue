<template>
<div class="container">
  <div class="app__content">
    <div class="app__header">
      <div class="app__profile">
        <img src="./../static/img/profile.png" alt="Profile image" class="profile_img">
      </div>
      <p class="app__title">
        Your Feed
      </p>
    </div>
    <div class="app__tracklist">
      <div class="app__trackcard cardtrack" v-for="song in songs" :key="song.src">
        <img :src="song.srcImg" alt="Image for card track" class="cardtrack__img">
        <div class="cardtrack__body">
          <p class="cardtrack__title">
            {{ song.title }}
          </p>
          <p class="cardtrack__author">
            {{ song.artist }}
          </p>
        </div>
        <div class="cardtrack__button">
          <button class="playbutton" @click="play(song)">
            <img src="./../static/img/play.png" alt="" class="playbutton__img">
          </button>
        </div>
      </div>
    </div>
    <div class="app__currentsong">
      <span class="app__curArtist">
        {{ current.artist }}
      </span>
      -
      <span class="app__curTitle">
        {{ current.title }}
      </span>
    </div>
    <div class="app__footer footer">
      <!-- <div class="footer__fullbtn">
        <button class="btnfullscreen">
        </button>
      </div> -->
      <div class="footer__prevbtn">
        <button class="btnprev" @click="prev">
          <img src="./../static/img/prevbtn.png" alt="">
        </button>
      </div>
      <div class="footer__playbtn">
        <button class="btnplay" v-if="!isPlaying" @click="play">
        </button>
        <button class="btnplay pause" v-else @click="pause">
        </button>
      </div>
      <div class="footer__nextbtn">
        <button class="btnnext" @click="next">
          <img src="./../static/img/nextbtn.png" alt="">
        </button>
      </div>
      <!-- <div class="footer__shufflebtn">
        <button class="btnshuffle">
          <img src="./../static/img/shufflebtn.png" alt="">
        </button>
      </div> -->
    </div>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      isPlaying: false,
      current: {},
      index: 0,
      songs: [
        {
          title: 'Summer Can Last More',
          artist: 'Vlad Gluschenko',
          // eslint-disable-next-line
          src: require('../static/sound/track-1.wav'),
          // eslint-disable-next-line
          srcImg: require('../static/img/track-1.jpg'),
        },
        {
          title: 'Insomnia',
          artist: 'Nomyn',
          // eslint-disable-next-line
          src: require('../static/sound/track-2.mp3'),
          // eslint-disable-next-line
          srcImg: require('../static/img/track-2.jpg'),
        },
        {
          title: 'what if i forget?',
          artist: 'kaleido',
          // eslint-disable-next-line
          src: require('../static/sound/track-3.mp3'),
          // eslint-disable-next-line
          srcImg: require('../static/img/track-3.jpg'),
        },
      ],
      player: new Audio(),
    };
  },
  created() {
    this.current = this.songs[this.index];
    this.player.src = this.current.src;
  },
  methods: {
    play(song) {
      if (typeof song.src !== 'undefined') {
        this.current = song;
        this.player.src = this.current.src;
      }
      this.player.play();
      // eslint-disable-next-line
      this.player.addEventListener('ended', function () {
        this.index += 1;
        if (this.index > this.songs.length - 1) {
          this.index = 0;
        }
        this.isPlaying = true;
        this.current = this.songs[this.index];
        this.play(this.current);
      }.bind(this));
      this.isPlaying = true;
    },
    pause() {
      this.player.pause();
      this.isPlaying = false;
    },
    prev() {
      this.index -= 1;
      if (this.index < 0) {
        this.index = this.songs.length - 1;
      }
      this.isPlaying = true;
      this.current = this.songs[this.index];
      this.play(this.current);
    },
    next() {
      this.index += 1;
      if (this.index > this.songs.length - 1) {
        this.index = 0;
      }
      this.isPlaying = true;
      this.current = this.songs[this.index];
      this.play(this.current);
    },
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
  &__title{
    margin: 0;
    font-style: normal;
    font-weight: 700;
    font-size: 25px;
    line-height: 30px;
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
  &__trackcard {
  }
  &__currentsong {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 10px 0px 0px 0px;
    font-size: 12px;
  }
  &__curTitle {
    display: block;
    font-size: 12px;
    margin-left: 10px;
  }
  &__curArtist {
    display: block;
    font-size: 12px;
    margin-right: 10px;
  }
  &__footer {
    margin-top: 25px;
  }
}
.footer {
  width: 100%;
  display: flex;
  justify-content: center;
  align-content: center;
  gap: 40px;
  &__fullbtn {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  &__prevbtn {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__playbtn {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  &__nextbtn {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__shufflebtn {
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
.btnfullscreen {
  border: solid #ffffff;
  background-color: #121212;
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 5px;
  transform: rotate(-135deg);
  -webkit-transform: rotate(-135deg);
  transition: 0.4s;
  &:hover{
    opacity: 0.8;
  }
}
.btnshuffle {
  width: 50px;
  height: 50px;
  background: none;
  border: none;
  border-radius: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 0.4s;
  & img{
    width: 25px;
    height: 25px;
  }
  &:hover{
    opacity: 0.8;
  }
}
.btnnext {
  width: 50px;
  height: 50px;
  background: none;
  border: none;
  border-radius: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 0.4s;
  & img{
    width: 25px;
    height: 25px;
  }
  &:hover{
    opacity: 0.8;
  }
}
.btnplay {
  height: 76px;
  width: 76px;
  border: none;
  border-radius: 100px;
  background: none;
  background: url(./../static/img/playbtn.png) no-repeat center center;
  background-color: #FFFFFF;
  transition: 0.4s;
  &.pause {
    background: none;
    background: url(./../static/img/pausebtn.png) no-repeat center center;
    background-color: #FFFFFF;
  }
  &:hover{
    opacity: 0.8;
  }
}
.btnprev {
  width: 50px;
  height: 50px;
  background: none;
  border: none;
  border-radius: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 0.4s;
  & img{
    width: 25px;
    height: 25px;
  }
  &:hover{
    opacity: 0.8;
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
  border: none;
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
