<script setup lang="ts">
import { ref } from 'vue';
import BaseFunctionPage from './BaseFunctionPage.vue';

const pageData = {
  title: '智眸千析',
  subtitle: '多模态融合，LLM对话，精准识人与智能交互。',
  description: '基于深度学习技术的人物特征识别与分析系统，能够自动从图像中识别和提取人物的多维特征信息。系统支持性别、年龄、服装颜色等多项特征的精确识别，并通过自然语言交互界面呈现分析结果，为安防监控、人员管理等领域提供智能化解决方案。',
  image: new URL('@/assets/function/person.png', import.meta.url).href,
  features: [
    {
      title: '多模型特征融合',
      description: '采用多个专业模型协同工作的方式，分别提取人物的不同特征，然后通过特征融合算法将各模型结果整合，实现更高精度的人物特征识别，有效提升边界情况的识别准确率。',
      icon: 'https://ext.same-assets.com/794583279/2838098675.svg'
    },
    {
      title: '深度学习识别算法',
      description: '基于ResNet50、YOLO等深度学习模型，结合改进的特征提取网络，通过大量训练数据实现对人物性别、年龄段、服装颜色等特征的精确识别，模型经过优化后在复杂场景下仍能保持较高准确率。',
      icon: 'https://ext.same-assets.com/794583279/2018733539.svg'
    },
    {
      title: '多模态语义理解',
      description: '将自然语言处理与计算机视觉技术相结合，支持用户通过自然语言描述查询特定特征的人物，系统能够理解查询意图并在图像中定位匹配的目标，实现"查找穿红色衣服的中年男性"等复杂查询任务。',
      icon: 'https://ext.same-assets.com/794583279/2067545548.svg'
    }
  ],
  actionRoute: '/domain/person-recognition/app',
  actionText: '开始使用智眸千析'
};
</script>

<template>
  <BaseFunctionPage
    :title="pageData.title"
    :subtitle="pageData.subtitle"
    :description="pageData.description"
    :image="pageData.image"
    :features="pageData.features"
    :actionRoute="pageData.actionRoute"
    :actionText="pageData.actionText"
  />
</template> 