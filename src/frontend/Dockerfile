FROM python:3.13-alpine AS builder

# Install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

WORKDIR /app

# Install dependencies in cache
RUN --mount=type=cache,target=/var/cache/uv,id=uv-cache \
    --mount=type=bind,source=uv.lock,target=uv.lock \
    --mount=type=bind,source=pyproject.toml,target=pyproject.toml \
    uv sync --locked --no-install-project --no-editable

# Copy the rest of the app into the intermediate image
COPY . /app

# Sync the project and install it.
RUN --mount=type=cache,target=/var/cache/uv,id=uv-cache \
    uv sync --locked --no-editable

FROM python:3.13-alpine

# Create a non-root user and group with specific IDs
RUN addgroup -S -g 1000 app && \
    adduser -S -u 1000 -G app app

# Copy the environment, but not the source code
COPY --from=builder --chown=app:app /app/.venv /app/.venv

# Set the user to the non-root user
USER app

# Expose the port
EXPOSE 22111

CMD ["/app/.venv/bin/study-tracker-frontend"]