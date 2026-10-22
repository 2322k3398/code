index.js:

import React from "react";
import ReactDOM from "react-dom/client";
import { BrowserRouter } from "react-router-dom";
import App from "./App";


const root = ReactDOM.createRoot(document.getElementById("root"));

root.render(
  <BrowserRouter>
    <App/>
    
  </BrowserRouter>
);

---------------------

<!-- App.js:

import {Routes,Route } from "react-router-dom"
import Product from "./Product"
import Cart from "./Cart"
function App(){
    return(
    <div>
    <Routes>
        <Route path="/" element={<Product/>}/>
        <Route path="/Cart" element={<Cart/>}/>
    </Routes>
    </div>)
}


export default App;

-----------------------
Product.js:

import React from "react";
import { useNavigate } from "react-router-dom";

function Product(){
    const navigate=useNavigate();

    const products=[
        {id:1,name:"mobile",price:15000},
        {id:2,name:"laptop",price:50000},
        {id:3,name:"headphone",price:2000}
    ]
    function addtocart(product){
        navigate("/Cart",{state:product})
    }
    return(
        <div>
            <h1>Products</h1>

        {products.map((product)=>(
            <div key={product.id}>
                <h2>Name:{product.name}</h2>
                <p>Price:{product.price}</p>
            <button onClick={()=>addtocart(product)}>Add To Cart</button>
            </div>
        ))
        }
        </div>
    )}
export default Product;

-----------------------
Cart.js:

import React from "react";
import { useLocation,useNavigate } from "react-router-dom";
function Cart(){
  const location = useLocation();
  const navigate=useNavigate();

  const product=location.state;
  if(!product){
    return(
      <div>
        <h2>No product selected</h2>
        <button onClick={()=>navigate("/")}>back to products</button>
      </div>
    )
  }

return(
  <div>
    <h1>Cart Page</h1>
    <h2>{product.name}</h2>
    <p>Price:{product.price}</p>
        <button onClick={()=>navigate("/")}>back to products</button>

  </div>
)


}
export default Cart; -->



