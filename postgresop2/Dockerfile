FROM postgres:latest

# Set environment variables for PostgreSQL
ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=postgres
ENV POSTGRES_DB=dBanking_profileMgt

# Copy initialization scripts
COPY dBanking.ProfileManagement/01_extensions.sql /docker-entrypoint-initdb.d/01-extensions.sql
COPY dBanking.ProfileManagement/DBScript01.sql /docker-entrypoint-initdb.d/02-dbscript.sql

# Expose PostgreSQL port
EXPOSE 5432

# Health check
HEALTHCHECK --interval=10s --timeout=5s --retries=5 \
  CMD pg_isready -U postgres

# Entrypoint and CMD are inherited from postgres:latest
