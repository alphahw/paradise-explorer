# Paradise Explorer

Simple ICIJ Paradise Papers explorer powered by a Neo4J graph database, (an eventual) GraphQL server/data gateway, and a SvelteKit + d3.js visualizer frontend.
Everything WIP… for the forseeable future.

## Data
[`paradise-explorer-data`](https://github.com/alphahw/paradise-explorer-data)

- Raw CSV sources
- Cleanup and GraphQL type definition generation scripts (written in node.js)
- Database dump(s)

## Data server/gateway
[`paradise-explorer-server`](https://github.com/alphahw/paradise-explorer-server)

Very simple GraphQL server/gateway to Neo4J.

## Frontend
[`paradise-explorer-fe`](https://github.com/alphahw/paradise-explorer-fe)

SvelteKit-based FE app with visualizations using d3.js. Currently reads data directly from a Neo4J database using the Neo4J JS driver, but one day hopefully powered by GraphQL.

## Backlog

- [ ] Data exploration
  - [x] Select suitabled storage
    - [X] Graph DB
      - [x] Neo4J
      - [ ] ArangoDB
  - [x] Containerized or cloud DB host?
    - [ ] docker
    - [x] Cloud (for now)
  - [x] Select cloud DB host
    - [x] GrapheneDB
    - [ ] Neo4J Aura

- [x] Data engineering
  - [x] Cleanup, format source CSVs for import
  - [x] Import data into local DB
    - [x] Nodes
    - [x] Edges
  - [x] Export local DB for cloud DB import
  - [x] Create/generate data types/definitions

- [x] Cloud DB setup
  - [x] Configure cloud DB (trial for now)
  - [x] Import local DB export into cloud DB
  - [ ] Create read-only user for initial visualization (not supported by Neo4J Community, unfortunately)

- [ ] Data gateway/proxy server engineering
  - [x] Select data gateway/proxy server API architecture
    - [ ] REST 
    - [x] GraphQL
  - [ ] Write server
    - ~[x] Serverless function in visualizer FE app~ (Neo4J Bolt protocol over WebSockets not supported in serverless env)
    - [ ] Authentication
      - [ ] API key system?
    - [ ] DB API calls
  - [ ] Select hosting
    - [ ] AWS?
    - [ ] Firebase?

- [ ] Visualizer FE app engineering
  - [x] Select FE framework
    - [ ] Next.js
    - [x] SvelteKit
  - [x] Select hosting solution
    - [x] Vercel?
    - [ ] AWS?
    - [ ] Firebase?
  - [ ] Write data server API client
    - [ ] GraphQL
  - [ ] Visualization
    - [ ] Select visualization solution
      - [ ] force-graph (simple and easy, but not working within SvelteKit)
      - [x] d3.js
    - [x] Write direct database query API (neo4j-driver based)
      - [x] Simple generic query statements
    - [ ] Implement visualization
      - [ ] d3.js force graph
    - [ ] Search/query input
      - [ ] Search bar
      - [ ] Implement very basic query input format
  - [ ] Deploy app
    - [ ] Vercel
    - [ ] Container somewhere, with server maybe?
