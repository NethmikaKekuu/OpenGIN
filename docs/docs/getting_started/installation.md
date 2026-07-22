# Installation & Setup

## Quick Development Setup

### Prerequisites
- Docker and Docker Compose
- Go 1.19+ (for CORE service)
- Ballerina 2201.13.4 (for APIs)

### Start the System

1. **Start databases**
   ```bash
   docker-compose up -d mongodb neo4j postgres
   ```
2. **Ingest data to the databases using data backups (for development)**

   Sample development backups (MongoDB, Neo4j, PostgreSQL) and a data insertion script are available in [LDFLK/data-backups](https://github.com/LDFLK/data-backups). See that repository for the backup files and `opengin/scripts/insert_data.py`.

3. **Start CORE service**
   ```bash
   docker-compose up -d core
   ```
4. **Start APIs**
   ```bash
   docker-compose up -d ingestion read
   ```

### Test the System

**Run E2E tests**
```bash
cd opengin/tests/e2e && ./run_e2e.sh
```
