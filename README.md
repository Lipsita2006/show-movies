# Movie Recommender — Team Project (4 members)

Live demo: https://movie-recommender-2-2qtf.onrender.com/

Short description
-----------------
A prototype Movie Recommender that returns movie suggestions similar to user prompts. The current demo returns movie titles only (no external links). This project was developed collaboratively as a class submission and is presented here as a showcase of the team’s work and my contributions.

Source code
-----------
The original application source is not included in this repository. This repo documents the project, the dataset I curated, and the DB schema I helped design.

How to use the live demo
------------------------
- Visit the demo: https://movie-recommender-2-2qtf.onrender.com/
- Try any movie:
"Inception"
"2022"

Note: the demo currently returns titles only (neither external detail pages/links nor all movies similar to the movie prompt).

My role — Data Collection & Database Management
----------------------------------------------
- Curated and cleaned the movie metadata used by the recommender (titles, release year).
- Assembled and prepared the dataset.
- Designed and maintained the small relational DB schema together with one other teammate (tables, normalization, and basic indices).
- Documented known data quality issues and limitations if worked in future (currently unavailable individually).

Data sources & curation notes
-----------------------------
- Data was collected from public movie metadata sources and supplemented by manual entries for missing items.
- Cleaning steps included:
  "Deduplication (title + year)"
  "Trimming/standardizing titles and years"
- The authorization to share other sources is not enabled as it is not the full project source.

Database schema (representative)
--------------------------------
The production schema was small and normalized. Below is a representative schema that matches the dataset I curated and managed during the project.

```sql
CREATE TABLE movies (
  id INTEGER PRIMARY KEY,
  title TEXT NOT NULL,
  year INTEGER
);

CREATE TABLE recommendations (
  id INTEGER PRIMARY KEY,
  movie_id INTEGER REFERENCES movies(id),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

Limitations & known issues
--------------------------
- Prototype returns only movie titles (no external links or deep metadata).
- Recommendation logic is basic and not fully tuned — ranking may not reflect nuanced relevance.
- Dataset is limited in size and coverage; many films are underrepresented.
- No user personalization or persistent user profiles in the deployed demo.
- Work on improvements was paused after initial discussion with the team.

Acknowledgements / contributors
-------------------------------
Team of four students. This showcase documents my contributions in data collection and DB management.
