<template>
  <div id="app">
    <AppHeader :wishlist-count="wishlist.length" />
    
    <main class="main-content">
      <div class="container">
        <div class="catalogue-header">
          <h2>Available Cooking Classes</h2>
          <div class="controls">
            <button 
              class="filter-btn" 
              :class="{ active: showAvailableOnly }"
              @click="toggleFilter"
            >
              {{ showAvailableOnly ? 'Show All' : 'Available Only' }}
            </button>
          </div>
        </div>
        
        <div class="courses-grid">
          <CourseCard
            v-for="course in filteredCourses"
            :key="course.id"
            :course="course"
            :saved="wishlist.includes(course.id)"
            @save="addToWishlist"
            @unsave="removeFromWishlist"
          />
        </div>
        
        <div v-if="filteredCourses.length === 0" class="empty-state">
          <h3>No courses found</h3>
          <p>Try adjusting your filters or check back later for new classes.</p>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import { courses } from './data/courses.js'
import AppHeader from './components/Header.vue'
import CourseCard from './components/CourseCard.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    CourseCard
  },
  data() {
    return {
      courses: courses,
      wishlist: [],
      showAvailableOnly: false
    }
  },
  computed: {
    filteredCourses() {
      if (this.showAvailableOnly) {
        return this.courses.filter(course => course.available)
      }
      return this.courses
    }
  },
  methods: {
    addToWishlist(courseId) {
      if (!this.wishlist.includes(courseId)) {
        this.wishlist.push(courseId)
      }
    },
    removeFromWishlist(courseId) {
      this.wishlist = this.wishlist.filter(id => id !== courseId)
    },
    toggleFilter() {
      this.showAvailableOnly = !this.showAvailableOnly
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f8f9fa;
  color: #333;
  line-height: 1.6;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.main-content {
  padding: 2rem 0;
}

.catalogue-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 2rem;
  flex-wrap: wrap;
  gap: 1rem;
}

.catalogue-header h2 {
  color: #2c3e50;
  font-size: 2rem;
}

.controls {
  display: flex;
  gap: 1rem;
}

.filter-btn {
  background: #95a5a6;
  color: white;
  border: none;
  padding: 0.7rem 1.5rem;
  border-radius: 25px;
  cursor: pointer;
  font-weight: 600;
  transition: all 0.3s ease;
}

.filter-btn.active {
  background: #3498db;
}

.filter-btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.2);
}

.courses-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 2rem;
}

.empty-state {
  text-align: center;
  padding: 3rem;
  color: #7f8c8d;
}

.empty-state h3 {
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

@media (max-width: 768px) {
  .courses-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .catalogue-header {
    flex-direction: column;
    align-items: flex-start;
  }
  
  .catalogue-header h2 {
    font-size: 1.6rem;
  }
  
  .main-content {
    padding: 1.5rem 0;
  }
}

@media (max-width: 480px) {
  .courses-grid {
    grid-template-columns: 1fr;
  }
  
  .container {
    padding: 0 0.5rem;
  }
}
</style>