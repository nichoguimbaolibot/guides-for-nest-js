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

Multiple Middleware
- consumer.apply(cors(), helmet(), logger).forRoutes(CatsController);

Functional Middleware
- export function logger(req, res, next) {
  console.log(`Request...`);
  next();
};

Global Middleware
- implement in the main.ts
const app = await NestFactory.create(ApplicationModule);
app.use(logger);
await app.listen(3000);
