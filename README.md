# stockton

A distributed cache written in Go

# Idea/Concept

- Start simple. Leverage HTTP. Grow to different protocols or networking
- Build client that leverage network protocols. Clients can also hold local cache aka hot cache. Hot cache is invalidated through subscription notification
- Distributed cache can notify pariticpants to disable an entry on the local cache
- Should be able to support telemetry (thinking different interface and package)
- Support multiple caching algorithms including LRU, LFU, ARC, TTL based sizing
- Redudant caching mechanisms, first focus would be primary/secondary nodes
- - Handle rebalancing in the background as nodes drop in and out
- - Maintain an address book of keys to primary/secondary locations, share address book across all nodes
- - If multiple nodes are dropped, nothing can be done to save entry. 