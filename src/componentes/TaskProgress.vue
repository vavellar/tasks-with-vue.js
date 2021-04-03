<template>
  <div class="task-progress">
			<span class="progress-value">{{ progress }}%</span> 
			<div class="progress-bar" :style="{width: progress + '%'}"></div> 
		</div>
</template>

<script>
export default {
  props: {
    progress: { type: Number, default: 0}
  }
}
</script>

<style>
  .task-progress {
    position: relative;
    border: 1px solid #fff;
    width: 80%;
    border-radius: 8px;
    align-items: center;
    margin-bottom: 15px;
    color: #fff;
    display: flex;
    flex-direction: column;
  }

  .progress-value{
    padding:0px;
    margin: 0px;
    font-size: 24px;
	}

  .progress-bar{
    background-color: #4CAF50;
    position: absolute;
    border-radius: 8px;
    height: 100%;
    align-self: flex-start;
  }

  .progress-value {
    z-index: 1;
  }
</style>