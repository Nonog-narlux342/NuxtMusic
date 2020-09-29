<template>
  <div id="bg">
    <div>
      <b-navbar toggleable="lg" type="dark" variant="Light">
        <b-avatar
          src="https://scontent.fbkk13-1.fna.fbcdn.net/v/t1.0-9/119161132_2829624320654949_2049276399592569660_n.jpg?_nc_cat=108&_nc_sid=09cbfe&_nc_ohc=PXgWT337WEQAX-0MIQR&_nc_ht=scontent.fbkk13-1.fna&oh=842f1118ab4fea753f23690f3c6e073d&oe=5F8C2189"
          size="5%"
        />
        <b-navbar-toggle target="nav-collapse" />
        <b-collapse id="nav-collapse" is-nav>
          <br>
          <b-navbar-brand href="#">
            Nonog_narlux
          </b-navbar-brand>
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-navbar-nav>
              <b-nav-item to="/">
                Home
              </b-nav-item>
              <b-nav-item to="/Credit">
                Credit
              </b-nav-item>
            </b-navbar-nav>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
    </div>
    <Nuxt />
    <br><br><br><br><br>
  </div>
</template>
<script>
export default {}
</script>
<style>
#bg {
  background-image: url(https://vorhaus.com/wp-content/uploads/2014/07/cloud-bg.png);
  background-size: cover;
}
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
