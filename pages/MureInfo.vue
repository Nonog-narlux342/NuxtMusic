<template>
  <div class="container">
    <br>
    <br>
    <br>
    <div>
      <b-card bg-variant="Default">
        <b-container class="bv-example-row">
          <b-row>
            <b-col><b-card-img :src="music.ArtworkUrl100" class="rounded-0" /></b-col>
            <b-col>
              <h1 id="hp">
                {{ music.TrackName }}
              </h1>
              <br>
              <div id="te">
                <h4>Artist : {{ music.ArtistName }}</h4>
                <h4>Collection : {{ music.CollectionName }}</h4>
                <h4>Track Number : {{ music.TrackNumber }}/{{ music.TrackCount }}</h4>
                <h4>Primary Genre : {{ music.PrimaryGenreName }}</h4>
                <h4>Release Date : {{ music.ReleaseDate }}</h4>
                <h4>Track Price : {{ music.TrackPrice }} {{ music.Currency }}</h4>
                <h4>Collection Price : {{ music.CollectionPrice }} {{ music.Currency }}</h4>
                <br>
                <audio controls>
                  <source :src="music.PreviewUrl" type="audio/mpeg">
                </audio>
                <br><br>
                <div>
                  <b-button variant="info" :href="music.ArtistViewUrl">
                    View on Artist
                  </b-button>
                  <b-button variant="info" :href="music.CollectionViewUrl">
                    View on Collection
                  </b-button>
                </div>
              </div>
            </b-col>
          </b-row>
        </b-container>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      music: this.$route.params
    }
  }
}
</script>
<style>
#te {
  font-size: 20px;
  text-align: center;
}
#hp {
  text-align: center;
}

</style>
