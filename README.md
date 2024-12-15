How to run example:

Lunch application with following env variable `spring_profiles_active=dev`

DeferredLogFactory logs will show `Loading property from AWS Parameter Store with name: /config/, optional: true` 
Meaning `ParameterStoreConfigDataLocationResolver` was invoked and profile is dev didn't disable the integration.


Go to `/config` folder and uncomment the `application-dev.properties`.
Binder now who binds properties will see profile specific values such as `spring.cloud.aws.parameterstore.enabled=false` binded.
This will disable loading of ParamStore for dev profile and `ParameterStoreConfigDataLocationResolver` will mock `ConfigData` as empty resource.