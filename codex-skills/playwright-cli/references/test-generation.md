# Test Generation

Use interactive browser work to discover the flow, then translate it into a maintained Playwright test.

## Workflow

1. Open the target page and inspect it with `snapshot`.
2. Perform the user flow with `click`, `fill`, `press`, and related commands.
3. Use the observed behavior to write a proper `@playwright/test` test with assertions.

## Example Shape

```typescript
import { test, expect } from '@playwright/test';

test('login flow', async ({ page }) => {
  await page.goto('https://example.com/login');
  await page.getByRole('textbox', { name: 'Email' }).fill('user@example.com');
  await page.getByRole('textbox', { name: 'Password' }).fill('password123');
  await page.getByRole('button', { name: 'Sign In' }).click();
  await expect(page).toHaveURL(/dashboard/);
});
```

## Guidance

- Treat the interactive session as discovery, not the final artifact.
- Prefer semantic locators such as roles and labels in the final test.
- Add assertions manually; actions alone are not a useful test.
