<template>
  <div class="resto">
    <router-link :to="'/restos/' + resto.restaurantID" class="filterrate resto">
      <div class="info-resto">
        <div class="name-resto">
          <h3>{{resto.name}}</h3>
          <p>Cuisine {{resto.kitchenType}}</p>
        </div>
        <span class="stars">
          <i class="fas fa-star" :class="{yellow: resto.averageRating >= 1} "></i>
          <i class="fas fa-star" :class="{yellow: resto.averageRating >= 2} "></i>
          <i class="fas fa-star" :class="{yellow: resto.averageRating >= 3} "></i>
          <i class="fas fa-star" :class="{yellow: resto.averageRating >= 4} "></i>
          <i class="fas fa-star" :class="{yellow: resto.averageRating >= 5}"></i>
        </span>

      </div>        <div class="icones">
          <div>
            <i class="fas fa-trash-alt red"></i>
          </div>
          <div><router-link :to=" resto.restaurantID + '/modifyresto' ">
            <i class="fas fa-pen blue"></i> </router-link>
          </div>
        </div>
    </router-link>
  </div>
</template>

<script>
export default {
  props: ["resto"]
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.icones{
    display: flex;
    
}
.fa-trash-alt{
    margin-right: 10px;
}
.red{
    color: crimson;
}
.blue{
    color: rgb(0, 129, 235);
}
a {
  text-decoration: none;
  color: black;
}
.yellow {
  color: crimson;
}
.resto {
  width: 320px;
  text-align: left;
  break-inside: avoid;
  overflow: hidden;
}
img {
  width: 100%;
}
h3 {
  margin: 8px 0 5px 0;
  font-size: 1.1em;
}
p {
  margin: 0 0 8px 0;
}
.info-resto {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 20px;
}
.stars {
  font-size: 14px;
}

</style>