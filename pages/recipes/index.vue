<template>
    <section class="recipes">
        <Recipe
        v-for="recipe in recipes"
        :key="recipe.id"
        :thumbnail="recipe.thumbnail"
        :title="recipe.title" 
        :id="recipe.id"
        :previewText="recipe.previewText"/>
        <Recipe
        thumbnail="https://images.unsplash.com/photo-1625805866852-b2ab3e740530?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80"
        title="Sea Food Pizza Saled"
        id="4" 
        previewText="Very tasty indeed ! "/>
        <!-- <article class="recipe">
            <div class="thumbnail" style="background-image: url('https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Good_Food_Display_-_NCI_Visuals_Online.jpg/800px-Good_Food_Display_-_NCI_Visuals_Online.jpg')"></div>
            <h1>Title</h1>
            <p>Some nice preview text</p>
        </article>
        <article class="recipe">
            <div class="thumbnail" style="background-image: url('https://food.fnr.sndimg.com/content/dam/images/food/fullset/2004/5/14/0/bw2c12_chicken_broccoli2.jpg.rend.hgtvcom.826.620.suffix/1371584021202.jpeg')"></div>
            <h1>Title</h1>
            <p>Some nice preview text</p>
        </article> -->
    </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
    components: {
        Recipe
    },
    asyncData()  {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id: "1",
                            title: "Delicious Pizza",
                            previewText: "Awesome Pizza!",
                            thumbnail: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Good_Food_Display_-_NCI_Visuals_Online.jpg/800px-Good_Food_Display_-_NCI_Visuals_Online.jpg"
                        },
                        {
                            id: "2",
                            title: "Sea Food Saled!",
                            previewText: "Very tasty indeed",
                            thumbnail: "https://food.fnr.sndimg.com/content/dam/images/food/fullset/2004/5/14/0/bw2c12_chicken_broccoli2.jpg.rend.hgtvcom.826.620.suffix/1371584021202.jpeg"
                        },
                        {
                            id: "3",
                            title: "Sea Food Saled!",
                            previewText: "Very tasty indeed",
                            thumbnail: "https://images.unsplash.com/photo-1625805866852-b2ab3e740530?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80"
                        },
                    ]
                })
            },1500)
        })
    },
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