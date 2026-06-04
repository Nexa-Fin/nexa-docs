# API Reference 🔌

Complete API documentation for Nexa Pay.

## Base URL

```
https://api.nexa-fin.com/v1
```

## Authentication

All requests require a JWT token in the Authorization header:

```
Authorization: Bearer YOUR_JWT_TOKEN
```

## Endpoints

### Authentication
- `POST /auth/register` - Register new account
- `POST /auth/login` - Login
- `POST /auth/refresh` - Refresh token
- `POST /auth/logout` - Logout

### Cards
- `GET /cards` - List cards
- `POST /cards` - Create card
- `GET /cards/{id}` - Get card details
- `PATCH /cards/{id}` - Update card
- `DELETE /cards/{id}` - Delete card

### Transactions
- `GET /transactions` - List transactions
- `GET /transactions/{id}` - Get transaction details
- `POST /transactions` - Create transaction

### Webhooks
- `POST /webhooks` - Register webhook
- `GET /webhooks` - List webhooks
- `DELETE /webhooks/{id}` - Delete webhook

## Response Format

```json
{
  "success": true,
  "data": {...},
  "timestamp": "2024-01-01T00:00:00Z"
}
```

## Error Handling

```json
{
  "success": false,
  "error": {
    "code": "INVALID_REQUEST",
    "message": "Invalid request parameters"
  }
}
```

---

For detailed endpoint documentation, see [Endpoints](./endpoints.md)