# Payments

The payments API provides endpoints required to take a stripe payment with your account. 

- [Checkout Session](./checkout_session.md)

### The checkout process

The payment process begins when your user visits your checkout page. Your checkout page should load the stripe payment form. Checkout the sample projects to see how we have implemented the payment form. 

To load the form, you will need to provide a ```clientSecret```. You can get this secret by sending a ```POST``` request to the ```checkout_session``` endpoint. If submitted properly, you will recieve a clientSecret you can add to your payment form.
