<template>
  <div id="events">
    <div class="slider">
      <div class="slides">
        <transition-group
          name="slide"
          mode="out-in"
          enter-class="slide-in"
          leave-class="slide-out"
          enter-active-class="slide-in-active"
          leave-active-class="slide-out-active"
        >
          <div v-for="(group, index) in visibleSlides" :key="index" class="slide-group">
            <div
              v-for="event in group"
              :key="event.id"
              class="slide-card"
              @click="showDetails(event)"
              :style="{ backgroundImage: `url(${event.image})` }"
            >
              <div class="overlay"></div>
              <div class="slide-content">
                <h3>{{ event.title }}</h3>
                <h4>{{ event.date }}</h4>
              </div>
            </div>
          </div>
        </transition-group>
      </div>
      <div class="nav-buttons">
        <span class="prev" @click="move(-1)">
          <i class="fa fa-chevron-left" aria-hidden="true"></i>
        </span>
        <span class="next" @click="move(1)">
          <i class="fa fa-chevron-right" aria-hidden="true"></i>
        </span>
      </div>
    </div>
    <EventModal v-if="showModal" :show="showModal" :event="selectedEvent" @close="showModal = false" />
  </div>
</template>

<script>
import EventModal from './EventModal.vue';

// Import images from assets
const images = [
  require('@/assets/pic1.jpg'),
  require('@/assets/pic2.jpg'),
  require('@/assets/pic3.jpg'),
  require('@/assets/pic4.jpg'),
  require('@/assets/pic5.jpg'),
  require('@/assets/pic6.jpg'),
  require('@/assets/pic7.jpg')
];

export default {
  components: {
    EventModal
  },
  data() {
    return {
      events: [
        { id: 1, title: 'Event 1', date: '2024-08-01', image: images[0], details: 'Details of Event 1' },
        { id: 2, title: 'Event 2', date: '2024-08-02', image: images[1], details: 'Details of Event 2' },
        { id: 3, title: 'Event 3', date: '2024-08-03', image: images[2], details: 'Details of Event 3' },
        { id: 4, title: 'Event 4', date: '2024-08-04', image: images[3], details: 'Details of Event 4' },
        { id: 5, title: 'Event 5', date: '2024-08-05', image: images[4], details: 'Details of Event 5' },
        { id: 6, title: 'Event 6', date: '2024-08-06', image: images[5], details: 'Details of Event 6' },
        { id: 7, title: 'Event 7', date: '2024-08-07', image: images[6], details: 'Details of Event 7' }
      ],
      cardsPerSlide: 3,
      activeSlide: 1,
      showModal: false,
      selectedEvent: {}
    };
  },
  computed: {
    totalSlides() {
      return Math.ceil(this.events.length / this.cardsPerSlide);
    },
    visibleSlides() {
      const groups = [];
      for (let i = 0; i < this.events.length; i += this.cardsPerSlide) {
        groups.push(this.events.slice(i, i + this.cardsPerSlide));
      }
      return groups;
    }
  },
  methods: {
    move(amount) {
      let newSlide = this.activeSlide + amount;
      if (newSlide > this.totalSlides) newSlide = 1;
      if (newSlide < 1) newSlide = this.totalSlides;
      this.activeSlide = newSlide;
      this.updateTransform();
    },
    updateTransform() {
      const offset = (this.activeSlide - 1) * 100;
      document.querySelector('.slides').style.transform = `translateX(-${offset}%)`;
    },
    showDetails(event) {
      this.selectedEvent = event;
      this.showModal = true;
    }
  }
};
</script>

<style scoped>
.slider {
  overflow: hidden;
  position: relative;
  width: 100%;
  height: 300px;
}

.slides {
  display: flex;
  transition: transform 0.5s ease;
}

.slide-group {
  display: flex;
  flex: 0 0 100%;
}

.slide-card {
  flex: 1 0 33.333%;
  box-sizing: content-box;
  padding: 30px;
  margin: 30px 15px;
  min-height: 200px;
  position: relative;
  background-size: cover;
  background-position: center;
  border-radius: 10px;
  cursor: pointer;
  color: white;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.5);
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  border-radius: 10px;
}

.slide-content {
  position: relative;
  text-align: center;
  z-index: 1;
}

.slide-content h3 {
  font-size: 18px;
  font-weight: bold;
  margin: 10px 0 5px 0;
}

.slide-content h4 {
  font-size: 14px;
  margin: 0;
}

.nav-buttons {
  position: absolute;
  top: 50%;
  width: 100%;
  display: flex;
  justify-content: space-between;
  transform: translateY(-50%);
}

.prev, .next {
  font-size: 24px;
  cursor: pointer;
  user-select: none;
  color: #007bff;
  padding: 10px;
}
</style>
