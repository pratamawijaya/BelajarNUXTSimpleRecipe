<template>
    <section class="single-recipe">
        <h1>title</h1>
        <div>
            <img src="" alt="">
        </div>
        <p>desc</p>
    </section>
</template>

<script>
    export default{
        asyncData(context){
            return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipe : [
                        { 
                            id : "1",
                            description : "ini makanan enak lho",
                            title : "Gudeg Batas kota",
                            previewText : "Gudeg enak jogja",
                            thumbnail : "https://media.travelingyuk.com/wp-content/uploads/2017/01/Gudeg-Batas-Kota.jpg"
                        },
                        {
                            id : "2",
                            description : "ini makanan enak lho",
                            title : "Gudeg Yu jum",
                            previewText : "Gudeg enak jogja",
                            thumbnail : "https://www.beritainfo.web.id/wp-content/uploads/2015/10/gudeg-jogja.jpg"
                        }
                    ].find(el => el.id === context.params.id)
                })
            }, 1500)
        })
        }
    }
</script>

<style>
    .single-recipe {
        display: flex;
        flex-flow: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 30px;
    }
</style>