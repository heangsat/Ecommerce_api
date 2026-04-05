# Express Backend

Simple Node.js + Express backend with MongoDB, product APIs, item APIs, and image uploads via Multer.

## Tech Stack

- Node.js
- Express
- MongoDB + Mongoose
- Multer (file upload)
- dotenv

## Project Structure

- `server.js` - main app entry point
- `models/Item.js` - item model
- `models/product.js` - product model
- `uploads/` - uploaded images
- `.env` - environment variables (not committed)

## Setup

1. Install dependencies:

```bash
npm install
```

2. Create your environment file:

```bash
cp .env.example .env
```

If you do not have `.env.example`, create `.env` manually with:

```env
PORT=4000
MONGODB_URI=your_mongodb_connection_string
# Optional in production (for hosted URL)
RENDER_EXTERNAL_URL=https://your-app-url
```

3. Start the server:

```bash
npm start
```

The API runs on `http://localhost:4000` by default.

## API Endpoints

### Health

- `GET /` - basic status response

### Products

- `POST /api/product` - create product (supports image upload as `image` field)
- `GET /api/product` - list products
- `PUT /api/product/:id` - update product (supports image upload)
- `DELETE /api/product/:id` - delete product

### Items

- `POST /api/items` - create item
- `GET /api/items` - list items

## Preventing Sensitive Files from Being Pushed

This project includes `.gitignore` rules for:

- `.env`
- `.env.*`
- `node_modules/`

If `.env` or `node_modules` were already committed before adding `.gitignore`, untrack them once:

```bash
git rm -r --cached node_modules .env
```

Then commit the change:

```bash
git add .gitignore README.md
git commit -m "Add README and ignore env/node_modules"
```
