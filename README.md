# Superheroes API

Flask API for managing superheroes and their powers.

## Models

- **Hero**: Has many powers through HeroPower
- **Power**: Has many heroes through HeroPower  
- **HeroPower**: Junction table with strength validation

## Setup

```bash
pip install -r requirements.txt
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
python seed.py
```

## Run

```bash
python app.py
```

API runs on `http://localhost:5000`

## Endpoints

- `GET /heroes` - List all heroes
- `GET /heroes/:id` - Get hero by ID with powers
- `GET /powers` - List all powers
- `GET /powers/:id` - Get power by ID
- `PATCH /powers/:id` - Update power description
- `POST /hero_powers` - Create hero-power association

## Validations

- Power description: minimum 20 characters
- HeroPower strength: must be 'Strong', 'Weak', or 'Average'