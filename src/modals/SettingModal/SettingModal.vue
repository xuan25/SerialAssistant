<script setup>
import { useSettingStore } from "@/store/useSettingStore";
import { useDataCode } from "@/utils/useDataCode/useDataCode";
const { dataCode } = useDataCode();
const { lineEnding, sendHexInputMode } = useSettingStore();
</script>
<template>
  <input type="checkbox" id="setting-modal" class="modal-toggle" />
  <label for="setting-modal" class="modal cursor-pointer">
    <label class="modal-box relative" for="">
      <h3 class="text-lg font-bold mb-8">波特律动串口助手 设置</h3>
      <div class="flex items-center gap-x-5">
        <span class="text-white w-60">行尾自动添加:</span>
        <select
          v-model="lineEnding"
          class="select select-bordered w-full max-w-xs"
        >
          <option value="">无</option>
          <option :value="'\n'">LF</option>
          <option :value="'\r'">CR</option>
          <option :value="'\r\n'">CRLF</option>
        </select>
      </div>
      <div class="h-3"></div>
      <div class="flex items-center gap-x-5">
        <span class="text-white w-60">中文编码:</span>
        <select
          v-model="dataCode"
          class="select select-bordered w-full max-w-xs"
        >
          <option :value="'UTF-8'">UTF-8</option>
          <option :value="'GBK'">GBK</option>
        </select>
      </div>
      <div class="h-3"></div>
      <!-- <div class="flex items-center gap-x-5">
        <span class="text-white w-60">Hex输入模式:</span>
        <select
          v-model="sendHexInputMode"
          class="select select-bordered w-full max-w-xs"
        >
          <option :value="'normal'">普通输入</option>
          <option :value="'format'">格式化输入</option>
        </select>
      </div> -->
    </label>
  </label>
</template>
