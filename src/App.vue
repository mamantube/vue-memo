<script setup>

import { ref } from 'vue';

const showForm = ref(false);
const newMemo = ref("");
const memos = ref ([]);


function addMemo() {
    memos.value.push({
        id: Date.now(),
        content: newMemo.value,
        date: new Date().toLocaleDateString("en-GB"),
        backgroundColor: `#${Math.floor(Math.random() * 16777215).toString(16)}`
    })

    newMemo.value = "";
    showForm.value = false;
}

</script>

<template>
    <main>
        <div class="container">
            <header>
                <h1>Memo</h1>
                <button @click="showForm = true" class="icon-btn add-btn">
                    <div class="add-icon"></div>
                    <div class="btn-text">Add Note</div>
                </button>
            </header>
            <div class="card-container">
                <div v-for="(memo, index) in memos" :key="index" class="card" :style="{backgroundColor: memo.backgroundColor}">
                    <p class="card-content">
                        {{ memo.content }}
                    </p>
                    <p class="card-date">
                        {{ memo.date }}
                    </p>
                </div>
            </div>
        </div>
        <div v-if="showForm" class="form-overlay">
            <div class="form-modal">
                <button @click="showForm = false" class="close-btn">
                    &times;
                </button>
                <textarea v-model="newMemo" name="memo" id="memo" cols="30" rows="10"></textarea>
                <button @click="addMemo" class="save-btn">Save</button>
            </div>
        </div>
    </main>
</template>

<style scoped>
main {
    height: 100vh;
    width: 100vw;
}

.container {
    max-width: 900px;
    padding: 10px;
    margin: 0 auto;
}

header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.icon-btn {
    width: 50px;
    height: 50px;
    border: 1px solid #cdcdcd;
    background: white;
    border-radius: 25px;
    overflow: hidden;
    position: relative;
    transition: width 0.2s ease-in-out;
    font-weight: 500;
    font-family: inherit;
}

.add-btn:hover {
    width: 120px;
}

.add-btn::before, .add-btn::after {
    transition: width 0.2s ease-in-out, border-radius 0.2s ease-in-out;
    content: "";
    position: absolute;
    height: 4px;
    width: 10px;
    top: calc(50% - 2px);
    background: seagreen;
}

.add-btn::after {
    right: 14px;
    overflow: hidden;
    border-top-right-radius: 2px;
    border-bottom-right-radius: 2px;
}

.add-btn::before {
    left: 14px;
    border-top-left-radius: 2px;
    border-bottom-left-radius: 2px;
}

.icon-btn:focus {
    outline: none;
}

.btn-text {
    opacity: 0;
    transition: opacity 0.2s;
}

.add-btn:hover::before, .add-btn:hover::after {
    width: 4px;
    border-radius: 2px;
}

.add-btn:hover .btn-text {
    opacity: 1;
}

.add-icon::after, .add-icon::before {
    transition: all 0.2s ease-in-out;
    content: "";
    position: absolute;
    height: 20px;
    width: 2px;
    top: calc(50% - 10px);
    background: seagreen;
    overflow: hidden;
}

.add-icon::before {
    left: 22px;
    border-top-left-radius: 2px;
    border-bottom-left-radius: 2px;
}

.add-icon::after {
    right: 22px;
    border-top-right-radius: 2px;
    border-bottom-right-radius: 2px;
}

.add-btn:hover .add-icon::before {
    left: 15px;
    height: 4px;
    top: calc(50% - 2px);
}

.add-btn:hover .add-icon::after {
    right: 15px;
    height: 4px;
    top: calc(50% - 2px);
}

.card {
    width: 225px;
    height: 225px;
    padding: 10px;
    background-color: #ffa61f;
    margin-bottom: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.card-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.form-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.77);
    z-index: 10;
    display: flex;
    align-items: center;
    justify-content: center;
}

.form-modal {
    width: 420px;
    background-color: white;
    border-radius: 10px;
    padding: 30px;
    position: relative;
    display: flex;
    flex-direction: column;
}

.save-btn {
    padding: 10px 20px;
    font-size: 20px;
    width: 100%;
    background-color: #495a7d;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    margin-top: 15px;
    color: white;
}

.close-btn {
    position: absolute;
    top: 5px;
    right: 10px;
    width: 30px;
    height: 30px;
    background-color: transparent;
    border: none;
    font-size: 25px;
    cursor: pointer;
}
</style>