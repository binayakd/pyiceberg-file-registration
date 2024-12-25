# Registering Parquet Files Into Iceberg Tables Without Rewrites Using Pyiceberg

This repo is a companion to [this post](https://binayakd.tech/posts/2024-12-25-register-parquet-files-to-iceberg-without-rewrites/), which can we worked though using the Jupyter notebook `iceberg-file-registration.ipynb`.

To work though the Notebook demo, you would need the following installed:

1. Docker/Podman Compose
2. Python 3.12 or higher
3. uv Python project manager (optional)
2. Minio client (optional)

There is a docker compose file in this repo, that will start the Postgres and Minio instances, and also run an Minio client container to create the `warehouse` bucket in the Minio instance. Here I will be using Podman:
```bash
podman compose up
```

The actual data for Minio and Postgres will be stored in the `local-data` folder, in the respective folders.

Python 3.12 and uv package manage was used for this demo. So the dependencies are setup in the `pyproject.toml` and `uv.lock` file. To get started using uv, first create the python virtual environment and install the required dependencies (has to be run outside this notebook):

```bash
uv sync
```
Then start the Jupyter Lab server using this virtual environment:

```bash
uv run --with jupyter jupyter lab
```