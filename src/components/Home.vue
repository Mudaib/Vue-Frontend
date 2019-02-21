<template>
  <div class="start">
	<section class="card home-top">
    <div class="container-fluid">
      	<ul class="nav" id="nav-home">
      <li class="nav-item" >How it works</li>
      <li class="nav-item">Log In</li>
      <li class="nav-item" v-on:click="testApi()">Sign Up</li>
    </ul>
    </div>
	
	</section>
  <section class="header-home container-fluid">
    <div class="row">
      <div class="col">
        <img src="" alt="Paysmosmo" srcset="">
      </div>
       <div class="col">
        <form class="form-inline">
          <div class="form-group">
          <input type="text" class="form-control" id="header-form" placeholder="🔍  Search for products"/>
          <button id="header-btn" class="btn btn-warning">Search</button>
          </div>
        </form>
      </div>
      <div class="col">
        <p style="text-align:right; line-height:40px">
          <i class="ti-shopping-cart header-icon"></i>
        <i class="ti-heart header-icon"></i>
        <i class="ti-bell header-icon"></i>
        </p>
      </div>
    </div>
  </section>

  <section class="container-fluid jumbo">
    <div class="row">
      <div class="col-3">
          <ul class="list-group list-cat">
          <div id="men" class="list-group-item active d-flex justify-content-between align-items-center">
            <h1 id="cat-id">Categories</h1> 
          </div>
          <li :key="index" v-for="(cat, index) in categories" class=" cat-list list-group-item d-flex justify-content-between align-items-center">{{cat.name}}
            <span class="badge badge-pill">
              <i class="ti-angle-right go-icon"></i>
            </span>
         </li>
        </ul>
      </div>
      <div class="col-9">
      <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
    <ol class="carousel-indicators">
      <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="3"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img  height="450" :src="img.slide1" class="d-block w-100 img slide-img" alt="...">
        <div class="slide-text">
          <h2 class="slide-head-text" >{{products[0].name}}</h2>
          <p class="slide-p-text">{{products[0].description}}
          </p>
          <button class="btn btn-warning slide-btn">SHOP NOW</button>
        </div>
      </div>
      <div class="carousel-item">
        <img height="450" :src="img.slide2" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img height="450" :src="img.slide3" class="d-block w-100" alt="...">
      </div>
      <div class="carousel-item">
        <img height="450" :src="img.slide4" class="d-block w-100" alt="...">
      </div>
    </div>
  </div>
  </div>
  </div>
