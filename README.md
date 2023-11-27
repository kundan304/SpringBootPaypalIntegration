# SpringBootPaypalIntegration

/*
Spring boot paypal integration
			> https://www.youtube.com/watch?v=GykDyG0ELms
			> https://www.sourcecodeexamples.net/2021/01/spring-boot-paypal-payment-gateway.html
for card : check this tutorial > https://www.youtube.com/watch?v=OYF8SY92iys
step 1:  generate correct card number using
			> https://developer.paypal.com/api/rest/sandbox/card-testing/#link-creditcardgeneratorfortesting
step 2: get random address for the selected country using
			>https://www.bestrandoms.com/random-address-in-us

 */

/*#####################RECHARGE WALLET BY PAYPAL#######################
  Step 1.click on recharge button
  step 2.open input form for payment
  step 3.submit input
  step 4. 	(I.)Now payment order initialized and payment id created
  			(II.)log db for this process
  			(III.)Set Execute payment action & Cancel payment action
  			(IV.)get url to execute payment
  			(V.)Return Execute Payment URI in Response
  step 5. do get call from ui to execute payment
  step 6. control will go to paypal payment
  step 7. do the required payment process
  step 8. payment continue or Cancel
  step 9. 	(a.)if payment Cancel then Cancel payment action will executed that you set at the time of payment order creation
  			(b.)if payment submitted then
  				1.)Execute payment action will get triggered that you set at the time of payment order creation
  				2.)Execute payment process will start ,
  					 I.)If payment is success then
  					 	(a.)log Db for this payment id
  					 	(C.)update Balance for this shipper
  						(b.)Redirect required action/url
  					II.)if payment fail then
  						(a.)log Db for this payment id
  						(b.)Redirect required action/url
  ####################CREATE BOOKING #####################
  step 1. create booking and submit
  step 2. check total prices <=account balance
  			if (yes) then allow submit booking and reduce balance
  		    if (No) then show error message while submitting the booking form
  		    	Go For recharge first
 */

/*
How to test this application :
Open Postman:
URI :	http://localhost:9090/payment
HttpMethod : POST
Method BODY :
	{
    "price":"4.9",
	"description":"testAgain"
	}
Response : https://www.sandbox.paypal.com/cgi-bin/webscr?cmd=_express-checkout&token=EC-4U813821RY996460B
do request this uel in browser
 */




/*
  Step 1 : Do post call to : http://localhost:9090/payment
  				Microservices Call > Booking App to paymentServic
  				Now payment order initialized and payment id created
  				log db for this process
  				payment success & cancel action set
  				get url to execute payment
  step 2 : call execute payment url
  step 2 : 	(a.)login paypal and click on continue payment
  			(b.)select credit card or debit card payment method and click on continue
  step 4 :	(a.)Paypal will redirect success url
  			(b.)Execute payment
  			(c.)if payment success then
  					(a.)log Db for this payment id
  					(b.)Redirect required action/url
  			(D.)if payment fail then
  					(a.)log Db for this payment id
  					(b.)Redirect required action/url
 */
