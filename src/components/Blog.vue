<template>
  <div class="blog-container">
    <div class="blog-header">
      <h1 class="blog-title">我的博客</h1>
      <p class="blog-subtitle">记录技术学习与生活感悟</p>
    </div>
    
    <div class="blog-content">
      <div class="blog-intro">
        <h2 class="section-title">关于博客</h2>
        <p class="intro-text">
          欢迎来到我的个人博客！在这里，我会分享技术学习心得、项目开发经验、
          以及对前端技术发展趋势的思考。希望这些内容能够对同行开发者有所帮助。
        </p>
      </div>
      
      <div class="articles-section">
        <h2 class="section-title">最新文章</h2>
        <div class="articles-grid">
          <article class="article-card" v-for="article in articles" :key="article.id">
            <div class="article-image">
              <div class="article-category">{{ article.category }}</div>
            </div>
            <div class="article-content">
              <h3 class="article-title">{{ article.title }}</h3>
              <p class="article-excerpt">{{ article.excerpt }}</p>
              <div class="article-meta">
                <span class="article-date">{{ article.date }}</span>
                <span class="article-read-time">{{ article.readTime }}</span>
              </div>
              <div class="article-tags">
                <span class="tag" v-for="tag in article.tags" :key="tag">{{ tag }}</span>
              </div>
            </div>
          </article>
        </div>
      </div>
      
      <div class="categories-section">
        <h2 class="section-title">文章分类</h2>
        <div class="categories-grid">
          <div class="category-card" v-for="category in categories" :key="category.name">
            <div class="category-icon">{{ category.icon }}</div>
            <h3 class="category-name">{{ category.name }}</h3>
            <p class="category-count">{{ category.count }} 篇文章</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Blog',
  data() {
    return {
      articles: [
        {
          id: 1,
          title: 'Vue 3 Composition API 深度解析',
          excerpt: '深入探讨Vue 3 Composition API的设计理念、使用方法和最佳实践，帮助开发者更好地理解和应用这一新特性。',
          category: '前端技术',
          date: '2024-01-15',
          readTime: '8分钟阅读',
          tags: ['Vue.js', 'JavaScript', '前端框架']
        },
        {
          id: 2,
          title: '现代CSS布局技术总结',
          excerpt: '从Flexbox到Grid，从传统布局到现代布局方案，全面总结CSS布局技术的发展和应用场景。',
          category: '前端技术',
          date: '2024-01-08',
          readTime: '12分钟阅读',
          tags: ['CSS', '布局', '响应式设计']
        },
        {
          id: 3,
          title: 'JavaScript性能优化实战',
          excerpt: '分享在实际项目中遇到的性能问题及解决方案，包括代码优化、内存管理和渲染优化等方面。',
          category: '性能优化',
          date: '2024-01-01',
          readTime: '15分钟阅读',
          tags: ['JavaScript', '性能优化', '最佳实践']
        },
        {
          id: 4,
          title: '前端工程化实践分享',
          excerpt: '从项目搭建到部署上线，分享前端工程化的完整流程和工具选择，提升开发效率和代码质量。',
          category: '工程化',
          date: '2023-12-25',
          readTime: '10分钟阅读',
          tags: ['工程化', 'Webpack', 'Vite']
        }
      ],
      categories: [
        {
          name: '前端技术',
          icon: '💻',
          count: 15
        },
        {
          name: '性能优化',
          icon: '⚡',
          count: 8
        },
        {
          name: '工程化',
          icon: '🔧',
          count: 6
        },
        {
          name: '生活感悟',
          icon: '📝',
          count: 4
        }
      ]
    }
  }
}
</script>

<style scoped>
.blog-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}

.blog-header {
  text-align: center;
  margin-bottom: 3rem;
  padding: 3rem 0;
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  border-radius: 15px;
}

.blog-title {
  font-size: 3rem;
  color: #2c3e50;
  margin-bottom: 1rem;
  font-weight: bold;
}

.blog-subtitle {
  font-size: 1.3rem;
  color: #7f8c8d;
  font-weight: 300;
}

.blog-content {
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

.section-title {
  font-size: 2rem;
  color: #2c3e50;
  margin-bottom: 1.5rem;
  border-bottom: 3px solid #667eea;
  padding-bottom: 0.5rem;
  display: inline-block;
}

.intro-text {
  font-size: 1.1rem;
  line-height: 1.8;
  color: #555;
  text-align: justify;
}

.articles-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.article-card {
  background: white;
  border-radius: 15px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
}

.article-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
}

.article-image {
  height: 120px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
}

.article-category {
  background: rgba(255, 255, 255, 0.9);
  color: #667eea;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-weight: 600;
  font-size: 0.9rem;
}

.article-content {
  padding: 1.5rem;
}

.article-title {
  font-size: 1.3rem;
  color: #2c3e50;
  margin-bottom: 0.8rem;
  font-weight: 600;
  line-height: 1.4;
}

.article-excerpt {
  color: #666;
  line-height: 1.6;
  margin-bottom: 1rem;
  font-size: 0.95rem;
}

.article-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
  font-size: 0.85rem;
  color: #888;
}

.article-date {
  background: rgba(102, 126, 234, 0.1);
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  color: #667eea;
}

.article-read-time {
  font-weight: 500;
}

.article-tags {
  display: flex;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.tag {
  background: #f8f9fa;
  color: #495057;
  padding: 0.3rem 0.6rem;
  border-radius: 12px;
  font-size: 0.8rem;
  font-weight: 500;
}

.categories-section {
  margin-top: 2rem;
}

.categories-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
}

.category-card {
  background: white;
  padding: 2rem;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  cursor: pointer;
}

.category-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
}

.category-icon {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.category-name {
  font-size: 1.2rem;
  color: #2c3e50;
  margin-bottom: 0.5rem;
  font-weight: 600;
}

.category-count {
  color: #7f8c8d;
  font-size: 0.9rem;
}

@media (max-width: 768px) {
  .blog-container {
    padding: 1rem;
  }
  
  .blog-title {
    font-size: 2.5rem;
  }
  
  .articles-grid {
    grid-template-columns: 1fr;
  }
  
  .categories-grid {
    grid-template-columns: repeat(2, 1fr);
  }
  
  .article-meta {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }
}

@media (max-width: 480px) {
  .categories-grid {
    grid-template-columns: 1fr;
  }
}
</style>