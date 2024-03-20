<template>
    <div class="common-layout">
      <el-container>
        <el-header>
          <div class="navbar">
            <el-link :underline="false">Logo</el-link>
            <el-button round @click="toggleDark()">
              <span class="ml-1">{{ isDark ? 'Dark' : 'Light' }}</span>
            </el-button>
          </div>
        </el-header>
        <el-main>
          <div class="main">
          </div>
        </el-main>
        <el-footer>
          <el-link :underline="false"><el-text class="mx-1" size="small">payamd.com © 2023 </el-text></el-link>
        </el-footer>
      </el-container>
    </div>
  </template>

<script setup>
import { useDark, useToggle } from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)

</script>  

<style>
.navbar{
  height: 5vh;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;

}
.main {
  min-height: 77vh;
  border: 1px solid var(--el-border-color);;
  border-radius: 4px;
}
.footer{
  height: 3vh;
  display: flex;
  justify-content: center;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
}
</style>