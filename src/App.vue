<template>
    <main>
        <div class="container">
            <header>
                <h1>Memo</h1>
                <button class="icon-btn add-btn">
                    <div class="add-icon"></div>
                    <div class="btn-text">Add Note</div>
                </button>
            </header>
            <div class="card-container">
                <div class="card">
                    <p class="card-content">Lorem ipsum dolor, sit amet consectetur adipisicing elit. At nulla molestias quasi dicta et expedita, voluptas perspiciatis. Nam, autem quasi!</p>
                    <p class="card-date">12/12/26</p>
                </div>
                <div class="card">
                    <p class="card-content">Lorem ipsum dolor, sit amet consectetur adipisicing elit. At nulla molestias quasi dicta et expedita, voluptas perspiciatis. Nam, autem quasi!</p>
                    <p class="card-date">12/12/26</p>
                </div>
                <div class="card">
                    <p class="card-content">Lorem ipsum dolor, sit amet consectetur adipisicing elit. At nulla molestias quasi dicta et expedita, voluptas perspiciatis. Nam, autem quasi!</p>
                    <p class="card-date">12/12/26</p>
                </div>
                <div class="card">
                    <p class="card-content">Lorem ipsum dolor, sit amet consectetur adipisicing elit. At nulla molestias quasi dicta et expedita, voluptas perspiciatis. Nam, autem quasi!</p>
                    <p class="card-date">12/12/26</p>
                </div>
                <div class="card">
                    <p class="card-content">Lorem ipsum dolor, sit amet consectetur adipisicing elit. At nulla molestias quasi dicta et expedita, voluptas perspiciatis. Nam, autem quasi!</p>
                    <p class="card-date">12/12/26</p>
                </div>
                <div class="card">
                    <p class="card-content">Lorem ipsum dolor, sit amet consectetur adipisicing elit. At nulla molestias quasi dicta et expedita, voluptas perspiciatis. Nam, autem quasi!</p>
                    <p class="card-date">12/12/26</p>
                </div>
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
</style>