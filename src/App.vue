<script setup>
import { ref } from 'vue';
import BreakingBadCards from './components/BreakingBadCardsSuspense.vue';
import RickMortyCards from './components/RickMortyCards.vue';
import Hero from './components/Hero.vue';

const isBreakingBad = ref(false);
</script>

<template>
    <main>
        <Hero
            :isBreakingBad="isBreakingBad"
            @selectShow="isBreakingBad = !isBreakingBad"
        />

        <KeepAlive>
            <Component
                :is="isBreakingBad ? BreakingBadCards : RickMortyCards"
            />
        </KeepAlive>
    </main>
</template>
