<template>
    <nav >
		<h1 class="logo"><a href="#"><i class="fa fa-play-circle fa-2x "></i></a></h1>
        <ul class="nav-items">
            <li><a href="#">Home</a></li>
            <li><a href="#">Trending</a></li>
            <li><button>Sign Up</button></li>
            <li><button>Login</button></li>
        </ul>
	</nav> 
</template>

<style>
    * {
	box-sizing: border-box;
}

body {
    margin: 0;
    color:#35d7a5;
    font-family: 'Raleway';

   
}

ul {
  margin: 0;
  padding: 0;
  list-style: none;
  font-size: 1.2rem;
  font-weight: 600;
  letter-spacing: 2px;
}


a {
	text-decoration: none;
    text-transform: uppercase;
    color: #35d7a5;

}
ul li button {
    background-color: white;
    outline: none;
    border: 1px solid #35d7a5;
    border-radius: 3%;
    padding: 10px 30px;
    font-size: 1.2rem;
    color:#35d7a5;
    font-family: 'raleway';
    font-weight: 600;
    letter-spacing: 2px;    

}

nav{
  display:flex;
  justify-content:space-around;
  margin-bottom: 2%;
  box-shadow: 0 0 13px -1px #35d7a5;
  
}
.logo{
    padding-left: 3%;
    flex-grow: 1;
}
.nav-items {
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-grow: 3;
}

@media screen and (max-width:920px){
  nav{
    justify-content:space-around;
  }
}
@media screen and (max-width:600px){
  nav{
    align-items:center;
    flex-direction:column;
    
  }
  .nav-items {
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    
  }
  ul li,
  ul li button {
    margin: 3%;
    font-size: 0.6rem;
    width: 120px;
    text-align: center;
}
    .logo {
        padding: 0;
    }
}


</style>
