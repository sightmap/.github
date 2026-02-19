# .sightmap/

**A semantic map of your application, for AI agents.**

`sitemap.xml` tells search engines how to crawl your site.  
`.sightmap/` tells AI agents how to understand your app.

---

When an AI coding agent needs to fix a bug on your checkout page, it greps through your codebase, guesses at component relationships, and hopes it's editing the right file. Sightmap eliminates the guessing.

A sightmap is a structured YAML file that lives in your repo. It maps every page, component, and interactive element in your application — giving any AI agent instant understanding of your app's architecture.

```yaml
# .sightmap/checkout.yaml
version: 1

views:
  - name: CheckoutPage
      route: /checkout
      description: Cart review and payment flow
      source: src/pages/Checkout.tsx
      components:
        - name: CartSummary
          selector: '[data-component="CartSummary"]'
          source: src/components/CartSummary.tsx
          description: Order line items with quantities and running total
          children:
            - name: line-items
              selector: '[data-element="line-items"]'
            - name: order-total
              selector: '[data-element="order-total"]'

        - name: PaymentForm
          selector: '[data-component="PaymentForm"]'
          source: src/components/PaymentForm.tsx
          description: Credit card input and order submission
          children:
            - name: card-number
              selector: '[data-element="card-number"]'
            - name: submit-order
              selector: '[data-element="submit-order"]'

        - name: ConfirmationModal
          selector: '[data-component="ConfirmationModal"]'
          source: src/components/ConfirmationModal.tsx
          description: Post-purchase confirmation with order details
```

### What agents get from a sightmap

- **Build accuracy** — the agent knows where components live and how they connect before writing code
- **Self-validation** — the sightmap defines what "correct" looks like, so agents can check their own work
- **Cross-agent portability** — define your app structure once; Claude Code, Cursor, Codex, and any other agent can consume it

### Get started

→ **[Read the spec](https://github.com/sightmap/spec)** — schema docs, examples, and agent integration guides  
→ **[sightmap.org](https://sightmap.org)** — project homepage

---

<sub>Open-source spec maintained by the [Subtext](https://subtext.fullstory.com) team · MIT License</sub>
