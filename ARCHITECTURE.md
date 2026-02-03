# Architecture Overview

## High-Level Goal
API Guard sits in front of public APIs to enforce authentication,
rate limiting, and collect operational metrics.

## Core Components
- API Gateway
- Authentication Layer
- Rate Limiter
- Metrics Collector
- Target Service

## Request Flow
1. Client sends request with API key
2. Gateway validates API key
3. Rate limiter checks allowance
4. Request is forwarded to target API
5. Metrics are recorded
6. Response is returned to client

## Rate Limiting Strategy
- Algorithm: Token Bucket
- Scope: Per API key
- Backing store: Redis

## Failure Handling
- Redis unavailable
- Invalid API key
- Rate limit exceeded

## Design Principles
- Fail-safe defaults
- Low latency overhead
- Clear separation of concerns
