<template>
  <div>
    <div class="container">
      <br>
      <br>
      <br>
      <b-row>
        <b-col cols="4">
          <div>
            <b-card
              no-body
              style="max-width: 20rem;"
              img-src="https://scontent.fbkk12-3.fna.fbcdn.net/v/t1.0-9/118920358_2823651957918852_4591020093238173501_n.jpg?_nc_cat=102&_nc_sid=730e14&_nc_ohc=5dRm6iX_zwoAX-UUVcf&_nc_ht=scontent.fbkk12-3.fna&oh=06968e7d7b0b29d35cc736e4b602562c&oe=5F8C9A14"
              img-alt="Image"
              img-top
              border-variant="info"
            >
              <template v-slot:header>
                <h1 id="te" class="mb-0">
                  Nonog_music
                </h1>
              </template>

              <b-card-body>
                <input v-model="textSearch " type="text" placeholder="Search">
                <button @click="searchData()">
                  Search
                </button>
              </b-card-body>
            </b-card>
          </div>
        </b-col>
        <b-col cols="8">
          <div v-for="list in playList" :key="list.trackId" class="mt-4">
            <b-card no-body class="overflow-hidden" style="width: 100%;" border-variant="info">
              <b-row no-gutters>
                <b-col md="2">
                  <b-card-img :src="list.artworkUrl100" :alt="list.artistName" class="rounded-0" />
                  <router-link
                    :to="{name: 'MureInfo',params:{TrackName: list.trackName,
                                                   ArtistName: list.artistName,
                                                   CollectionName: list.collectionName,
                                                   TrackNumber: list.trackNumber,
                                                   TrackCount: list.trackCount,
                                                   ReleaseDate: list.releaseDate,
                                                   TrackPrice: list.trackPrice,
                                                   CollectionPrice: list.collectionPrice,
                                                   Currency: list.currency,
                                                   ArtistViewUrl: list.artistViewUrl,
                                                   CollectionViewUrl: list.collectionViewUrl,
                                                   ArtworkUrl100: list.artworkUrl100,
                                                   PreviewUrl: list.previewUrl
                    }}"
                  >
                    <b-button variant="info">
                      --Mure Info--
                    </b-button>
                  </router-link>
                </b-col>
                <b-col id="ta" md="10">
                  <b-card-body :title="list.trackName">
                    <div>Artist : {{ list.artistName }}</div>
                    <div>Collection : {{ list.collectionName }}</div>
                    <b-card-text>
                      <audio controls>
                        <source :src="list.previewUrl" type="audio/mpeg">
                      </audio>
                    </b-card-text>
                  </b-card-body>
                </b-col>
              </b-row>
            </b-card>
          </div>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      playList: null,
      textSearch: ''
    }
  },

  methods: {
    searchData () {
      axios
        .get(
          'https://itunes.apple.com/search?term=+' +
            this.textSearch +
            '&limit=100'
        )
        .then((response) => {
          this.playList = response.data.results.slice(1, 15)
        })
        .catch((err) => {
          // eslint-disable-next-line no-console
          console.log(err)
        })
    }
  }
}
</script>

<style>
#text {
  font-size: 20px;
  color: rgb(0, 0, 0);
}
#te {
  font-size: 40px;
  text-align: center;
}
#ta {
  text-align: center;
}
</style>
