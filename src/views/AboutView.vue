<template>
  <div class="page">
    <header-component></header-component>
    <div class="about">
      <h1>Our Team</h1>
      <div class="team-members">
        <div class="team-member" v-for="member in teamMembers" :key="member.name">
          <h2>{{ member.name }}</h2>
          <p>{{ member.role }}</p>
          <p>{{ member.description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue'

export default {
  components: {
    HeaderComponent
  },
  data() {
    return {
      teamMembers: [
        {
          name: 'Nguyễn Thu Thảo',
          role: 'Project Manager',
          description:
            'Thảo is an experienced project manager who ensures that everything runs smoothly and on time.',
          img: 'nguyen-thu-thao.jpg'
        },
        {
          name: 'Trang',
          role: 'Lead Developer',
          description:
            'Trang is a lead developer with a knack for solving complex problems and creating innovative solutions.',
          img: 'trang.jpg'
        },
        {
          name: 'Mai Phương',
          role: 'UI/UX Designer',
          description:
            'Mai Phương designs intuitive and engaging user interfaces that provide a seamless user experience.',
          img: 'mai-phuong.jpg'
        },
        {
          name: 'Đức Anh',
          role: 'Marketing Specialist',
          description:
            'Đức Anh is a marketing specialist who creates effective marketing strategies to promote our products and services.',
          img: 'duc.jpg'
        }
      ]
    }
  }
}
</script>

<style scoped>
.page {
  color: #333;
}

.about {
  padding: 20px;
  text-align: center;
}

.about h1 {
  font-size: 3em;
  margin-bottom: 20px;
}

.team-members {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.team-member {
  background: #f9f9f9;
  border: 1px solid #e1e1e1;
  border-radius: 10px;
  margin: 10px;
  padding: 20px;
  width: calc(25% - 40px);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition:
    transform 0.3s,
    box-shadow 0.3s;
}

.team-member:hover {
  transform: translateY(-10px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.team-member img {
  border-radius: 50%;
  width: 100px;
  height: 100px;
  object-fit: cover;
  margin-bottom: 15px;
}

.team-member h2 {
  font-size: 1.5em;
  margin-bottom: 10px;
}

.team-member p {
  font-size: 1em;
  line-height: 1.5;
}

@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .team-member {
    width: calc(25% - 20px);
  }
}
</style>
