<template>
    <div class="modal-wrapper">
        <div class="header-modal">
            <button 
                class="close"
                @click='Close'
            >X</button>
        </div>    
        <div class="content-modal">
            <div class="form">
                <form action="#" @submit.prevent="GetData">
                    <label for="">Описание</label>
                    <input type="text" v-model="description">
                    <label for="">Приоритет</label>
                    <select name="" id="" v-model="priority">
                        <option selected value="1">1</option>
                        <option value="2">2</option>
                        <option value="3">3</option>
                    </select>
                    <button>Сохранить</button>
                </form>
            </div>
        </div>
    </div>
</template>
<script>

export default {
    name: 'Modal',
    data() {
        return {
            description: '',
            priority: ''
        }
    },
    methods: {
        Close(){
            this.$emit('Close')
        },
        GetData(){
            let data = [this.description, this.priority]
            if (this.description != '' && this.priority != ''){
                this.$emit('GetData', data)
                this.description = ''
                this.priority = ''
            }
        }
    },

}

</script>

<style scoped>
    .close{
        width: 35px;
        height: 35px;
        font-size: 20px;
        border: 2px solid #3f3f3f;
        background: #9e9e9e;
        color: #3f3f3f;
        font-weight: bold;
        border-radius: 100%;
    }

    .close:hover{
        transition: .5s;
        background: #5e5e5e;
    }
    
    .modal-wrapper{
        width: 300px;
        height: 300px;
        background: #fff;
        border: 2px solid #3f3f3f;
        border-radius: 10px;
        padding: 15px;
    }

    .header-modal{
        display: flex;
        justify-content: flex-end;
    }

    .form form{
        color: #3f3f3f;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    label{
        margin-top: 10px;
    }
    input, select{
        margin-top: 10px;
        padding: 10px;
        width: 240px;
        outline: none;
        background: #ffffff;
        font-size: 20px;
        color: #000000;
        border-radius: 10px;
        border: 2px solid #3f3f3f;
    }

    select{
        width: 265px;
    }

    button{
        margin-top: 20px;
        padding: 5px;
        border: none;
        background: #3f3f3f;
        color: #fff;
    }

</style>