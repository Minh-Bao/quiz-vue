<template>
    <div id="app" class="container">
        <h1 class="mb-4">Un quiz ?</h1>
        <b-alert v-if="fin" show> Votre score est : {{score}} / {{questions.length}}</b-alert>
        <b-card
            :header="questions[index].question"
            header-tag="header">
            <b-list-group>
                <b-list-group-item 
                button 
                v-for="(item, index) in questions[index].answers" 
                :key="item"
                @click="action(index)">
                    {{item}}
                </b-list-group-item>
            </b-list-group>
            <b-button v-if="fin" @click="recommencer" class="mt-4">Recommencer ! </b-button>
        </b-card>
    </div>
</template>

<script>
export default {
    name: "App",
    data: function () {
        return {
            fin: false,
            index: 0,
            score: 0,
            questions: [
                {
                    question:
                        "Quel révolutionnaire et grand orateur a déclaré en 1792 : “De l’audace, encore de l’audace, toujours de l’audace.”",
                    answers: [
                        "Desmoulin",
                        "Danton",
                        "Robespierre",
                        "Saint Just",
                    ],
                    ok: 1,
                },
                {
                    question:
                        "Dans quel pays peut-on trouver le mont Elbrouz ?",
                    answers: ["Russie", "Azerbaïdjan", "Géorgie", "Iran"],
                    ok: 0,
                },
                {
                    question: "Qui a dit “Ich bin ein Berliner” ?",
                    answers: ["Bismarck", "Reagan", "De Gaulle", "Kennedy"],
                    ok: 3,
                },
            ],
        };
    },
    methods: {
        action: function(index) {
            //test bonne réponse
            if(index == this.questions[this.index].ok) {
                this.score++;
            }
            //Test fin de quiz
            if(this.index == this.questions.length -1) {
                this.fin = true;
            }else{
                this.index++;
            }
        },
        recommencer: function() {
            this.fin = this.index = this.score = 0;
        }
    }
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
