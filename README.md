# Virus-Database-Notes
Notes about a potential virus database

## Database Requirements / Features

### Architecture 

The backend server should be able to be standalone-installed, where potential users could setup a server of their own for their own local use, whether installing it on their own machine or via a Docker image. It should also be able to scale to user needs. 

Current planned backend setup: Cloudflare workers or just `npm run dev` for local environments, connected to Supabase (with a PostgreSQL database) and file storage on Cloudflare R2 (likely a local file system or some kind of mock S3 / R2 system for local environments). Look into libraries that help manage code complexity / abstract platform-specific syntax away. 

### Data Storage

CRAM format: Highly compressed, lossless, reference-based, sequence data format. May have higher processing overhead for compression/decompression. 

### Data Operations

#### 1. Importing / Exporting Databases

#### 2. Querying Data

Querying By Sequence

Querying By Metadata

Live-Sequence Searching (?)

Searching For Mutations

#### 3. Adding Data

Read Mapping

#### 4. Analyzing / Updating Data

Multi-Sequence Alignment

Consensus Sequence Generation

Variant Calling

#### 5. Archiving / Deleting Data

## Potential Database Paradigms

Will likely initially use PostgreSQL because it is an industry standard, has a comprehensive ecosystem, and can also support full text search (among other features). I (Daniel) also am the most familiar with this database language, so it will be easiest for me to get some kind of MVP out. Possibly can be later augmented with Redis, a graph database, or a search engine database. 

### 1. Relational Database (PostgreSQL)

### 2. Key-Value Database (Redis)

### 3. Graph Database (Neo4j)

Potentially interesting article: https://medium.com/codex/turn-neo4j-into-a-genome-browser-e94c7311dfab

### 4. Search Engine (Lucene, ElasticSearch)

Possible speed up of finding sequences in large database.

### 5. Vector Database

Possible speed up of finding similar sequences (as represented by vectors that point in the similar direction). Could be useful for variant calling speed up. 

## Databases in Literature / in Use

GeNemo: https://pubmed.ncbi.nlm.nih.gov/27098038/

## Frontend Interface

### Frontend Requirements / Features

See Data Operations. 

### Frontend Tech Stack

Svelte (likely). 
