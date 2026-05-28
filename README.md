# Movie Pic Pipeline

Short demo pipeline that builds and deploys a React frontend and Flask backend to EKS.

- **Frontend URL:** http://a17aff8f796f54da993961295d10592f-482155947.us-east-1.elb.amazonaws.com/
- **Backend URL:** http://a46fba1e220614940bcf5838240b80ff-1328591864.us-east-1.elb.amazonaws.com/movies

Quick notes

- **Local dev:** run backend on `http://localhost:5000` and frontend with `npm start` in `starter/frontend`.
- **CI/CD:** GitHub Actions workflows under `.github/workflows/` build, tag and push images to ECR and deploy to EKS.
- **Build-time API config:** The frontend expects `REACT_APP_MOVIE_API_URL` at build time (passed as a `--build-arg`).

Troubleshooting

- If the UI shows no movies, ensure `REACT_APP_MOVIE_API_URL` points to the backend base URL (no trailing `/movies`) and redeploy the frontend image.
- Check backend `/movies` returns `{"movies":[...]}` and CORS is enabled.

Files of interest

- `starter/frontend/Dockerfile`, `starter/frontend/src/components/MovieList.js`
- `starter/backend/movies/resources.py`, `starter/backend/__init__.py`

License: see LICENSE.md