</section>


  <section class="container-fluid cat-sec">
    <div class="card cat-sec-card">
      <div class="card-header cat-header">
        EXPLORE POPULAR CATEGORIES
      </div>
      <div class="body">
        <div class="row cat-row justify-content-center">
          <div class="col-md-3 cat-col" :key="index" v-for="(prod,index) in catProd">
          <img :src="img.shoe" width="250px" height="200px"> 
            <h3 class="cat-text-head">{{prod.name}}</h3>
            <span class="cat-rating starrating d-flex flex-row-reverse">
              <input type="radio" id="star5" name="rating" value="5"><label class="ti-star" for="star5" title="5 star"></label>
              <input type="radio" id="star4" name="rating" value="4"><label class="ti-star" for="star4" title="4 star"></label>
              <input type="radio" id="star3" name="rating" value="3"><label class="ti-star" for="star3" title="3 star"></label>
              <input type="radio" id="star2" name="rating" value="2"><label class="ti-star" for="star2" title="2 star"></label>
              <input type="radio" id="star1" name="rating" value="1"><label class="ti-star" for="star1" title="1 star"></label>
            </span><br>
            <del class="cat-price-promo">₦{{prod.old_price}}</del>
            <p class="cat-price">₦{{prod.price}}</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="new-stuff" class="container-fluid cat-sec">
    <div class="card cat-sec-card">
      <div class="card-header cat-header">
        EXPLORE NEW STUFFS
      </div>
      <div class="body">
        <div class="row cat-row justify-content-center">
          <div class="col-md-3 cat-col" :key="index" v-for="(prod, index) in newProducts">
            <img :src="img.shoe" width="250px" height="200px"> 
              <h3 class="cat-text-head">{{prod.name}}</h3>
              
              <br>
              <del class="cat-price-promo">₦{{prod.old_price}}</del>
              <p class="cat-price">₦{{prod.price}}</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <footer class="d-footer">
    <div class="container-fluid footer-foot">
      <div class="row justify-content-center">
      <div class="col footer-text">
        <p>PAYSMOSMO</p>
        <p>Help give out inventory loans to <br>
        cooperative members with ease </p> 
      </div>
      <div class="col footer-text">
        <ul class="nav flex-column">
          <h4 class="nav-item">Contact</h4>
          <li class="nav-item"><a href="">Registration</a></li>
          <li class="nav-item"><a href="">About Us</a></li>
          <li class="nav-item"><a href="">Contact Us</a></li>
        </ul>
      </div>
      <div class="col">
         <ul class="nav flex-column">
          <h4 class="nav-item">Help</h4>
          <li class="nav-item"><a href="">Privacy Policy</a></li>
          <li class="nav-item"><a href="">How it works</a></li>
          <li class="nav-item"><a href=""> Terms & Conditions</a></li>
        </ul>
      </div>
      <div class="col">
        <div class="row">
          <h4>Stay Connected</h4>
        </div>
        <div class="row">
          <div class="col">
            <div class="social-icon">
              <i class="ti-facebook"></i>
            </div>
          </div>
          <div class="col">
            <div class="social-icon">
              <i class="ti-twitter"></i>
            </div>
          </div>
          <div class="col">
            <div class="social-icon">
              <i class="ti-instagram"></i>
            </div>
          </div>
        </div>
      </div>
      <div class="col">
        <p>Back to top <a href="#" class="ti-angle-up"></a></p>
      </div>
    </div>
    </div>
    
    <div class="inner-footer">
      <p>©2018 PAYSMOSMO</p>
    </div>
  </footer>
    
  </div>
</template>




	
<script>
import '@/assets/css/slider.css'
import '@/assets/css/bootstrap.min.css'
import '@/assets/css/themify-icons.css'
import router from '../router'
import axios from 'axios'
export default {
  name: 'start',
  components: {
    
    },
  data () {
    return {
      CatApiUrl:' http://demo4507124.mockable.io/categories',
      prodApiUrl:'http://demo4507124.mockable.io/products',
      tokenStr:'ki494034jkjdfsi49e8943iufkljfdkj4oi3uu498usajhasdfoi4jkjfi434',
      categories:null,
      products:null,
      catProd:null,
      img:{
        slide1:require('../assets/img/slide1.png'),
        slide2:require('../assets/img/slide2.png'),
        slide3: require('../assets/img/slide3.png'),
        slide4:require('../assets/img/slide4.png'),
        shoe:require('../assets/img/shoe.jpeg')
      }
    }
  },  
	 methods: {
    checkRating:function(item){
      return item.rating >= 3
    }
  },
  computed:{
      newProducts(){
        let take =[]
        for(var i=0; i<=3; i++){
          take.push(this.products[i])
        }
        return take
      }
    },
 mounted(){
   axios.get(this.CatApiUrl, {
      headers:{"Authorization" : 'Bearer ${this.tokenStr}'}
    }).then((response) => {
      console.log('Got the categories data')
      this.categories = response.data;
    });
    
    axios.get(this.prodApiUrl, {
      headers:{"Authorization" : 'Bearer ${this.tokenStr}'}
    }).then((response) => {
      console.log('Got the product data')
     this.catProd = response.data.filter(this.checkRating);
     this.products = response.data;
    });
 }
}
</script>

<style>
 @import url('https://fonts.googleapis.com/css?family=Lato:100,300,400,700');
body{
  max-width: 100%;
  font-family:"Lato",san-serif;
}
.nav-item{
  margin-left: 20px;
  float:right;
  
}
#nav-home{
  float:right;
}

