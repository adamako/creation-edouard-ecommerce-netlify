<template>
  <section class="boxes">
    <div v-for="(box, i) in boxes" :key="box.heading" :class="`box${i}`">
      <nuxt-link :to="box.uri">
        <img :src="box.icon" alt="service icon"/>
      </nuxt-link>
      <h4>
        <nuxt-link :to="box.uri">
          {{ box.heading }}
        </nuxt-link>
      </h4>
    </div>
  </section>
</template>

<script>
    export default {
        data() {
            return {
                boxes: [
                    {
                        uri: "/men",
                        icon: "/icon-cal.svg",
                        heading: "Collection hommes",
                        details: ""
                    },
                    {
                        uri: "/children",
                        icon: "/icon-service.svg",
                        heading: "Collection enfants",
                        details: ""
                    },
                    {
                        uri: "/women",
                        icon: "/icon-package.svg",
                        heading: "collection femmes",
                        details: ""
                    }
                ]
            };
        }
    };
</script>

<style lang="scss" scoped>
  .boxes {
    margin: 70px 0;

    div {
      border: 1px solid #ddd;
      min-height: 150px;
      justify-self: center;
      align-self: center;
      text-align: center;
    }

    .box1 {
      grid-area: 1 / 1 / 2 / 2;
    }

    .box2 {
      grid-area: 1 / 2 / 2 / 3;
    }

    .box3 {
      grid-area: 1 / 3 / 2 / 4;
    }
  }

  h4 {
    text-transform: uppercase;
    letter-spacing: 0.15em;
    margin: 0 0 10px 0;
  }

  @media screen and (min-width: 700px) {
    .boxes {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      grid-template-rows: 1fr;
      grid-column-gap: 20px;
      grid-row-gap: 0px;

      div {
        padding: 40px 50px;
      }
    }
  }

  @media screen and (max-width: 699px) {
    .boxes {
      width: 83vw;
      margin-left: 5vw;

      div {
        padding: 10px 20px;
        margin-bottom: 10px;
      }
    }
  }
</style>
