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
import baffle from "baffle";
import { onMounted } from "@vue/runtime-core";

export default {
  name: "App",
  setup() {
    function init(elm) {
      const b = baffle(elm, {
        characters: "zpxzVpasdfh86136░█▒ ░░░█▓ >░░ ▓/▒█▓ █ █>█▒sayg▒ ░░░█▓ >yf",
        speed: 150,
      });
      b.start().reveal(2500);
    }
    onMounted(() => {
      init(".short-desc");
    });
  },
};
</script>

<style lang="scss">
@import "./assets/styles/_include-media.scss";

$breakpoints: (
  sm: 640px,
  md: 768px,
  lg: 1024px,
  xl: 1280px,
  xl2: 1536px,
  xl4: 1920px,
  xl6: 2304px,
);

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
    // font-size: 5rem;
    font-size: 9.75vh;
    opacity: 0.45;
    // background-image: url(https://media.giphy.com/media/26BROrSHlmyzzHf3i/giphy.gif);
    // background-size: cover;
    // color: transparent;
    // background-clip: text;
    // -moz-background-clip: text;
    // -webkit-background-clip: text;
    // text-transform: uppercase;
  }

  #hero-section {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;

    .card-outer {
      width: 70%;
      height: auto;
      margin-left: 10%;

      .card-inner {
        display: flex;
        gap: 0.75em;

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
            font-size: 1rem;
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

@include media("screen", "<sm") {
  #container {
    flex-direction: column-reverse;

    #hero-section {
      height: 70vh;

      .card-outer {
        width: 60%;
        height: 70%;
        margin-left: 0;
        // margin-top: -5%;

        .card-inner {
          flex-direction: column;

          .image {
            width: 100%;

            img {
              width: 60%;
              height: 60%;
            }
          }

          .description {
            width: 100%;

            .name {
              text-align: center;
              font-size: 6.25vw;
            }

            .short-desc {
              text-align: center;
              font-size: 2.6vw;
            }
          }
        }
      }
    }

    .large-text {
      height: 30vh;
      font-size: 16.5vw;
      word-break: break-all;
    }
  }
}

@include media("screen", ">=sm", "<xl") {
  #container {
    #hero-section {
      .card-outer {
        width: 70%;
        height: 60%;
        margin-left: 0;
        // margin-top: -5%;

        .card-inner {
          flex-direction: column;

          .image {
            width: 100%;
          }

          .description {
            width: 100%;

            .name {
              text-align: center;
              font-size: 5.4vw;
            }

            .short-desc {
              text-align: center;
              font-size: 1.25em;
            }
          }
        }
      }
    }
  }
}

@include media("screen", ">=xl4") {
  #container {
    #hero-section {
      .card-outer {
        .card-inner {
          .image {
            img {
              height: 12em;
              width: 12em;
            }
          }
          .description {
            .name {
              font-size: 3em;
            }

            .short-desc {
              font-size: 1.4em;
            }
          }
        }
      }
    }
  }
}

@include media("screen", ">=xl6") {
  #container {
    #hero-section {
      .card-outer {
        .card-inner {
          .image {
            img {
              height: 15em;
              width: 15em;
            }
          }
          .description {
            .name {
              font-size: 5em;
            }

            .short-desc {
              font-size: 1.8em;
            }
          }
        }
      }
    }
  }
}
</style>
