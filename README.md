# MovieReact

A movie discovery app built with React and Vite. Browse popular films, search for any title, and see what's trending based on real-time search activity tracked in Appwrite.

## Features

- Browse movies sorted by popularity
- Search movies with debounced input (500ms delay — no unnecessary API calls)
- Trending section showing the 5 most-searched movies, updated live
- Movie cards displaying poster, rating, language, and release year
- Loading and error states handled gracefully

## Tech Stack

- **React 18** + **Vite**
- **Tailwind CSS v4**
- **TMDB API** — movie data
- **Appwrite** — backend database for tracking search counts

## Getting Started

### 1. Clone and install

```bash
git clone https://github.com/ankita-058/MovieReact.git
cd MovieReact
npm install
```

### 2. Set up Appwrite

In your Appwrite project, create a database and a collection with these 4 attributes:

| Attribute | Type | Size | Required |
|-----------|------|------|----------|
| `searchTerm` | String | 255 | Yes |
| `count` | Integer | — | Yes |
| `movie_id` | Integer | — | Yes |
| `poster_url` | String | 2048 | Yes |

Then go to the **Indexes** tab and create an index on `count` (type: Key, order: DESC).

### 3. Configure environment variables

Create `.env.local` in the project root:

```env
VITE_TMDB_API_KEY=your_tmdb_v3_api_key

VITE_APPWRITE_PROJECT_ID=your_project_id
VITE_APPWRITE_DATABASE_ID=your_database_id
VITE_APPWRITE_COLLECTION_ID=your_collection_id
```

- TMDB key: [themoviedb.org](https://www.themoviedb.org) → Settings → API → **API Key (v3 auth)**
- Appwrite IDs: found in your Appwrite console URL when navigating to your collection

### 4. Run

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) in your browser.

## Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build |
| `npm run lint` | Run ESLint |
