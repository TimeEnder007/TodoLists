<template>
    <div class="todo-container">
        <h1>ToDo List</h1>
        <input v-model="newTask" @keyup.enter="addTask" placeholder="Enter a task" />
        <button class="button" @click="addTask">Add</button>
        <ul>
            <li v-for="(task, index) in tasks" :key="index">
                {{ task }}


                <button class="btn2" @click="removeTask(index)"> <div class="12" style="width: 15px; height: 15px;"> <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor" class="size-4">
                    <path fill-rule="evenodd" d="M5 3.25V4H2.75a.75.75 0 0 0 0 1.5h.3l.815 8.15A1.5 1.5 0 0 0 5.357 15h5.285a1.5 1.5 0 0 0 1.493-1.35l.815-8.15h.3a.75.75 0 0 0 0-1.5H11v-.75A2.25 2.25 0 0 0 8.75 1h-1.5A2.25 2.25 0 0 0 5 3.25Zm2.25-.75a.75.75 0 0 0-.75.75V4h3v-.75a.75.75 0 0 0-.75-.75h-1.5ZM6.05 6a.75.75 0 0 1 .787.713l.275 5.5a.75.75 0 0 1-1.498.075l-.275-5.5A.75.75 0 0 1 6.05 6Zm3.9 0a.75.75 0 0 1 .712.787l-.275 5.5a.75.75 0 0 1-1.498-.075l.275-5.5a.75.75 0 0 1 .786-.711Z" clip-rule="evenodd" />
                </svg>
                </div>
        </button>


            </li>
        </ul>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTask: '',
            tasks: []
        };
    },
    methods: {
        addTask() {
            if (this.newTask.trim() !== '') {
                this.tasks.unshift(this.newTask);
                this.newTask = '';
            }
        },
        removeTask(index) {
            this.tasks.splice(index, 1);
        }
    }
};
</script>

<style scoped>

.todo-container {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
    background-color: #f9f9f9;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
input {
    width: calc(100% - 100px);
    padding: 10px;
    margin-right: 10px;
    border: 3px solid #ccc;
    border-radius: 4px;
    font-size: 15px;
    font-weight: normal;
}
input:focus {
    border-color: #007bff;
    outline: none; /* Убирает стандартное выделение */
}
.button {
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    background-color: #007bff;
    color: #fff;
    cursor: pointer;
}
.btn2{
    padding: 10px;
    border:none;
    border-radius: 4px;
    background-color: #009bff;
    color: #fff;
    cursor:pointer;
}
button:hover {
    background-color: #0056b3;
}
ul {
    list-style-type: none;
    padding: 0;
}
li {
    padding: 10px;
    background-color: white;
    margin-bottom: 5px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-radius: 4px;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
    font-size: 20px;
}
</style>
