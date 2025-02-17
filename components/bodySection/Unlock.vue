<template>
    <section class="unlock">
        <div class="container">
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
    </section>
</template>

<style>
.unlock {
    width: 100%;
    overflow-x: hidden;
}

.unlock .container {
    display: flex;
    justify-content: center; /* horizontally */
    align-content: center; /* vertically */
    max-width: 1200px;
    margin: 0 auto;
    /* padding: 40px 20px; */
}

.unlock-frame {
    flex-shrink: 0;
    margin-right: 49px;
    display: flex;
    justify-content: flex-end;
}

.unlock-frame img {
    width: 442px;
    height: 433px;
    object-fit: contain;
    max-width: 100%;
}

.unlock-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    /* max-width: 500px; */
}

.unlock-text {
    padding-right: 60px;
}

.unlock-text h2 {
    margin-bottom: 20px;
}

.unlock-text p {
    font-weight: 400;
    font-size: 14px;
    line-height: 20px;
}

.unlock-btn {
    margin-top: 32px;
}

.unlock-btn button {
    background-color: var(--Primary);
    width: 151px;
    height: 52px;
    padding: 14px 32px;
    color: var(--White);
    border: none;
    border-radius: 4px;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    text-align: center;
    cursor: pointer;
}

@media (max-width: 1100px) {
    .unlock .container {
        flex-direction: column;
        align-items: center;
        /* padding: 30px 20px; */
    }
    
    .unlock-frame {
        margin-right: 0;
        margin-bottom: 30px;
        padding: 0;
        justify-content: center;
    }

    .unlock-content {
        padding: 0 20px;
        max-width: 100%;
        align-items: center;
        text-align: center;
    }

    .unlock-text {
        padding-right: 0;
    }
}

@media (max-width: 768px) {
    .unlock-frame img {
        width: 320px;
        height: 313px;
    }
}

@media (max-width: 480px) {
    .unlock-frame img {
        width: 280px;
        height: 274px;
    }

    .unlock-text h2 {
        font-size: 24px;
        line-height: 32px;
    }

    .unlock-btn button {
        width: 130px;
        height: 46px;
        padding: 12px 24px;
        font-size: 14px;
        line-height: 22px;
    }
}
</style>