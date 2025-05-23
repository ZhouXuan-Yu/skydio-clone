/**
 * 文件名: HomeView.vue
 * 描述: 网站首页视图
 * 在项目中的作用: 
 * - 作为用户访问网站的第一个页面
 * - 展示产品的主要特点和核心功能
 * - 提供导航到其他页面的入口
 * - 通过视觉元素和交互体验吸引用户
 */

<script setup lang="ts">
import { ref } from 'vue';
import { useRouter } from 'vue-router';
import HeroBanner from '../components/home/HeroBanner.vue';
import MissionStatement from '../components/home/MissionStatement.vue';
import VideoProductShowcase from '../components/home/VideoProductShowcase.vue';
import ProductHighlights from '../components/home/ProductHighlights.vue';
import SolutionsCarousel from '../components/home/SolutionsCarousel.vue';
import ActionCards from '../components/home/ActionCards.vue';
import SuccessStories from '../components/home/SuccessStories.vue';
import CtaSection from '../components/home/CtaSection.vue';
import TransitionBanner from '../components/home/TransitionBanner.vue';

const router = useRouter();
const videoShowcaseRef = ref<HTMLElement | null>(null);
const secondShowcaseRef = ref<HTMLElement | null>(null);
const productHighlightsRef = ref<HTMLElement | null>(null);

// 第一个产品数据
const productOne = {
  title: '低空多模态感知平台',
  subtitle: "融合可见光与热成像数据，结合深度学习算法，实现复杂环境下的小目标精准探测",
  description: '针对低空经济中的智能感知需求，我们创新性地融合可见光与热成像数据，采用深度学习模型进行小目标检测与识别。该平台不仅提升了低空场景的感知能力，还为低空经济活动提供了更可靠的监测手段，广泛应用于夜间安保巡检、复杂地形测绘等低空经济活动。',
  imageSrc: new URL('@/assets/images/homepageRemote.jpg', import.meta.url).href,
  ctaLink: '/products/sensing'
};

// 第二个产品数据
const productTwo = {
  title: '智能决策与应用平台',
  subtitle: '基于知识图谱与语义理解技术，提供智能问答与决策支持，助力低空经济智慧运营',
  description: '智能决策与应用平台整合低空经济领域的专业知识，通过知识图谱技术构建领域知识网络，应用自然语言处理技术实现精准理解与查询。该平台为无人机飞行任务规划、低空经济产业园区运营管理等场景提供精准决策建议，有效提升运营效率，符合国家政策中培育低空经济新质生产力的要求。',
  imageSrc: new URL('@/assets/images/homepageKnowledge1.jpg', import.meta.url).href
};

// Smooth scroll to the video showcase section
const scrollToVideoShowcase = () => {
  if (videoShowcaseRef.value) {
    videoShowcaseRef.value.scrollIntoView({ behavior: 'smooth' });
  }
};

// Smooth scroll to the second showcase section
const scrollToSecondShowcase = () => {
  if (secondShowcaseRef.value) {
    secondShowcaseRef.value.scrollIntoView({ behavior: 'smooth' });
  }
};

// Smooth scroll to the product highlights section
const scrollToProductHighlights = () => {
  if (productHighlightsRef.value) {
    productHighlightsRef.value.scrollIntoView({ behavior: 'smooth' });
  }
};

// 前往无人机任务页面
const goToDroneTask = () => {
  router.push('/drone-task');
};
</script>

