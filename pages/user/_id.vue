<template>
    <div>
        <h1>{{post.FirstName+post.LastName+post.userId}}</h1>
    </div>
</template>

<script>
export default {
    data(){
        console.log('test:'+this.$route.params.id)
        var idVue=this.$route.params.id
        
        return{
            id:this.$route.params.id,
            user:[
                {
                    id:idVue,
                    FirstName:idVue.split('-',3)[0],
                    LastName:idVue.split('-',3)[1],
                    userId:idVue.split('-',3)[2],
                    result:idVue.split('-',3)
                },
                // {
                //     id:'Ben-Zhang-2',
                //     FirstName:'Ben',
                //     LastName:'Zhang',
                //     userId:2
                // },
                // {
                //     id:'Da-Liu',
                //     FirstName:'Da',
                //     LastName:'Liu',
                //     userId:3
                // }

            ]
            
        }
    },
    computed:{
        post(){
            return this.user.find(post=>post.id===this.id)
        }
    }


}
</script>
