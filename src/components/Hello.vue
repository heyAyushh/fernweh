<template>
<div>
  <div class="hello centered" v-show="slide1" >
    <h1 >{{ msg }}</h1>
    <a  v-on:click="slide2 = true, slide1=false" >Next</a>
  </div>

<!-- 2duration -->
<div v-show="slide2 " class="hello centered">
<h1>from</h1>
        <date-picker v-model="datefrom" :config="options1"></date-picker>
        <h1>to</h1>
                <date-picker v-model="dateto" :config="options2"></date-picker>
                      <a  v-on:click="slide3 = true, slide2=false" >Next</a>
</div>
<!-- 3tour templates -->
<div v-show="slide3" class="hello centered">
  <h1> tour templates</h1>
    <b-card title="Card Title"
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2">
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of the card's content.
    </p>
    
    <b-button href="#" variant="primary">Go somewhere</b-button>

  </b-card>
            <a  v-on:click="slide4 = true, slide3=false" >Next</a>
</div>
<!-- 4venues -->
<div v-show="slide4" class="hello centered">
  <h1>choose venues</h1>
    <b-card title="Card Title"
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2">
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of the card's content.
    </p>
    <b-button href="#" variant="primary">Go somewhere</b-button>
  </b-card>
            <a  v-on:click="slide5 = true, slide4=false" >Next</a></li>
</div>

<!-- 5mode of transport -->
<div v-show="slide5" class="hello centered">
<h1>mode of transport</h1>
  <h1>car</h1>
    <b-card title="Card Title"
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2">
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of the card's content.
    </p>
    <b-button href="#" variant="primary">Go somewhere</b-button>
  </b-card>
  <h1>bike</h1>
      <b-card title="Card Title"
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2">
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of the card's content.
    </p>
<!--  need a driver -->
    <b-button href="#" variant="primary">Go somewhere</b-button>
  </b-card>
                  <a  v-on:click="slide6 = true, slide5=false" >Next</a></li>
</div>

<!-- 6 want to have a tour guide? -->
<div v-show="slide6" class="hello centered">    
    <div>
    <b-form-group label="Need a tourist guide?">
      <b-form-radio-group id="btnradios1"
                          buttons
                          v-model="selected"
                          :options="optionss"
                          name="radiosBtnDefault" />
    </b-form-group>
            <a  v-on:click="slide7 = true, slide6=false" >Next</a></li>
</div>
</div >
<!-- 7 price -->
<div v-show="slide7" class="hello centered">
<h1> Your total cost is {{price}} rs</h1>
</div>

<!-- Payment -->
<div v-show="payment">
  <h1> Enter payment options </h1>
              <a  v-on:click="slide7 = true, slide6=false" >Next</a></li>
</div>
</div>
</template>

 
<script>
import "bootstrap/dist/css/bootstrap.css";

// Import this component
import datePicker from "vue-bootstrap-datetimepicker";

// Import date picker css
import "pc-bootstrap4-datetimepicker/build/css/bootstrap-datetimepicker.css";

export default {
  name: "hello",
  
  data() {
    return {
      slide1:true,
      slide2:false,
      slide3:false,
      slide4:false,
      slide5:false,
      slide6:false,
      slide7:false,

      selected: 'radio1',
      optionss: [
        { text: 'Yes', value: 'radio1' },
        { text: 'No', value: 'radio2' }
      ],
    dateto: new Date(),
      options1: {
        format: "DD/MM/YYYY",
        useCurrent: false
      },
      datefrom: new Date(),
      options2: {
        format: "DD/MM/YYYY",
        useCurrent: false
      },
      msg: "travelessly",
      price: 1600
    };
  },
  components: {
    datePicker
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.hello{
  align-content: center;
  height: 50%;
}

.centered {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
}
</style>
