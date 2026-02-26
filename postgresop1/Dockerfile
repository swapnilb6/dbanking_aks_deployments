FROM postgres:latest

# Set environment variables for PostgreSQL
ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=postgres
ENV POSTGRES_DB=dBanking_CMS

# Copy initialization scripts
COPY dBanking.CustomerOnboarding/01-create-role.sql /docker-entrypoint-initdb.d/01-create-role.sql
COPY dBanking.CustomerOnboarding/02-create-db.sql /docker-entrypoint-initdb.d/02-create-db.sql

# Expose PostgreSQL port
EXPOSE 5432

# Health check
HEALTHCHECK --interval=10s --timeout=5s --retries=5 \
  CMD pg_isready -U postgres

# Entrypoint and CMD are inherited from postgres:latest
