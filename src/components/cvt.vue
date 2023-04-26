<template>
    <div class="conversor">
        <h2>{{ moedaA }} para {{ moedaB }}</h2>
        <input type="text" v-model="moedaA_v" v-bind:placeholder="moedaA">
        <button v-on:click="converter" >Converter agora</button>
        <h3>{{ moedaB_v }}</h3>
    </div>
</template>

<script>
    export default{
        name: "conVs",
        props: ["moedaA","moedaB"],
            data(){
                return{
                    moedaA_v : "",
                    moedaB_v : 0
                };
            },
            methods:{
                converter(){
                    let depara = this.moedaA + "_" + this.moedaB;
                    let url = "https://api.currencyapi.com/v3/latest?apikey=n6q74GqxtPrbPIeX6H7dcfob4mw0BRvJcjcydwvG&currencies=BRL";
                fetch(url).then(res=>{return res.json();})
                          .then(json=>{
                                let cotacao = json[depara]
                                this.moedaB_v = (cotacao * parseFloat(this.moedaA_v)).toFixed(2);
                          })
                          
                }
            }
    };
</script>

<style scoped>
    .conversor{
        padding: 50px;
        max-width: 300px;
        box-shadow: 5px 5px 5px grey;
        margin: 25px;
        background-color: lightblue;
        display: flex;
        align-items: center;
        flex-direction: column;
        border-radius: 20px;
        animation: ani 1s;
    }
    button{
        border-radius: 5px;
        color: aliceblue;
        background-color: blue;
        width: 50%;
        height: 50px;
        margin: 20px;
        font-weight: bold;
        border: black 3px solid;
        font-size: 15px;
    }
    input{
        border-radius: 5px;
        color: rgb(0, 0, 0);
        background-color: rgb(255, 255, 255);
        width: 150px;
        height: 50px;
        font-weight: bold;
        border: black 3px solid;
        text-align: center;
        font-size: 40px;
    }
    button:hover{
        background-color: white;
        color: blue;
        transition: 0.5s;
        cursor: pointer;
    }
    h3{
        font-size: 40px;
    }
    @keyframes ani {
    from{
        filter: blur(5px);
    transform: translateY(100%);
    }
    to{
        transform: translateY(0%);
    }
}
</style>