.home-top{
  height:45px;
   -webkit-box-shadow: -1px 5px 5px -4px rgb(189, 189, 189); 
-moz-box-shadow: -1px 5px 5px -4px rgb(189, 189, 189); 
box-shadow: -1px 5px 5px -4px rgb(189, 189, 189);  

}
.container-fluid{
  padding-left: 50px;
  padding-right: 50px;
}

.header-home{
  margin-top: 20px;
}
#header-form{
  width: 800px;
  border-radius: 0;
  background: rgb(216, 216, 216);
}

#header-btn{
  border-radius: 0;
}

.header-icon{
  margin-left: 30px;
}

.jumbo{
  margin-top: 20px;
  height: 400px;
  float: left;
}

#men{
  border-radius:0;
  background:#00c853;
  border:0px solid white;
}

#cat-id{
  font-size: 18px;
  font-weight: 700;
}

.go-icon{
  font-size: 15px;
  font-weight: 600;
  
}

.cat-list{
  cursor: pointer;
}

.list-cat{
  height: 450px;
  -webkit-box-shadow: -1px 5px 5px -4px rgb(189, 189, 189); 
-moz-box-shadow: -1px 5px 5px -4px rgb(189, 189, 189); 
box-shadow: -1px 5px 5px -4px rgb(189, 189, 189); 
}
.carousel-indicators li.active {
    border-radius: 12px;
    width: 12px;
    height: 12px;
    background-color: #eeff41;
}
.carousel-indicators li {
    border-radius: 12px;
    width: 12px;
    height: 12px;
    background-color: white;
}
.slide-img{
  float: left;
}
.slide-text{
  position: absolute;
  margin-top:20%;
  margin-left: 20px;
}

.slide-head-text{
  color: white;
  font-weight: bolder;
  font-size: 40px;
}

.slide-p-text{
  color: white;
}

.slide-btn{
  background: none;
  border:2px solid #eeff41;
  color: #eeff41;
  font-weight:600;
}

.cat-sec{
  margin-top:70px;
  float:left;
}

.cat-sec-card{
  -webkit-box-shadow: -1px 5px 5px -4px rgb(189, 189, 189); 
-moz-box-shadow: -1px 5px 5px -4px rgb(189, 189, 189); 
box-shadow: -1px 5px 5px -4px rgb(189, 189, 189); 
}

.cat-row{
  padding-top: 20px;
}

.cat-header{
  background: white;
}

.cat-text-head{
  font-size: 16px;
  font-weight:500;
  margin-top: 10px;
  text-align: left;
  margin-left: 20px;
}

.cat-col{
  display:inline-block;
  float:none;
  text-align:center;
}

.starrating > input {display: none;}

.starrating > label:before { 
  display: inline-block; 
}

.starrating > label
{
  color: #222222; 
}

.starrating > input:checked ~ label
{ 
  color: #ffca08;
}

.starrating > input:hover ~ label
{ 
  color: #ffca08;
}
.cat-rating{
  float: left;
  margin-left: 20px;
}

.cat-price-promo{
  float: left;
  margin-left: 20px;
}

.cat-price{
  float: right;
  margin-right: 20px;
  }

  footer{
    width: 100%;
    float: left;
    background: #4E505A;
    padding-top: 50px;
    color: white;
  }

  .footer-foot{
    height: 150px;
  }

  #new-stuff{
    margin-top:50px;
    margin-bottom: 100px;
  }

  .inner-footer{
    background: #26282C;
    height: 70px;
    margin-top:20px;
    text-align: center;
    padding-top: 30px;
  }

  .social-icon{
    width: 30px;
    height: 30px;
    border: 1px solid white;
    border-radius: 200px;
    padding-top:3px;
    text-align: center;
  }

  a{
    color: white;
  }

  a:hover{
    text-decoration: none;
  }
/**.carousel {
  width:640px;
  height:360px;
}*/

</style>