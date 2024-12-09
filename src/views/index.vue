<template>
  <div class="app-container home">
    <el-row :gutter="20">
      <el-col :sm="24" :lg="24">
        <el-card>
          <template #header>
            <div class="card-header">
              <span>更新日志</span>
            </div>
          </template>
          <div class="update-log">
            <el-timeline>
              <el-timeline-item
                v-for="(activity, index) in updateLog"
                :key="index"
                :timestamp="activity.timestamp"
                :color="activity.color"
              >
                {{ activity.content }}
              </el-timeline-item>
            </el-timeline>
          </div>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script setup name="Index">
const updateLog = [
  { timestamp: '2024/3/1', content: '新版本发布', color: '#0bbd87' },
  { timestamp: '2024/2/1', content: '更新 XXX 功能', color: '#0bbd87' },
  { timestamp: '2024/1/1', content: '系统优化', color: '#0bbd87' }
  // 你可以根据需要添加更多日志
];
</script>

<style scoped lang="scss">
.home {
  .card-header {
    font-weight: bold;
    font-size: 16px;
  }
  .update-log {
    padding: 20px;
  }
}
</style>

