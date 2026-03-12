# Request Mocking

Use routing when the task needs blocked assets, mocked API responses, or modified requests.

## Core Commands

```bash
playwright-cli route "**/*.jpg" --status=404
playwright-cli route "**/api/users" --body='[{"id":1,"name":"Alice"}]' --content-type=application/json
playwright-cli route "**/*" --remove-header=cookie,authorization
playwright-cli route-list
playwright-cli unroute "**/*.jpg"
playwright-cli unroute
```

## Pattern Examples

```text
**/api/users
**/api/*/details
**/*.{png,jpg,jpeg}
**/search?q=*
```

## Advanced Cases

Use `run-code` when you need:

- Conditional responses based on request data
- Delays or simulated failures
- Partial modification of real upstream responses
- Logic that depends on headers, body content, or previous requests
