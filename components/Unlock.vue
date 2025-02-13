<template>
    <div class="unlock">
        <div class="unlock-frame">
            <img src="~/assets/images/Unlock.svg" alt="Unlock Frame">
        </div>
        <div class="unlock-content">
            <div class="unlock-text">
                <h2 class="h2"> The unseen of spending three years at Pixelgrade </h2>
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sit amet justo ipsum. Sed accumsan
                    quam
                    vitae est varius fringilla. Pellentesque placerat vestibulum lorem sed porta. Nullam mattis
                    tristique iaculis. Nullam pulvinar sit amet risus pretium auctor. Etiam quis massa pulvinar,
                    aliquam
                    quam vitae, tempus sem. Donec elementum pulvinar odio.
                </p>
            </div>
            <div class="unlock-btn">
                <button> Learn More </button>
            </div>
        </div>
    </div>
</template>

<style>
.unlock {
    display: flex;
    justify-content: center;
    align-items: center; /* Centers the content vertically */
    width: 100vw;
    box-sizing: border-box;
}

.unlock-frame {
    width: 100%;
    height: 100%;
    padding: 0 144px;
    padding-right: 0;
    margin-right: 49px;
}

.unlock-frame img {
    width: 100%;
    height: auto;
}

.unlock-content {
    display: flex;
    flex-direction: column;
    padding: 0 144px;
    padding-left: 0;
}

.unlock-text {
    padding-right: 60px;
}

.unlock-text p {
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0%;
}

.unlock-btn {
    margin-top: 32px;
}

.unlock-btn button {
    padding: 14px 32px;
    background-color: var(--Primary);
    width: 151px;
    height: 52px;
    gap: 10px;
    padding: 14px 32px;
    color: var(--White);
    border-radius: 4px;

    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0%;
    text-align: center;
}
</style>