### Cookie和Session

> Cookie  客户端存储<br/>
  生成的Cookie（设置的信息）会返回给客户端，后续客户端每一次请求都会带上Cookie信息。

```` bash
设置Cookie
Cookie cookie = new Cookie("userName", "Fluently");
cookie.setPath("/");
cookie.setMaxAge(60*60*60*24);
resp.addCookie(cookie)

获取Cookie
Cookie[] cookie = request.getCookies();
````

> Session 服务器端存储<br/>
  Session设置之后的信息不会发送给客户端，会保存在服务端，但是会自动生成JSESSIONID发送给客户端用于唯一标识客户，客户端后续的每次请求都会带上JSESSIONID作为标识。

```` bash
设置Session
HttpSession session = req.getSession(true);
session.setAttribute("userName", "123");
session.setMaxInactiveInterval(60*30);

获取Session
HttpSession session = req.getSession(true);
session.getAttribute("userName");
````
参考文档
- [理解Session 和Cookie机制](https://blog.csdn.net/u014638988/article/details/51456248)
- [Cookie/Session机制详解](https://blog.csdn.net/taozi8023/article/details/51423144)
