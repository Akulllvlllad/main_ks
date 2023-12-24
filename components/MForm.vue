<template>
    <Form class="form" @submit="onSubmit">
        <CellGroup>

            <Field v-model="fullname"  placeholder="Как к вам обращаться?" />
            <Field v-model="tel"  placeholder="Ваш номер телефона?"  />
            
            <Field v-model="message"
                type="textarea"
                placeholder="Сообщение"
                rows="3"
                autosize
            />
        </CellGroup>


       


        <div style="margin: 16px;">
            <Button round block type="primary" native-type="submit">
                Отправить
            </Button>
        </div>
    </Form>

</template>

<script>
import { Form, Field, CellGroup, Button, showDialog } from 'vant';



export default {
    data(){
        return {
            fullname: '',
            tel: '',
            message: '',
            
   
        }
    },

    components: {
        Button,
        Form,
        Field,
        CellGroup,

    },
    methods: {

        

     
        
        onSubmit(e){
            const { fullname, tel, message, date } = this

            showDialog({ message: 'Alert' });

            console.log({fullname, tel, message, date })
        }
    }
}


</script>
<style scoped>

</style>