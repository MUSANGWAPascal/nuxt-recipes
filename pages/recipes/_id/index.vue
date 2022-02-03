<template>
    <!-- <p> {{ $route.params.id }} </p> -->
    <section class="single-recipe">
        <h1> {{ recipe.title }}</h1>
        <div>
            <img class="recipe-image" :src="recipe.thumbnail" :alt="Recipe">
        </div>
        <p>{{ recipe.descriptionText }}</p>
    </section>
</template>

<script>
export default {
    asyncData(context)  {
        return new Promise((resolve, reject) => {
            setTimeout(() => {
                resolve({
                    recipe: [
                        {
                            id: "1",
                            title: "Delicious Pizza",
                            previewText: "Awesome Pizza!",
                            descriptionText: "Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of de Finibus Bonorum et Malorum (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, Lorem ipsum dolor sit amet.., comes from a line in section 1.10.32.The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested. Sections 1.10.32 and 1.10.33 from de Finibus Bonorum et Malorum by Cicero are also reproduced in their exact original form, accompanied by English versions from the 1914 translation by H. Rackham.",
                            thumbnail: "https://upload.wikimedia.org/wikipedia/commons/thumb/6/6d/Good_Food_Display_-_NCI_Visuals_Online.jpg/800px-Good_Food_Display_-_NCI_Visuals_Online.jpg"
                        },
                        {
                            id: "2",
                            title: "Sea Food Saled!",
                            previewText: "Very tasty indeed",
                            descriptionText: "This is really a delicious meal!",
                            thumbnail: "https://food.fnr.sndimg.com/content/dam/images/food/fullset/2004/5/14/0/bw2c12_chicken_broccoli2.jpg.rend.hgtvcom.826.620.suffix/1371584021202.jpeg"
                        },
                    ].find(el => el.id === context.params.id)
                })
            },1500)
        })
    },
}
</script>

<style scoped>
.single-recipe{
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}
.recipe-image{
    width: 100%;
}
p{
    width: 70%;
    margin-bottom: 50px;
}
</style>