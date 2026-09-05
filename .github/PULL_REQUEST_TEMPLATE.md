## Summary

<!-- What changed, and why? Keep this focused. -->

## Ownership

<!-- Why does this repository own the change? Note any cross-repository contract or data dependency. -->

## Verification

<!-- List the checks you ran: tests, typecheck, lint, build, manual verification, screenshots, data validation, etc. -->

- [ ] Relevant automated checks pass
- [ ] I manually verified the affected behavior where appropriate
- [ ] I added or updated tests when the behavior changed

## Trust-boundary review

Check any that apply:

- [ ] No privacy/security/data-ownership boundary changes
- [ ] Private student data handling changed
- [ ] Authentication/authorization/encryption changed
- [ ] Campus facts, provenance or routing evidence changed
- [ ] Public API/SDK contract changed
- [ ] AI/MCP permissions or delegated context changed

If any boundary changed, explain the impact and why the design remains appropriately scoped.

## User-facing changes

<!-- Screenshots/recordings for UI work; migration or compatibility notes for contract/data changes. -->

## Documentation

- [ ] No documentation change needed
- [ ] Repository documentation updated
- [ ] Public developer documentation needs or includes a corresponding update

## Final checklist

- [ ] The change is focused and belongs in this repository
- [ ] No credentials, tokens, secrets or private user data were committed
- [ ] Deterministic domain logic was not unnecessarily duplicated in another interface
- [ ] Accessibility and uncertainty states were preserved where relevant
