<template>
    <div class="converter">

        <h2>{{ curA }} to {{ curB }}</h2>
        <input type="text" v-model="curA_value" v-bind:placeholder="curA">
        <input type="button" value="Convert" v-on:click="convert()">
        <h2>{{ curB_value }}</h2>
    </div>
</template>

<script>
export default {
    name: "Converter",
    props: ["curA", "curB"],
    data(){
        return{
            curA_value: "",
            curB_value: 0
        };
    },
    methods:{

        convert(){
            let from_to = this.curA + "_" + this.curB;
            let url ="https://free.currconv.com/api/v7/convert?q="+from_to+"&compact=ultra&apiKey=051747b3ecbbbb065497";


            fetch(url)
            .then(res => {
                return res.json()
                })
                .then(json => {
                     let cotation = json[from_to]
                     this.curB_value = (cotation * parseFloat(this.curA_value)).toFixed(2)
                     })
        }
    }
}
</script>

<style scoped>
.converter{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
}
</style>