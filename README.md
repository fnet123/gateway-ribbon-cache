# Gateway caching

Caching implemented with 2 filters:

- CachingPreFilter: reads cache and fill response if URI found in cache
- CachingPostFilter: stores response into cache using URI as key

Cache name uses service id.

We should take into account whether the response is gzipped.

## Define an API to manage caches

Maybe on top of gateway routes.

- GET /api/gateway/routes/[serviceId}/cache returns cache information (# elements, hits, configuration, ...) if any
- POST /api/gateway/routes/{serviceId}/cache/clear clears cache 

## Add tests and look at closing connections

https://github.com/spring-cloud/spring-cloud-netflix/pull/1196
