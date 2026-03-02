Date: 2026-02-03
Tags: [[code level patterns]], [[pragmatism]]

Instead of
```ts
function calculateDiscount(userTier: string): number {
    // The business rules are hardcoded directly into the logic
    if (userTier === "vip") {
        return 0.25;
    } else if (userTier === "premium") {
        return 0.15;
    } else if (userTier === "standard") {
        return 0.05;
    } else {
        return 0.00;
    }
}
```

Build something like
```json
// discounts.json
{ "vip": 0.25, "premium": 0.15, "standard": 0.05, "gold": 0.20 }
```

```ts
import * as fs from 'fs';

// 1. Define the shape of our configuration metadata
type DiscountRules = Record<string, number>;

// 2. Load the configuration dynamically at runtime (Node.js example)
const rawData = fs.readFileSync('discounts.json', 'utf-8');
const discountRules: DiscountRules = JSON.parse(rawData);

function calculateDiscount(userTier: string): number {
    // 3. The code doesn't care about the specific tiers.
    // It looks up the tier in the config, and defaults to 0.00 if not found.
    return discountRules[userTier] ?? 0.00;
}
```

But wait, configurable doesn't mean a file of configuration.