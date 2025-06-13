
# Scaling Document

## Scaling Frontend
- Current State:

- Static React SPA hosted on Netlify

- Netlify’s CDN automatically scales horizontally across global edge nodes.

## What this means:

- Virtually infinite concurrent users on frontend

- No server-side logic involved on Netlify

- Almost no work needed to scale frontend

## Scaling the Backend (Render — Node.js, Express, Socket.io)
- This is where real scaling challenges emerge:
## Key bottlenecks:
- HTTP API scaling (Express)

- WebSocket connections (Socket.io)

- MongoDB query latency

- JWT validation overhead

- a) Horizontal Scaling (more instances)
- Move backend service to Autoscaling Render Instances.

- Scale-out multiple instances based on CPU/memory usage.

- Load balancing handled automatically by Render.

- b) Sticky Sessions for WebSockets
- Socket.io requires sticky sessions if scaled horizontally.

- Use a Redis-based session store:
This allows Socket.io instances to coordinate rooms across distributed backend nodes.

- c) Database Connection Pooling
- Use connection pooling with MongoDB Atlas.

- Upgrade Mongo Atlas cluster to M10+ tiers.

- Scale-out shards as concurrent connections grow.

- d) API Gateway Layer
Introduce API Gateway (like AWS API Gateway / Nginx / Traefik)

- Handle authentication throttling, API quotas, rate limiting centrally.

- e) Global CDN + Reverse Proxy
Frontend stays on Netlify.

- Introduce reverse proxy/CDN (Cloudflare) to shield backend.

- f) Logging, Monitoring & Observability (New Relic or Datadog for distributed tracing)


## Future Scale Targets:
- Socket.io works well up to 10K-50K connections per instance.

Beyond that:

- Move to Redis-backed pub/sub model.

- Use managed WebSocket services (like AWS API Gateway WebSockets or Ably).

- For enterprise scale:

- Consider Kafka for message queueing.

- Event sourcing model for chat message persistence
