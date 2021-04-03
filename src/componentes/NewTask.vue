<template>
    <div class="newTask">
			<input type="text" v-model="name" @keydown.enter="addTask" placeholder="Nova tarefa?" class="form-element">
			<button class="form-element" @click="addTask"> + </button>
	</div>
</template>

<script>
export default {
    data() {
        return {
            name: ''
        }
    },
    methods: {
        addTask() {
            this.$emit('taskAdded', { name: this.name })
            this.name = ''
        }
    }
}
</script>

<style>
    .newTask input {
		width: 500px;
		height: 37px;
		background: #fff2;
		border-top-left-radius: 8px;
		border-bottom-left-radius: 8px;

	}

    .newTask button {
		border-left: none;
		outline: none;
		font-size: 2rem;
		border-top-right-radius: 8px;
		border-bottom-right-radius: 8px;
		background-color:#2196F3;
		color: #FFF;
		margin: 0px;
		margin-left: -3px;
		cursor: pointer;
	}

    .form-element {
		outline: none;
		font-size: 2rem;
		border: 1px solid #fff;
		padding: 5px 10px 8px;
		color: #fff;
	}

	.newTask {
		margin: 50px;
	}

	.form-element::placeholder {
		color:#757575;
		padding: 5px;
		font-size: 32px;
		
	}
</style>