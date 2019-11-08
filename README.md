# springboot实现异步方法
- @JsonIgnoreProperties(ignoreUnknown = true)，将这个注解写在类上之后，就会忽略类中不存在的字段
- RestTemplate是Spring提供的用于访问Rest服务的客户端，RestTemplate提供了多种便捷访问远程Http服务的方法,能够大大提高客户端的编写效率
- RestTemplate默认依赖jdk的HTTP连接工具。当然你也可以 通过setRequestFactory属性切换到不同的HTTP源，比如Apache HttpComponents、Netty和OkHttp
- String类的format()方法用于创建格式化的字符串以及连接多个字符串对象
- 在Spring中，基于@Async标注的方法，称之为异步方法；这些方法将在执行的时候，将会在独立的线程中被执行，调用者无需等待它的完成，即可继续其他的操作
   - 返回的数据类型为Future类型，其为一个接口。具体的结果类型为AsyncResult,这个是需要注意的地方
   - 当计算完成后，只能通过get方法来获取执行结果，必要的话该方法会阻塞。通过cancel方法可以取消计算。一旦计算已经完成，便无法取消
   - cancel()：取消任务
   - get()：等待任务执行完成，并获取执行结果
   - get(long timeout, TimeUnit unit)：在指定的时间内会等待任务执行，超时则抛异常。