<template>
  <main class="home-view">
    <!-- 首屏区域 -->
    <HeroBanner @scroll-to-showcase="scrollToVideoShowcase" />
    
    <!-- 演示功能入口 -->
    <!-- <div class="demo-section">
      <div class="container mx-auto px-4 py-8">
        <h2 class="text-2xl font-bold text-center mb-8">产品功能演示</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div class="demo-card" @click="router.push('/data-dashboard-detail')">
            <div class="demo-icon">📊</div>
            <h3>数据仪表盘</h3>
            <p>查看无人机数据分析和可视化界面</p>
          </div>
          
          <div class="demo-card" @click="goToDroneTask">
            <div class="demo-icon">🛸</div>
            <h3>无人机巡逻任务</h3>
            <p>查看正在执行的无人机巡逻任务</p>
          </div>
          
          <div class="demo-card" @click="router.push('/geo-api')">
            <div class="demo-icon">🗺️</div>
            <h3>地理服务API</h3>
            <p>体验位置搜索、路径规划等地理服务</p>
          </div>
        </div>
      </div>
    </div> -->
    
    <!-- 过渡区域 - 项目价值主题展示 -->
    <div class="transition-section value-proposition">
      <div class="transition-content">
        <!-- 核心价值主张 -->
        <div class="core-value">
          <h2>多模态感知融合，驱动低空经济智能化发展</h2>
          <div class="divider"></div>
        </div>
        
        <!-- 特色亮点列举 -->
        <div class="features-highlight">
          <div class="feature-item">
            <div class="feature-icon">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <circle cx="12" cy="12" r="3.5" stroke="currentColor" stroke-width="1.5"/>
                <path d="M20.188 10.9343C20.5762 11.4056 20.7703 11.6412 20.7703 12C20.7703 12.3588 20.5762 12.5944 20.188 13.0657C18.7679 14.7899 15.6357 18 12 18C8.36427 18 5.23206 14.7899 3.81197 13.0657C3.42381 12.5944 3.22973 12.3588 3.22973 12C3.22973 11.6412 3.42381 11.4056 3.81197 10.9343C5.23206 9.21014 8.36427 6 12 6C15.6357 6 18.7679 9.21014 20.188 10.9343Z" stroke="currentColor" stroke-width="1.5"/>
              </svg>
            </div>
            <h3>多模态感知</h3>
            <p>融合可见光与热成像<br>实现复杂环境下<br>小目标精准探测</p>
          </div>
          
          <div class="feature-item">
            <div class="feature-icon">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M16 3.93552C18.8915 5.95319 21 9.17319 21 12.7958C21 16.4184 18.8915 19.6384 16 21.6561M16 3.93552C14.5209 2.96773 12.8158 2.41797 11 2.41797C9.18419 2.41797 7.4791 2.96773 6 3.93552M16 3.93552L13.5 8.71656M8 21.6561C5.10851 19.6384 3 16.4184 3 12.7958C3 9.17319 5.10851 5.95319 8 3.93552M8 3.93552L10.5 8.71656M8 3.93552C9.16414 3.16902 10.5439 2.64747 12 2.46582M13.5 16.875C11.8431 15.3961 10.1569 15.3961 8.5 16.875" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>
            <h3>智能灾害预警</h3>
            <p>基于U-Net语义分割<br>实现火灾、洪水<br>早期精准预警</p>
          </div>
          
          <div class="feature-item">
            <div class="feature-icon">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M12 16V14M12 14V12M12 14H18C19.1046 14 20 13.1046 20 12C20 10.8954 19.1046 10 18 10H12M12 8V6M6 10C4.89543 10 4 10.8954 4 12C4 13.1046 4.89543 14 6 14H8M21 3L3 21" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </div>
            <h3>精准识别</h3>
            <p>多模型特征融合<br>深度学习算法<br>实现人物车辆识别</p>
          </div>
          
          <div class="feature-item">
            <div class="feature-icon">
              <svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M4 12C4 8.22876 4 6.34315 5.17157 5.17157C6.34315 4 8.22876 4 12 4C15.7712 4 17.6569 4 18.8284 5.17157C20 6.34315 20 8.22876 20 12C20 15.7712 20 17.6569 18.8284 18.8284C17.6569 20 15.7712 20 12 20C8.22876 20 6.34315 20 5.17157 18.8284C4 17.6569 4 15.7712 4 12Z" stroke="currentColor" stroke-width="1.5"/>
                <path d="M9 10L15 10" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
                <path d="M9 14H12" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"/>
              </svg>
            </div>
            <h3>智能决策支持</h3>
            <p>知识图谱构建<br>语义理解与查询<br>赋能低空智慧运营</p>
          </div>
        </div>
        
        <!-- 项目功能切换引导 -->
        <div class="next-section-guide">
          <h3>更多精彩，即将呈现</h3>
          
          <!-- 关键词云 -->
          <div class="keyword-cloud">
            <span class="keyword size-lg">热成像融合</span>
            <span class="keyword size-md">暗光增强</span>
            <span class="keyword size-xl">灾害预警</span>
            <span class="keyword size-sm">车牌监控</span>
            <span class="keyword size-lg">智能导航</span>
            <span class="keyword size-md">知识图谱</span>
            <span class="keyword size-sm">森林火灾检测</span>
            <span class="keyword size-xl">深度学习</span>
            <span class="keyword size-md">多模态感知</span>
            <span class="keyword size-lg">低空巡检</span>
          </div>
        </div>
      </div>
    </div>
    

    <!-- 使命宣言 -->
    <MissionStatement />
    
    <!-- 第一个视频展示区域 -->
    <div ref="videoShowcaseRef" class="video-showcase-container">
      <VideoProductShowcase :product="productOne" :flipped="false" />
    </div>
    
    <!-- 第二个视频展示区域 -->
    <div ref="secondShowcaseRef" class="video-showcase-container">
      <VideoProductShowcase :product="productTwo" :flipped="false" />
    </div>
    
    <!-- 功能卡片 -->
    <ActionCards />
    
    <!-- 解决方案轮播 -->
    <SolutionsCarousel @scrollToNext="scrollToProductHighlights" />
    
    <!-- 产品亮点 -->
    <div ref="productHighlightsRef">
      <ProductHighlights />
    </div>
    
    <!-- 用户故事 -->
    <SuccessStories
      :stories="[
        {
          title: '智慧森林防火监测',
          description: '基于热成像与可见光融合技术，结合U-Net语义分割网络，实现了对森林火灾的早期预警，准确率提升35%，为国家林业局提供更可靠的森林防火监测手段。',
          icon: 'fire-alert'
        },
        {
          title: '城市低空安防巡检',
          description: '采用多模态特征融合技术，结合深度学习算法，实现对城市低空场景中人员、车辆的精准识别，夜间识别准确率提升40%，助力城市安防智能化升级。',
          icon: 'shield-check'
        },
        {
          title: '应急救援指挥决策',
          description: '融合知识图谱与多源数据分析技术，构建应急救援知识网络，为救援指挥提供智能决策支持，缩短决策时间48%，显著提升救援效率。',
          icon: 'ambulance'
        }
      ]"
    />
    
    <!-- 行动号召 -->
    <CtaSection />
  </main>
