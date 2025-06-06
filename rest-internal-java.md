### 🔁 What Happens When You Hit a REST Endpoint in Spring Boot?

1. **Client Sends a Request**

   * The request first reaches the **embedded server** (like Tomcat, Jetty, etc.).

2. **DispatcherServlet Takes Control**

   * Spring’s `DispatcherServlet` is the front controller that receives all incoming HTTP requests.

3. **Filters are Triggered**

   * Any configured **filters** run first. These can handle:

     * Authentication & Authorization
     * CORS policies
     * Logging, etc.

4. **HandlerMapping Matches the Request**

   * Spring uses `HandlerMapping` to find the correct controller method based on URL and HTTP method.

5. **Interceptors Run**

   * Any registered **interceptors** execute:

     * `preHandle()` runs **before** the controller
     * `postHandle()` and `afterCompletion()` run **after**

6. **Controller Logic Executes**

   * The actual **controller method** runs and returns a response object.

7. **Exception Handlers Kick In (If Needed)**

   * If something goes wrong, global exception handlers (`@ControllerAdvice`, etc.) catch and handle the error.

8. **Filters Execute Again (on the Way Out)**

   * Response flows back through the filter chain again before leaving the server.

9. **Response Sent to the Client**

   * Finally, the response is serialized (e.g., to JSON) and sent back to the client.

---

### 🛠 Bonus Tip from Real Experience

I once had a bug where an **interceptor failed** because it was trying to access authentication info **before the filter** had processed it.

🔍 Fixed it by adjusting the **filter order** and adding **detailed logging** to each phase of the request flow — which helped trace exactly where things broke.
