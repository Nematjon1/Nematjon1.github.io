<template>
  <article class="ottergram">
    <header class="main-header">
      <h1 class="logo-text">ottergram</h1>
    </header>
    <main class="main-content">
      <ul class="thumbnail-list">
        <li class="thumbnail-item">
          <a
            href="@/assets/otters/Barry.jpg"
            data-image-role="trigger"
            data-image-title="Stanley Alive"
            data-image-url="images/Barry.jpg"
          >
            <img
              class="thumbnail-image"
              src="@/assets/otters/Barry.jpg"
              alt="Barry the Otter"
            />
            <span class="thumbnail-title">Barry</span>
          </a>
        </li>
        <li class="thumbnail-item">
          <a
            href="@/assets/otters/Robin.jpeg"
            data-image-role="trigger"
            data-image-title="How Deep Is Your Love"
            data-image-url="images/Robin.jpeg"
          >
            <img
              class="thumbnail-image"
              src="@/assets/otters/Robin.jpeg"
              alt="Robin the Otter"
            />
            <span class="thumbnail-title">Robin</span>
          </a>
        </li>
        <li class="thumbnail-item">
          <a
            href="@/assets/otters/Maurice.jpeg"
            data-image-role="trigger"
            data-image-title="You Should Be Dancing"
            data-image-url="images/Maurice.jpeg"
          >
            <img
              class="thumbnail-image"
              src="@/assets/otters/Maurice.jpeg"
              alt="Maurice the Otter"
            />
            <span class="thumbnail-title">Maurice</span>
          </a>
        </li>
        <li class="thumbnail-item">
          <a
            href="@/assets/otters/Lesley.jpeg"
            data-image-role="trigger"
            data-image-title="Night Fever"
            data-image-url="images/Lesley.jpeg"
          >
            <img
              class="thumbnail-image"
              src="@/assets/otters/Lesley.jpeg"
              alt="Lesley the Otter"
            />
            <span class="thumbnail-title">Lesley</span>
          </a>
        </li>
        <li class="thumbnail-item">
          <a
            href="@/assets/otters/Barbara.jpeg"
            data-image-role="trigger"
            data-image-title="To Love Somebody"
            data-image-url="images/Barbara.jpeg"
          >
            <img
              class="thumbnail-image"
              src="@/assets/otters/Barbara.jpeg"
              alt="Barbara the Otter"
            />
            <span class="thumbnail-title">Barbara</span>
          </a>
        </li>
      </ul>
      <div class="detail-image-container">
        <div class="detail-image-frame" data-image-role="frame">
          <img
            class="detail-image"
            data-image-role="target"
            src="@/assets/otters/Barry.jpg"
            alt=""
          />
          <span class="detail-image-title" data-image-role="title"
            >Stanley Alive</span
          >
        </div>
      </div>
    </main>
  </article>
</template>

<script>
export default {
  name: "Otters",

  data() {
    return {
      DETAIL_IMAGE_SELECTOR: '[data-image-role="target"]',
      DETAIL_TITLE_SELECTOR: '[data-image-role="title"]',
      DETAIL_FRAME_SELECTOR: '[data-image-role="frame"]',
      THUMBNAIL_LINK_SELECTOR: '[data-image-role="trigger"]',
      HIDDEN_DETAIL_CLASS: "hidden-detail",
      TINY_EFFECT_CLASS: "is-tiny",
      ESC_KEY: 27
    };
  },

  methods: {
    setDetails(imageUrl, titleText) {
      let detailImage = document.querySelector(this.DETAIL_IMAGE_SELECTOR);
      detailImage.setAttribute("src", imageUrl);
      let detailTitle = document.querySelector(this.DETAIL_TITLE_SELECTOR);
      detailTitle.textContent = titleText;
    },
    imageFromThumb(thumbnail) {
      return thumbnail.getAttribute("data-image-url");
    },

    titleFromThumb(thumbnail) {
      return thumbnail.getAttribute("data-image-title");
    },

    setDetailsFromThumb(thumbnail) {
      const self = this;
      this.setDetails(
        self.imageFromThumb(thumbnail),
        self.titleFromThumb(thumbnail)
      );
    },

    addThumbClickHendler(thumb) {
      const self = this;
      thumb.addEventListener("click", function(event) {
        event.preventDefault();
        self.setDetailsFromThumb(thumb);
        self.showDetails();
      });
    },
    getThumbnailsArray() {
      let thumbnails = document.querySelectorAll(this.THUMBNAIL_LINK_SELECTOR);
      let thumbnailArray = [].slice.call(thumbnails);
      return thumbnailArray;
    },

    hideDetails() {
      document.body.classList.add(this.HIDDEN_DETAIL_CLASS);
    },

    showDetails() {
      const self = this;
      let frame = document.querySelector(this.DETAIL_FRAME_SELECTOR);
      document.body.classList.remove(this.HIDDEN_DETAIL_CLASS);
      frame.classList.add(this.TINY_EFFECT_CLASS);
      setTimeout(function() {
        frame.classList.remove(self.TINY_EFFECT_CLASS);
      }, 140);
    },

    addKeyPressHandler() {
      const self = this;

      document.body.addEventListener("keyup", function(event) {
        event.preventDefault();
        if (event.keyCode === self.ESC_KEY) {
          self.hideDetails();
        }
      });
    },
    initializeEvents() {
      const self = this;
      let thumbnails = this.getThumbnailsArray();
      thumbnails.forEach(self.addThumbClickHendler);
      this.addKeyPressHandler();
    }
  },

  mounted() {
    this.initializeEvents();
  }
};
</script>

