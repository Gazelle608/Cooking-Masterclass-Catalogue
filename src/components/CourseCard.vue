<template>
  <div class="course-card" :class="{ 'sold-out': !course.available }">
    <div class="card-image">
      <img :src="course.image" :alt="course.title" />
      <div v-if="!course.available" class="sold-out-badge">Sold Out</div>
      <div class="level-badge" :class="course.level.toLowerCase()">
        {{ course.level }}
      </div>
    </div>
    
    <div class="card-content">
      <h3 class="course-title">{{ course.title }}</h3>
      <p class="chef-name">By Chef {{ course.chef }}</p>
      
      <div class="course-details">
        <span class="price">${{ course.price }}</span>
        <button 
          class="save-btn" 
          :class="{ saved: isSaved }"
          @click="toggleSave"
          :disabled="!course.available"
        >
          {{ isSaved ? 'Saved' : 'Save' }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CourseCard',
  props: {
    course: {
      type: Object,
      required: true
    },
    saved: {
      type: Boolean,
      default: false
    }
  },
  emits: ['save', 'unsave'],
  computed: {
    isSaved() {
      return this.saved;
    }
  },
  methods: {
    toggleSave() {
      if (this.isSaved) {
        this.$emit('unsave', this.course.id);
      } else {
        this.$emit('save', this.course.id);
      }
    }
  }
}
</script>

<style scoped>
.course-card {
  background: white;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: all 0.3s ease;
  position: relative;
}

.course-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.15);
}

.course-card.sold-out {
  opacity: 0.7;
}

.card-image {
  position: relative;
  height: 200px;
  overflow: hidden;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.course-card:hover .card-image img {
  transform: scale(1.05);
}

.sold-out-badge {
  position: absolute;
  top: 1rem;
  left: 1rem;
  background: #e74c3c;
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: bold;
}

.level-badge {
  position: absolute;
  top: 1rem;
  right: 1rem;
  padding: 0.4rem 0.8rem;
  border-radius: 15px;
  font-size: 0.7rem;
  font-weight: bold;
  color: white;
}

.level-badge.beginner {
  background: #27ae60;
}

.level-badge.intermediate {
  background: #f39c12;
}

.level-badge.advanced {
  background: #e74c3c;
}

.card-content {
  padding: 1.5rem;
}

.course-title {
  margin: 0 0 0.5rem 0;
  font-size: 1.2rem;
  font-weight: 600;
  color: #2c3e50;
}

.chef-name {
  margin: 0 0 1rem 0;
  color: #7f8c8d;
  font-size: 0.9rem;
}

.course-details {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.price {
  font-size: 1.4rem;
  font-weight: bold;
  color: #e67e22;
}

.save-btn {
  background: #3498db;
  color: white;
  border: none;
  padding: 0.6rem 1.2rem;
  border-radius: 25px;
  cursor: pointer;
  font-weight: 600;
  transition: all 0.3s ease;
}

.save-btn:hover:not(:disabled) {
  background: #2980b9;
  transform: scale(1.05);
}

.save-btn.saved {
  background: #27ae60;
}

.save-btn:disabled {
  background: #bdc3c7;
  cursor: not-allowed;
  transform: none;
}

@media (max-width: 768px) {
  .card-content {
    padding: 1rem;
  }
  
  .course-title {
    font-size: 1.1rem;
  }
  
  .price {
    font-size: 1.2rem;
  }
  
  .save-btn {
    padding: 0.5rem 1rem;
    font-size: 0.9rem;
  }
}
</style>