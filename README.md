## Topology

```mermaid
graph TD;
    NGINX-->WP1;
    NGINX-->WP2;
    WP1-->DB;
    WP2-->DB;
```

## Goal

Mencoba load balancing wordpress. Load test dengan k6.