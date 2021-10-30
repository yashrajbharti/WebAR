# Table of Contents
1. **[Introduction](#Introduction)**
2. **[Steps](#Steps)**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**a. [Scan the QR code](#Scan-the-QR-code)**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**b. [Enter the AR World](#Enter-the-AR-World)**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**c. [On Marker detection](#On-Marker-detection)**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**d. [Payment Option](#Payment-Option)**  
3. **[Code](#Code)**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**a. [Marker Detection](#Marker-Detection)**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**b. [Model Rotation](#Model-Rotation)**   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**c. [Model Scaling](#Model-Scaling)**   
4. **[FAQs](#FAQs)**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**a. [Why AR.js?](#Why-ARjs)**  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**b. [What next?](#What-next)**  
5. **[Wrapping up](#Wrapping-up)**  
6. **[Contributing](#Contributing)** 
- - -

# Introduction

Built using [AR.js](https://github.com/AR-js-org/AR.js), we aim at developing an Augmented Reality Experience that not only lets you interact with 3D models but guides you through the whole workflow from advertising to purchasing, creating a unique WebAR shopping experience on the scan of a QR code. 
  
- - -
  
# Steps
1. **Scan the QR code**: At a mall that supports cashless transactions, which is essential these days, the customer can interact and enjoy WebAR experiences that aim to advertise the products via WebAR and purchase them. To do so, the customer has first to scan the QR code, just as the one shown below.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<img src="./Images%20and%20QR%20codes/main-qr-code.png" height="200px"></img> 
  
2. **Enter the AR World**: After one has scanned the QR code, they get redirected to our web app. One needs to give camera permissions, and then they are all set to watch for markers and have fun with AR.  
  
3. **On Marker detection**: The markers can either be showcased inside the QR code or separately as shown below (showing full-size image, so you get a better demonstration if you're following along): 
    
![](./Images%20and%20QR%20codes/fifa.png)
![](./Images%20and%20QR%20codes/reebok.png)
![](./Images%20and%20QR%20codes/iphone.png)  
  
4. **Payment Option**: Every time a new marker gets detected, the payment options come along with the AR models, making the workflow from advertising to purchase an essential keypoint for our web app.
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;One can have the whole fun experience at an *ARified* mall with such markers, load up WebAR experiences, enjoy and interact with models, and a cashless payment option to make our WebAR app more than just an aesthetic piece of work.

- - -

# Code  
## Marker Detection   
```javascript
AFRAME.registerComponent('registerevents', {
		  init: function () {
			var marker = this.el;

			  marker.addEventListener('markerFound', function() {
				var markerId = marker.id;
				console.log('markerFound', markerId);
        });
			  marker.addEventListener('markerLost', function() {
				var markerId = marker.id;
				console.log('markerLost', markerId);
        });
		}
});
```  
## Model Rotation  
```javascript
 handleRotation(event) {
    if (isMarkerVisible) {
      el.object3D.rotation.y +=
        event.detail.positionChange.x * rotationFactor;
      el.object3D.rotation.x +=
        event.detail.positionChange.y * rotationFactor;
    }
  }
```
## Model Scaling
```javascript
handleScale(event) {
    if (isMarkerVisible) {
      this.scaleFactor *=
        1 + event.detail.spreadChange / event.detail.startSpread;

      this.scaleFactor = Math.min(
        Math.max(this.scaleFactor, this.data.minScale),
        this.data.maxScale
      );

      el.object3D.scale.x = scaleFactor * initialScale.x;
      el.object3D.scale.y = scaleFactor * initialScale.y;
      el.object3D.scale.z = scaleFactor * initialScale.z;
    }
  }
```
- - -
# FAQs
## Why AR.js?
* AR.js is a lightweight library for Augmented Reality on the Web.
* Completely opensource, with MIT license.
* Updated frequently.
* Compatible with all the browsers and all the devices.
* Pretty fast since it can perform at 60FPS easily.
* Very easy to be used, mainly because it can work with A-frame.  
  
## What next?
* The AR experiences made to raise sales and attract masses and not just limited to effectively work as a product development tool.
* They can itself become the product, as NFTs: a novel kind of collectible. 
* AR NFTs are immersive experiences that can be shared via AR-enabled websites or apps.
* One can sell these AR models as NFTs, which has become the most noticeable growing up source of revenue for artists. 
* The proof of ownership from the specific brands allows and motivates us to think these AR models have the flexibility and future scope in such a superb direction.
* NFT ownership is recorded on the blockchain, a digital ledger of transactions that underpins cryptocurrencies like bitcoin and Ether.
* [More info on Augmented Reality NFTs](https://poplar.studio/blog/augmented-reality-nfts/)
* [WebAR shop example](https://dressx.com)

- - -
  
# Wrapping up

**AR**ifying the shops and malls with our solution will work as a catalyst to lure the customers into loading up an AR on their phone and interact with it and make them more interested in the purchase. Also, we don't want the buyers to keep searching over a catalog in AR then adding to buy finally. That would become like an online shopping site but in AR. We want to reduce the UI to give them a one-tap buying solution, so the AR guides the whole workflow for the purchase with a clever UX.
  
![](https://i.ibb.co/37hqBth/pngaaa-com-1761516.png)
- - -
# Contributing

* **Fork** the repo on GitHub
* **Clone** the project to your own machine

To run it locally on your machine run the following command
```
npm init 
```
```
npm i -s express
```
```
npm start
```
 Open http://localhost:3000/ 
* **Commit** changes to your own branch
* **Push** your work and create a pull request

NOTE: Be sure to merge the latest from "upstream"!!
