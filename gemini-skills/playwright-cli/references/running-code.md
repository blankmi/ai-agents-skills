# Running Code

Use `run-code` for Playwright features not exposed through the direct CLI commands.

## Syntax

```bash
playwright-cli run-code "async page => {
  // raw Playwright code
}"
```

## Common Uses

### Permissions And Geolocation

```bash
playwright-cli run-code "async page => {
  await page.context().grantPermissions(['geolocation']);
  await page.context().setGeolocation({ latitude: 37.7749, longitude: -122.4194 });
}"
```

### Wait Conditions

```bash
playwright-cli run-code "async page => {
  await page.waitForLoadState('networkidle');
}"
```

### Frames

```bash
playwright-cli run-code "async page => {
  const frame = page.locator('iframe').contentFrame();
  await frame.locator('button').click();
}"
```

### Downloads

```bash
playwright-cli run-code "async page => {
  const [download] = await Promise.all([
    page.waitForEvent('download'),
    page.click('a.download-link')
  ]);
  await download.saveAs('./downloaded-file.pdf');
}"
```

### Inspection

```bash
playwright-cli run-code "async page => {
  return {
    url: page.url(),
    title: await page.title()
  };
}"
```

## Guidance

- Keep `run-code` snippets small and single-purpose.
- Prefer regular CLI commands when they already cover the task.
- Add `try/catch` inside the snippet when failure is expected and should return structured output.
