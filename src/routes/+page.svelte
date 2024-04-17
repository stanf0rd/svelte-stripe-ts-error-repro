<script lang="ts">
  import { loadStripe, type Stripe } from "@stripe/stripe-js";
  import { Elements } from "svelte-stripe";
  import { onMount } from "svelte";

  let stripe: Stripe | null;

  onMount(async () => {
    stripe = await loadStripe("abc");
  });
</script>

{#if stripe}
  <Elements {stripe}>
    <!-- ... -->
  </Elements>
{/if}
