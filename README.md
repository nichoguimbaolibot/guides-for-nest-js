@Global()
- a function that can make a module globally available.
- usage for authentication or user services.

Exclusion of a certain method using a middleware
- 
consumer
  .apply(LoggerMiddleware)
  .exclude(
    { path: 'cats', method: RequestMethod.GET },
    { path: 'cats', method: RequestMethod.POST }
  )
  .forRoutes(CatsController);
