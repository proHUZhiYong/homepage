<script setup>
import { ref } from 'vue'

const showContact = ref(false)

const toggleContact = () => {
  showContact.value = !showContact.value
}

const skills = [
  {
    category: '前端',
    icon: '💻',
    description: '熟悉vue3，react，vite等技术'
  },
  {
    category: '后端',
    icon: '⚙️',
    description: 'node等'
  },
  {
    category: '移动端',
    icon: '📱',
    description: 'H5，微信小程序开发'
  }
]

const socialPlatforms = [
  {
    name: '公众号',
    icon: '📢',
    url: 'https://mp.weixin.qq.com/s/fGVIebz-zFlkyFLJDISu-w'
  }
]
</script>

<template>
  <div class="homepage">
    <!-- 头像和个人信息 -->
    <div class="profile">
      <img src="./assets/images/avatar.jpg" alt="头像" class="avatar" />
      <h1 class="name">小伍</h1>
    </div>

    <!-- 个人标签 -->
    <div class="tags">
      <span class="tag">独立开发者</span>
      <span class="tag">内容创作者</span>
      <span class="tag">AIP万粉博主</span>
    </div>

    <!-- 联系我 -->
    <button class="contact-btn" @click="toggleContact">联系我</button>

    <!-- 联系图片弹窗 -->
    <div v-if="showContact" class="contact-modal" @click="toggleContact">
      <div class="contact-content" @click.stop>
        <img src="./assets/images/contact.png" alt="联系方式" class="contact-img" />
        <button class="close-btn" @click="toggleContact">关闭</button>
      </div>
    </div>

    <!-- 专业技能 -->
    <div class="skills">
      <h2 class="section-title">专业技能</h2>
      <div class="skills-grid">
        <div v-for="(skill, index) in skills" :key="index" class="skill-item">
          <div class="skill-icon">{{ skill.icon }}</div>
          <h3 class="skill-category">{{ skill.category }}</h3>
          <p class="skill-description">{{ skill.description }}</p>
        </div>
      </div>
    </div>

    <!-- 社交平台 -->
    <div class="social">
      <h2 class="section-title">社交平台</h2>
      <div class="social-grid">
        <a v-for="(platform, index) in socialPlatforms" :key="index" :href="platform.url" target="_blank" class="social-item">
          <div class="social-icon">{{ platform.icon }}</div>
          <span class="social-name">{{ platform.name }}</span>
        </a>
      </div>
    </div>

    <!-- 实用小工具 -->
    <div class="tools">
      <h2 class="section-title">实用小工具</h2>
      <div class="tools-placeholder">
        <p>正在开发中~</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* 全局样式在style.css中定义 */
</style>
