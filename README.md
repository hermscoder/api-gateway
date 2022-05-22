# api-gateway
It's a component capable of routing the requests from users to the corresponding services. This component must be at the start of the request flow and can be named as API Gateway.


More than act just as a gate keeper the API Gateway It can address some additional concerns in the micro-services landscape like:

- Routing based on Request Headers
- Authentication & security
    - If we want to make sure all the requests are authenticated we can configure that in the API Gateway, contacting the authorisation server or whatever authentication mechanism we want to implement.
- Load Balancing
    - If the user makes a request to *user-service* and we have multiple instances of it*,* the gateway will make sure which instance to call and retrieve the response from this instance and return it to the user.
- SSL Termination
    - Usually if we are calling an external service we need to be sure to include the https scheme there by following the TLS protocol.
      So if the API Gateway is called from the outside with the TLS protocol with https the API Gateway, as it’s already part of the micro-services network, **won’t need https** to communicate with the services as this is **completely internal communication**.
      The SSL connection will be terminated at the entry point of the request, that’s why we say that the SSL Termination will happen at the API Gateway level.
      This is also implemented for us automatically by all the api gateways.


Some **API Gateway options** would be:

- **[Kong](https://github.com/Kong/kong)**

- **[Tyk.io](https://github.com/TykTechnologies/tyk)**

- **[Apigee](https://apigee.com/)**

- **[Amazon AWS API Gateway](https://aws.amazon.com/api-gateway/)**

- **[Spring Cloud Gateway](https://cloud.spring.io/spring-cloud-gateway/reference/html/)**

For our project we used Spring Cloud Gateway.