<template>
  <div class="loader" ref="loader">
    <h1 class="title">Loading...</h1>
  </div>
  <div class="banner section">
    <div class="container">
      <h1 class="title" data-textify-title>Hello</h1>
      <h2 class="sub-title" data-textify>
        Your Name 
      </h2>
      <p class="paragraph" data-textify>
        A short introduction about you. 
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
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
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
        yourname@email.com
      </p>
      <p class="paragraph" data-textify>
        +1 888 222 1111
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
