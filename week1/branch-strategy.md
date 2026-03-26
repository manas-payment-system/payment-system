# Branch Strategy
**Project:** Payment System
**Author:** Backend Engineer

## Branch Structure

| Branch | Purpose | Who uses |
|--------|---------|----------|
| `main` | Stable, production-ready code | Protected — PR only |
| `develop` | Active development base | All team members |
| `feature/*` | New features | Backend Engineer |
| `hotfix/*` | Urgent bug fixes | Backend Engineer |

## Rules
- `main` is protected — no direct push allowed
- All changes go through Pull Request
- PR requires at least 1 review before merge
- Feature branches are created from `develop`
- Naming: `feature/payment-transaction`, `feature/user-account`

## Flow
```
feature/xxx → develop → main
```

## Example
```bash
git checkout develop
git checkout -b feature/payment-transaction
# work...
git push origin feature/payment-transaction
# open Pull Request → develop
```
