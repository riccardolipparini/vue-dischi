<template>
  <header>
    <div id="spotify">
      <img
        src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/74/Spotify_App_Logo.svg/2048px-Spotify_App_Logo.svg.png"
        alt=""
      />
      <select>
      <option value="">Seleziona un Genere</option>
      <option></option>
      </select>
    </div>
  </header>
</template>

<script>
export default {
  name: "Background",

};
</script>

<style lang="scss">
#spotify {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 100px;
  width: 100%;
  background-color: grey;
  img {
    width: 80px;
    height: 80px;
  }
}
</style>