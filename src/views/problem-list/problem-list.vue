// file created at 2019-9-24
// Auto-generated files problem-list.vue

<template>
  <div>
    <div class="problemlist-content-area content-zone content-zone-padding">
      <div class="problemlist-descriptor">전체 문제
        <div style="flex: 1;"></div>
        <!-- <a-select size="small" defaultValue="25" style="font-size: 12px">
          <a-select-option value="25">25개씩 보기</a-select-option>
          <a-select-option value="50">50개씩 보기</a-select-option>
          <a-select-option value="75">75개씩 보기</a-select-option>
          <a-select-option value="100">100개씩 보기</a-select-option>
        </a-select> -->
      </div>

      <div class="table-area">
        <div class="table-item header">
          <div class="start-item">번호</div>
          <div class="options-2">제목</div>
          <div class="options-1">카테고리</div>
          <div class="options-1">만든이</div>
          <div class="options-1">생성 시간</div>
          <div class="options-1">제출 횟수</div>
          <div class="end-item">풀이 결과</div>
        </div>
        <div class="table-item items"
            v-for="(problem, i) in api.problems" :key="'problem' + i"
            @click="clickItem(problem.pid)">
          <div class="start-item">{{problem.pid}}</div>
          <div class="options-2 problem-title" style="padding-left: 4px;">{{problem.title}}</div>
          <div class="options-1" style="padding-left: 4px;">{{problem.category}}</div>
          <div class="options-1" style="padding-left: 4px;">{{problem.creator}}</div>
          <div class="options-1" style="padding-left: 4px;">{{new Date(problem.createdAt).getFullYear() + '/' + (new Date(problem.createdAt).getMonth() + 1) + '/' + new Date(problem.createdAt).getDate() }}</div>
          <div class="options-1" style="padding-left: 4px;">{{getSubmitCount(problem.pid)}}</div>
          <div v-if="getSubmitCount(problem.pid) === 0" class="end-item"  style="padding-left: 4px;">-</div>
          <div v-else-if="getResult(problem.pid)" class="end-item"  style="padding-left: 4px; color: rgb(65, 165, 211);">맞았습니다</div>
          <div v-else class="end-item"  style="padding-left: 4px; color: #ff3232;">틀렸습니다</div>
        </div>
      </div>
    </div>
  </div>
</template>
<script src='./problem-list.ts'>

</script>
<style lang='scss' scoped>
@import "../../style/_common.scss";
@import "./problem-list.scss";
</style>
