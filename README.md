
 function Rorder(piro){
	
   var urib = 'https://indodax.com/tapi/';

 var nonce=Math.floor(Date.now() / 1000);
  var postb ='method=trade&'+piro+'&nonce='+nonce;
 var sha512screet = CryptoJS.HmacSHA512(postb, screet);
   //  console.log(postb+' : '+ piro  );
 let hb = new Headers(); 
 hb.append('Content-Type','application/x-www-form-urlencoded'); 
   hb.append('User-Agent','kontol kebo  \n\r'); 

hb.append('Sign', sha512screet)
hb.append('Key', key) 
let reqb = new Request(urib, {
 //credentials: 'include',
 method: 'POST',
 headers: hb,
 body: postb ,
});
fetch(reqb)
.then(
 function(response) {
   if (response.status !== 200) {
  console.log('error: ' +  response.status);
  return;
   }

 
   response.text().then(function(data) {
	  
	   myObj = JSON.parse(data);
	  var sussi  = myObj.success;
 
 		
  const text  = myObj.success;
 const eror  = myObj.error;
	 
	 
	 if (text == 0 ){
	   alert(   eror + piro);	

	   }else
	   {   alert(   text + piro);	  }
	   
	   
		
		
		
		
	//	console.log(data );
		
		

 document.location.reload();
   
 
	 
 
 
  })
  
  	 })
	 
	
		 
	}
	 
	
