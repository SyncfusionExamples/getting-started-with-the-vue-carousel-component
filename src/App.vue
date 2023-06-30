<template>
  <div class="control-container">
    <ejs-carousel :dataSource="birdsList" :itemTemplate="'itemTemplate'" >
           <template v-slot:itemTemplate = "{data}">
              <div>
                <img :src="getImage(data.imageName)" :alt="data.Name"
                      style="height:250px;width:100%;">
                <div><h2>{{ data.Name }}</h2>
                     <p>{{ data.Content }}</p></div>
              </div>
          </template>
    </ejs-carousel>
  </div>
</template>

<script>
import { 
  CarouselComponent,
  
 } from "@syncfusion/ej2-vue-navigations";
export default {
  components: {
    "ejs-carousel": CarouselComponent,
   
  },
  data: function()
  {
    return{
        birdsList:[
        { ID: 1, Name: "Cardinal", imageName: 'cardinal', Content: "Cardinalidae is a family of New World-endemic passerine birds that consists of cardinals, grosbeaks, and buntings. It also includes several birds such as the tanager-like Piranga and the warbler-like Granatellus. As such, membership of this group is not easily defined by a single or even a set of physical characteristics, but instead by molecular work." },
        { ID: 2, Name: "Kingfisher", imageName: 'hunei',Content: "Kingfishers are a family, the Alcedinidae, of small to medium-sized, brightly colored birds in the order Coraciiformes. They have a cosmopolitan distribution, with most species found in the tropical regions of Africa, Asia, and Oceania, but also can be seen in Europe."},
        { ID: 3, Name: "Keel-billed-toucan", imageName: 'costa-rica',Content: "The keel-billed toucan (Ramphastos sulfuratus), also known as sulfur-breasted toucan, keel toucan, or rainbow-billed toucan, is a colorful Latin American member of the toucan family. It is the national bird of Belize. The species is found in tropical jungles from southern Mexico to Colombia."  },
        { ID: 4, Name: "Yellow-warbler", imageName: 'kaohsiung',Content: "Yellow warblers are small widespread songbirds found in the Americas. The summer males of this species are generally the yellowest warblers wherever they occur. They are brilliant yellow below and greenish-golden above. Winter females and immature birds all have similarly greenish-yellow uppersides and are a duller yellow below. "  },
        { ID: 5, Name: "Bee-eater", imageName: 'bee-eater',Content: "With populations spread across parts of China, Bangladesh, Bhutan, India, Thailand, Vietnam and other neighbouring countries, Blue-bearded Bee-eaters prefer forest areas, rural gardens and parks as habitats. These birds have an overall green plumage with a bluish colouration on their face and neck and yellow underparts. "  }
      ],
    };
  },
  methods:
  {
    getImage: function(bird) {
      return "https://ej2.syncfusion.com/products/images/carousel/" + bird + ".png";
    }
  }
 }
</script>

<style>
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
@import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";


.img-container {
  height: 100%;
  margin: 0;
}
 .control-container {
 margin: 0 auto 2em;
 max-width: 450px; 
 height: 460px;
} 
.e-carousel .e-carousel-indicators.e-default .e-indicator-bars .e-indicator-bar .e-indicator div 
{
  background-color: #e7e7e7;
}

.e-carousel .e-carousel-indicators.e-default .e-indicator-bar.e-active .e-indicator div 
{
  background-color: red;
}
.e-carousel-navigators .e-previous
{
  margin-bottom: 208px;
}
.e-carousel-navigators .e-next
{
  margin-bottom:208px;
}

.img-caption {
   color: #fff; 
  font-size: 1rem;
  position: absolute;
  bottom: 3rem;
  width: 100%;
   text-align: center; 
}
</style>
