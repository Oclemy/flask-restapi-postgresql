# Flask REST API Boilerplate + PostgreSQL

A minimal, production-ready Flask REST API with CRUD, PostgreSQL, pagination, and one-click Railway deploy.

---

## One-click Deploy

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/deploy/Qp7bSt?referralCode=-Xd4K_&utm_medium=integration&utm_source=template&utm_campaign=generic)

## Quick Start (Local)

```bash
pip install -r requirements.txt
python main.py            # runs on http://localhost:8080
```


## Environment Variables

| Variable | Default | Notes |
|---|---|---|
| `DATABASE_URL` | `sqlite:///dev.db` | Auto-set by Railway Postgres plugin |
| `SECRET_KEY` | `change-me-in-production` | Set a real secret in prod |
| `PORT` | `5000` | Auto-set by Railway |

## API Endpoints

| Method | Path | Description |
|---|---|---|
| `GET` | `/` | Service info |
| `GET` | `/health` | Health check |
| `GET` | `/api/items?page=1&per_page=20` | List items (paginated) |
| `POST` | `/api/items` | Create item `{"name": "...", "description": "..."}` |
| `GET` | `/api/items/<id>` | Get single item |
| `PUT` | `/api/items/<id>` | Update item |
| `DELETE` | `/api/items/<id>` | Delete item |

## Example

```bash
# Create
curl -X POST http://localhost:8080/api/items \
  -H "Content-Type: application/json" \
  -d '{"name": "My Item", "description": "Hello world"}'

# List
curl http://localhost:8080/api/items
```
