<template>
  <div class="loader" ref="loader">
    <h1 class="title">Loading...</h1>
  </div>
  <div class="banner section">
    <div class="container">
      <h1 class="title" data-textify-title>Hello</h1>
      <h2 class="sub-title" data-textify>
        Payam Dowlatyari 
      </h2>
      <p class="paragraph" data-textify>
        I am a software engineer, UX designer, photographer, and blogger. 
        </p>
    </div>
  </div>
    <div class="container">
      <div class="section-media">
        <ParallaxImage
          src="1.jpg"
          alt="Image"
          className="section-media-image"
          wrapperClassName="section-media-wrapper"
        />
      </div>
      <div class="section-content">
        <h1 class="title" data-textify-title>
         About
        </h1>
        <p class="paragraph" data-textify>
        I studied Software Engineering at UC Irvine and graduated in 2020. 
        I have been working in Silicon Valley as a full-stack web developer since then with a focus 
        on the design and implementation of user interfaces using JavaScript-based frameworks and libraries. 
        I am a hobbyist photographer and blogger interested in art, philosophy, and social sciences.
        </p>
      </div>
    </div>
  <div class="images-gallery">
    <div class="container">
      <ParallaxImage
        src="3.jpg"
        alt="Image"
        className="gallery-image"
        wrapperClassName="image-wrapper"
      />
      <ParallaxImage
        src="4.jpg"
        alt="Image"
        className="gallery-image"
        wrapperClassName="image-wrapper"
      />
    </div>
  </div>
  <div class="center-section">
    <div class="container">
      <h1 class="title" data-textify-title>Contact</h1>
      <p class="paragraph" data-textify>
        contact@payamd.com
      </p>
      <p class="paragraph" data-textify>
        +1 916 547 8918
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  data() {
    return {
      images: null,
      loaded: false
    };
  },
  methods: {
    createLoader() {
      this.images = document.querySelectorAll("img");
      new this.$loader({
        images: this.images,
        onLoaded: () => {
          this.loaded = true;
          document.body.classList.add("loaded");
          new this.$textify(); // text animations
        }
      });
    }
  },
  watch: {
    loaded() {
      if (this.loaded) {
        this.$refs.loader.classList.add("inactive");

        setTimeout(() => {
          this.$refs.loader.remove();
        }, 1000);
      }
    }
  },
  mounted() {
    this.createLoader();
  }
};
</script>

<style lang="scss" scoped></style>
