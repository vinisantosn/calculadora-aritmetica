<script setup>
const props = defineProps(['selecionaNumeroA','editaNumA', 'selecionaOperacao','selecionaNumeroB','editaNumB','resultado'])


</script>

<template>
    <section class="calc">
        <div class="row justify-content-between">
            <input :value="props.selecionaNumeroA" @change="props.editaNumA" class="col-md-2" type="number" name="" id="">
            <select @change="props.selecionaOperacao" class="col-md-2 ">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
            </select>
            <input :value="props.selecionaNumeroB" @change="props.editaNumB" class="col-md-2" type="number" name="" id="">
        </div>
        <h3 class="mt-5">Resultado</h3>
        <div class="result">
             
            <h4>{{ props.resultado }}</h4>
        </div>
    </section>


</template>

<style scoped></style>