</template>

<style scoped>
.home-view {
  padding-top: 60px;
  position: relative;
  overflow-x: hidden;
  background-color: #ffffff;
}

/* 演示功能区域 */
.demo-section {
  background-color: #f8fafc;
  padding: 40px 0;
}

.demo-card {
  background-color: white;
  border-radius: 12px;
  padding: 30px 20px;
  text-align: center;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
  cursor: pointer;
  transition: all 0.3s ease;
}

.demo-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
}

.demo-icon {
  font-size: 2.5rem;
  margin-bottom: 15px;
}

.demo-card h3 {
  font-size: 1.2rem;
  font-weight: 600;
  margin-bottom: 8px;
  color: #1e293b;
}

.demo-card p {
  font-size: 0.9rem;
  color: #64748b;
}

.transition-section {
  position: relative;
  width: 100%;
  background-color: #ffffff;
  margin: 0;
}

.value-proposition {
  background-color: #ffffff;
  padding: 100px 0;
  color: #000000;
  border-top: 1px solid #f0f0f0;
  border-bottom: 1px solid #f0f0f0;
}

.transition-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 30px;
}

/* 核心价值主张样式 */
.core-value {
  text-align: center;
  margin-bottom: 80px;
}

.core-value h2 {
  font-size: 3.2rem;
  font-weight: 700;
  color: #000000;
  margin-bottom: 20px;
  letter-spacing: -0.5px;
  line-height: 1.2;
}

