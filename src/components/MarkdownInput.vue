<template>
    <div>
        <div class="bar">
            <button>
                B
            </button>

            <button>
                I
            </button>

            <button>
                S
            </button>
        </div>
        <textarea v-model="markdown" @keyup="update" name="input" id="" cols="30" rows="10"></textarea>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                markdown: ''
            }
        },
        methods: {
            update(){
                this.$emit('update', this.markdown)
            }
        }
    }
</script>

<style lang="css" scoped>
textarea {
    resize: none ;
    height: 70vh;
    width: 40vw;
    background-color: white;
    border-radius: 5px;
    padding: 20px;
    outline: none;
    border-left-color: transparent;
    border-top-color: transparent;
    border-bottom-color: transparent;
    border: 2px solid #4893bd;
    -webkit-box-shadow: 5px 5px 15px 5px rgba(72,149,189,0.52);
    box-shadow: 5px 5px 15px 5px rgba(72,149,189,0.52);
}
</style>