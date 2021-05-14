<template>
    <div class="container">
        <LargeCardDisplay
            v-for="cardInfo in largeCardInfo"
            :key="cardInfo.id"
            :cardsSection="cardInfo"
        />
        <SmallCardDisplay 
            v-for="cardI in smallCardSections"
            :key="cardI.id"
            :cardsSection="cardI"
        /> 
    </div>
</template>

<script>
import { largeCardSections, smallCardSections } from "@/assets/data.js"
    export default {
        data(){
            return {
                largeCardInfo: largeCardSections,
                smallCardSections: smallCardSections
            }
        }
    }
</script>

<style scoped>

</style>