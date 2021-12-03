<template>
  <div id="container">
    <span class="large-text">
      SEEK <br />
      DISCOMFORT
    </span>
    <div id="hero-section">
      <div class="card-outer">
        <div class="card-inner">
          <div class="image">
            <img src="./assets/IMG_4430.jpg" />
          </div>
          <div class="description">
            <div class="name">Vishank Talesara</div>
            <div class="short-desc">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
              reprehenderit in voluptate velit esse cillum dolore eu fugiat
              nulla pariatur. Excepteur
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
};
</script>

<style lang="scss">
@mixin border-gradient($from, $to, $weight: 0) {
  $mix-main: mix($from, $to);
  $mix-sub-from: mix($mix-main, $from);
  $mix-sub-to: mix($mix-main, $to);

  box-shadow: 0 1px 0 $weight rgba($mix-sub-to, 0.25),
    0 -1px 0 $weight rgba($mix-sub-from, 0.25),
    1px 0 0 $weight rgba($mix-sub-to, 0.25),
    -1px 0 0 $weight rgba($mix-sub-from, 0.25),
    1px -1px 0 $weight rgba($mix-main, 0.5),
    -1px 1px 0 $weight rgba($mix-main, 0.5), 1px 1px 0 $weight rgba($to, 0.75),
    -1px -1px 0 $weight rgba($from, 0.75);
}

#app {
  background-image: url("./assets/pexels-roberto-nickson-2559941.jpeg");
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;
  background-attachment: fixed;
}

#container {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: row;
  backdrop-filter: blur(10px);

  .large-text {
    writing-mode: vertical-lr;
    text-orientation: upright;
    font-family: "Major Mono Display", monospace;
    font-weight: 700;
    color: #e5e5e5;
    font-size: 5rem;
    opacity: 0.45;
  }

  #hero-section {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;

    .card-outer {
      width: 70%;
      height: 25%;
      margin-left: 10%;

      .card-inner {
        display: flex;
        gap: 0.5em;

        .image {
          width: 25%;
          display: flex;
          justify-content: center;
          align-items: center;

          img {
            width: 10em;
            height: 10em;
            border-radius: 50%;
            // @include border-gradient(blue, green);
          }
        }

        .description {
          width: 75%;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
          gap: 0.5em;
          color: #e5e5e5;

          .name {
            font-family: "Shadows Into Light", cursive;
            font-size: 2.5em;
            letter-spacing: 0.2em;
            text-decoration: underline;
          }

          .short-desc {
            font-family: monospace;
            font-size: 1.25em;
            font-weight: 400;
            letter-spacing: 0.125em;
            vertical-align: middle;
            line-height: 1.25em;
          }
        }
      }
    }
  }
}
</style>
