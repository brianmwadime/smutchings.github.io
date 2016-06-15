---
layout: page
title: stripe test
permalink: /stripe-test/
meta-description: Test for Stripe Checkout
---

STRIPE FORM SHOULD RENDER BELOW THIS LINE

<form action="/charge" method="POST">
  <script
    src="https://checkout.stripe.com/checkout.js"
    class="stripe-button"
    data-key="pk_live_gMpBWkn7HQlrRHJvGX4a6VKM"
    data-image="/square-image.png"
    data-name="Work Deposit"
    data-description="Deposit for upcoming work (£75.00)"
    data-amount="7500"
    data-currency="GBP"
    data-label="Pay Deposit"->
  </script>
</form>

BUT ABOVE THIS LINE