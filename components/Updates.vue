<template>
    <div class="updates">
        <div class="community-text">
            <h2 class="h2"> Caring is the new marketing </h2>
            <p>
                The Nexcent blog is the best place to read about the latest membership insights, trends and more. See
                who's joining the community, read about how our community are increasing their membership income and
                lot's more.
            </p>
        </div>
        <div class="community-cards">
            <div class="community-card" v-for="(item, index) in items" :key="index">
                <h4 class="h4"> {{ item.title }} </h4>
                <button class="btn-Tertiary"> Readmore -> </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            items: [
                {
                    title: 'Creating Streamlined Safeguarding Processes with OneRen'
                },
                {
                    title: 'What are your safeguarding responsibilities and how can you manage them?'
                },
                {
                    title: 'Revamping the Membership Model with Triathlon Australia'
                }
            ]
        }
    },
}
</script>

<style>
.updates {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 48px;
    width: 100dvw;
    gap: 16px;
}

.community-text {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 0 165px 0 165px;
    gap: 8px;
}

.community-text p {
    font-weight: 400;
    font-size: 16px;
    line-height: 24px;
    letter-spacing: 0%;
    text-align: center;
    color: var(--Grey);

    margin: 0 241px 0 241px;
}

.community-cards {
    display: flex;
    justify-content: center;
    margin: 19.5px 144px 19.5px 144px;
    gap: 100.5px;
}

.community-card {
    flex: 1;
    background-color: var(--Silver);
    box-shadow: 0px 8px 16px 0px rgba(171, 190, 209, 0.4);
    border-radius: 8px;
    padding: 16px;
    gap: 16px;

    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    text-align: center;
}
</style>