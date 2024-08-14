<template>
  <div>
    <h2>Playing Song</h2>
    <div v-if="selectedSong">
      <img :src="selectedSong.image_url" alt="Song Image" style="width: 100px; height: 100px;">
      <h3>{{ selectedSong.title }}</h3>
      <p>{{ selectedSong.artist }}</p>
    </div>
    <div v-else>
      <p>Please select a song to play.</p>
    </div>

    <h2>Song List</h2>
    <ul>
      <li v-for="song in songs" :key="song.song_id" @click="selectSong(song)">
        <img :src="song.image_url" alt="Song Image" style="width: 50px; height: 50px;">
        <span>{{ song.title }} - {{ song.artist }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      songs: [
        { title: "Song One", artist: "Artist One", song_id: 1, image_url: "https://picsum.photos/100?random=1" },
        { title: "Song Two", artist: "Artist Two", song_id: 2, image_url: "https://picsum.photos/100?random=2" },
        { title: "Song Three", artist: "Artist Three", song_id: 3, image_url: "https://picsum.photos/100?random=3" },
      ],
      selectedSong: null,
    };
  },
  methods: {
    selectSong(song) {
      this.selectedSong = song;
    },
  },
};
</script>

<style scoped>
h2 {
  margin-top: 20px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  cursor: pointer;
  margin: 10px 0;
  display: flex;
  align-items: center;
}

li img {
  margin-right: 10px;
}
</style>
