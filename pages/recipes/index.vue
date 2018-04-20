<template>
    <section class="recipes">
            <Recipe
                id = "1"
                title = "judul enak"
                thumbnail = "https://images.summitmedia-digital.com/yummyph/images/2016/08/05/salted-eggs-main2.jpg"
                previewText = "desc enak"
            />

            <Recipe
                id = "2"
                title = "judul enak"
                thumbnail = "https://images.summitmedia-digital.com/yummyph/images/2016/08/05/salted-eggs-main2.jpg"
                previewText = "desc enak"
            />

            <Recipe
                id = "3"
                title = "judul enak"
                thumbnail = "https://images.summitmedia-digital.com/yummyph/images/2016/08/05/salted-eggs-main2.jpg"
                previewText = "desc enak"
            />
    </section>
</template>

<script>
import Recipe from '@/components/Recipe'
export default {
    components : {
        Recipe
    },
    asyncData() {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        { 
                            id : "1",
                            title : "Gudeg Batas kota",
                            previewText : "Gudeg enak jogja",
                            thumbnail : "https://media.travelingyuk.com/wp-content/uploads/2017/01/Gudeg-Batas-Kota.jpg"
                        },
                        {
                            id : "2",
                            title : "Gudeg Yu jum",
                            previewText : "Gudeg enak jogja",
                            thumbnail : "https://www.beritainfo.web.id/wp-content/uploads/2015/10/gudeg-jogja.jpg"
                        }
                    ]
                })
            }, 1500)
        })
    }
}
</script>

<style scoped>
    .recipes {
        display: flex;
        flex-flow: row wrap;
        justify-content: center;
        align-items: center;
    }
</style>