.divider {
  width: 60px;
  height: 4px;
  background-color: #3498db;
  margin: 0 auto;
}

/* 特色亮点样式 */
.features-highlight {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 40px;
  margin-bottom: 90px;
}

.feature-item {
  text-align: center;
  padding: 30px 20px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border-radius: 8px;
}

.feature-item:hover {
  transform: translateY(-8px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
}

.feature-icon {
  margin: 0 auto 20px;
  width: 65px;
  height: 65px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #3498db;
  background-color: rgba(52, 152, 219, 0.08);
  border-radius: 50%;
  padding: 15px;
}

.feature-icon svg {
  width: 32px;
  height: 32px;
}

.feature-item h3 {
  font-size: 1.5rem;
  font-weight: 600;
  color: #000000;
  margin-bottom: 15px;
}

.feature-item p {
  font-size: 1rem;
  color: #666666;
  line-height: 1.7;
}

/* 项目功能切换引导样式 */
.next-section-guide {
  text-align: center;
  margin-top: 60px;
}

.next-section-guide h3 {
  font-size: 2rem;
  font-weight: 600;
  color: #000000;
  margin-bottom: 35px;
  opacity: 0.9;
}

.keyword-cloud {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 25px;
  max-width: 900px;
  margin: 0 auto;
}

.keyword {
  display: inline-block;
  padding: 10px 20px;
  border-radius: 50px;
  background-color: #f7f9fc;
  font-weight: 500;
  transition: all 0.3s ease;
}

.keyword:hover {
  background-color: #e1e8f0;
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
}

.size-sm {
  font-size: 0.9rem;
}

.size-md {
  font-size: 1.2rem;
}

.size-lg {
  font-size: 1.4rem;
}

.size-xl {
  font-size: 1.6rem;
}

/* 移除可能造成蒙图效果的伪元素 */
.transition-section::before,
.transition-section::after {
  display: none;
}

.video-showcase-container {
  position: relative;
  min-height: auto;
  overflow: visible;
  z-index: 1;
  background-color: #ffffff;
  margin: 0;
}

/* 确保视频区域与过渡区域无缝衔接 */
.video-showcase-container + .video-showcase-container {
  margin-top: 0;
}

/* 移除波浪效果的伪元素 */
.wave-divider {
  display: none;
}

@media (max-width: 1200px) {
  .core-value h2 {
    font-size: 2.8rem;
  }
}

@media (max-width: 992px) {
  .features-highlight {
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
  }
  
  .value-proposition {
    padding: 80px 0;
  }
  
  .core-value {
    margin-bottom: 60px;
  }
  
  .core-value h2 {
    font-size: 2.5rem;
  }
}

@media (max-width: 768px) {
  .value-proposition {
    padding: 60px 0;
  }
  
  .transition-content {
    padding: 0 20px;
  }
  
  .core-value {
    margin-bottom: 50px;
  }
  
  .core-value h2 {
    font-size: 2.2rem;
  }
  
  .features-highlight {
    grid-template-columns: 1fr;
    gap: 25px;
    margin-bottom: 50px;
  }
  
  .feature-item {
    padding: 20px 15px;
  }
  
  .next-section-guide h3 {
    font-size: 1.6rem;
    margin-bottom: 25px;
  }
  
  .keyword-cloud {
    gap: 15px;
  }
  
  .size-xl {
    font-size: 1.4rem;
  }
  
  .size-lg {
    font-size: 1.2rem;
  }
  
  .home-view {
    padding-top: 40px;
  }
}
</style>
