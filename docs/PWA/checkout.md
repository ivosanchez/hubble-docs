# Checkout 
The hubble checkout process is split in several pages. For a distraction free checkout
experience all checkout pages are assigned to the `layouts/hubble_light.vue` component.
To switch between the different steps hubble comes with a _CheckoutProgressBar.vue_.

## `checkout/cart`
Besides the classic cart overview with a list of products, customers can directly checkout via 
_Amazon Pay_ and apply vouchers.

- CartItemsList
- Coupon
- Totals 
- AmazonPayButton

## `checkout/login`
This is where your customer can log in with his/her credentials, continue as a Guest or use 
a express checkout payment experience like _Amazon Pay_.

- RegisterForm
- LoginForm

## `checkout/payment`
Your customer sees his available billing and shipping addresses and can create, edit or choose 
a different address from our great _CustomerAddresses.vue_ component.
On this page your customer have to choose a payment method and a shipping method. Optionally 
he/she can also apply a voucher and write an order comment.

At this moment hubble supports [Payone](https://www.bspayone.com/) as a great payment provider,
which is fully integrated in hubble checkout without leading the customer away from your checkout.

- CustomerAddresses
- PaymentMethods
- ShippingMethods
- Coupons 
- OrderComment 

## `checkout/summary`
This is the last chance for the customer to review the order before he/she accepts the terms
and conditions and places the order.

- CustomerAddresses
- CartItemsListNonInteractive
- Totals

## `checkout/success`
After the successful response from the payment provider, the order will be placed via api call
to your shop system. If your shop responds with no errors, the customer will be redirected
to the success page where he/she sees the order in total. Customer will see a notification to
check their e-mail inbox for an order confirmation.

- OrderDetail