<style lang="scss">
.ottergram {
  background: #503b71;
  display: flex;
  flex-direction: column;
  font-family: "Eagle Lake", Arial, Helvetica, sans-serif;
  font-size: 16px;
}
a[href] {
  text-decoration: none;
}
.main-header {
  flex: 01 auto;
}
.main-content {
  flex: 11 auto;
  flex-direction: column;
  display: flex;
}
.logo-text {
  background: hsl(120, 60%, 90%);
  color: hsl(120, 30%, 40%);
  text-align: center;
  text-transform: uppercase;
  font-family: "Eagle Lake", cursive;
  font-size: 3rem;
  padding: 0.3em 0;
  border-radius: 3px;
}
.thumbnail-list {
  flex: 0 1 auto;
  order: 2;
  display: flex;
  justify-content: space-between;
  list-style: none;
  padding: 20px 0;
  white-space: nowrap;
  overflow-x: auto;
}
.thumbnail-item {
  display: inline-block;
  max-width: 120px;
  min-width: 120px;
  border: 2px solid rgba(80, 58, 112, 0.8);
  transition: transform 133ms ease-in-out;
}
.thumbnail-item:hover {
  transform: scale(1.2);
}
.thumbnail-image {
  display: block;
  max-width: 100%;
  min-height: 100px;
}
.thumbnail-title {
  display: block;
  font-family: "Eagle Lake", cursive;
  margin: 0;
  padding: 4px 10px;
  background: rgb(45, 65, 128);
  color: rgb(47, 202, 107);
  font-size: 1.1rem;
  text-align: center;
}
.detail-image-container {
  flex: 1 1 auto;
  display: flex;
  justify-content: center;
  align-items: center;
}
.detail-image-frame {
  position: relative;
  text-align: center;
  transition: transform 550ms cubic-bezier(0.06, 0.62, 0.92, 0.83);
}
.is-tiny {
  transform: scale(0.001);
  transition: transform 50ms;
}
.detail-image {
  width: 90%;
}
.detail-image-title {
  position: absolute;
  bottom: -16px;
  left: 4px;
  font-family: "EagleLake";
  color: white;
  text-shadow: rgba(0, 0, 0, 0.9) 3px 4px 7px;
  font-size: 40px;
}
.hidden-detail .detail-image-container {
  display: none;
}
.hidden-detail .thumbnail-list {
  flex-direction: column;
  align-items: center;
}
.hidden-detail .thumbnail-item {
  max-width: 80%;
}
@media all and (min-width: 768px) {
  .main-content {
    flex-direction: row;
    overflow: hidden;
  }
  .thumbnail-list {
    flex-direction: column;
    order: 0;
    margin-left: 20px;
    padding: 0 55px;
  }
  .thumbnail-item {
    max-width: 260px;
  }
  .thumbnail-item + .thumbnail-item {
    margin-top: 20px;
  }
}
</style>
