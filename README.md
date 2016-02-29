# Open-Falcon API Documentation

The Open-Falcon API is based on REST principles, all you need to use it is your Open-Falcon account. You must be authenticated and call HTTPs requests on the URLs listed below. 
This documentation covers the core resources you can used to manipulate objects on Open-Falcon. Review the information basic instructions if you are new to APIs.

>**Note:** We strongly discourage Open-Falcon customers from using the apiary Traffic Inspector. Any information you submit through Traffic Inspector is routed through a 3rd party, and is unsecured. If you choose to use Traffic Inspector against our recommendation, use your Open-Falcon TESTING credentials for API calls. _Never_ use your production credentials.

# Getting Started with the Open-Falcon APIs

Welcome to the Open-Falcon API reference! The Open-Falcon API is based on REST. This documentation lists and describes the individual resources you can used to manipulate objects on the Open-Falcon Platform. If you are new to APIs, review the info in this section.Often individual resources are used together in complex use cases. We describe many of these use cases on the Open-Falcon Developer Portal. Happy calling!!

# Allowed HTTPs requests:

- `POST` - Creates or updates a resource
- `PUT` - Updates a resource
- `GET` - Retrieves a resource or list of resources
- `DELETE` - Delete a resource

# Typical Server Responses

- 200 `OK` - The request was successful (some API calls may return 201 instead).
- 201 `Created` - The request was successful and a resource was created.
- 204 `No Content` - The request was successful but there is no representation to return (that is, the response is empty).
- 400 `Bad Request` - The request could not be understood or was missing required parameters.
- 401 `Unauthorized` - Authentication failed or user does not have permissions for the requested operation.
- 403 `Forbidden` - Access denied.
- 404 `Not Found` - Resource was not found.
- 405 `Method Not Allowed` - Requested method is not supported for the specified resource.
- 429 `Too Many Requests` - Exceeded Open-Falcon API limits. Pause requests, wait one minute, and try again. 
- 503 `Service Unavailable` - The service is temporary unavailable (e.g. scheduled Platform Maintenance). Try again later.

# Use Cases
## Create an Alearting Rule
For an alearting rule, you should have 1) an Template for strategies, 2) an UserGroup for notification, and 3) and HostGroup to apply this rule.

### Steps
1. Create [HostGroup](#usecase-1-1), [UserGroup](#usecase-1-2), and [Template](#usecase-1-3)
2. [Edit the strategy](#usecase-1-4).
3. [Bind Template to UserGroup](#usecase-1-5).
4. [Bind Template to HostGroup](#usecase-1-6).

## Get Data for Your Customized Graph
You could also use other chart library (e.g., jsflot, D3.js, highcharts) to draw your own graphs. 

### Steps
1. [Get the endpoint](#usecase-2-1).
2. [Get the counter of endpoints step 2](#usecase-2-2).
3. [Using the result of step 1 and 2 to get the graph history.](#usecase-2-3).

# Feedback and Help
If you have ideas about how we can improve this documentation (or want to tell us how great it is), contact us on [Github](https://github.com/xiaomi/open-falcon/issues). If you have questions about using these APIs, check out our [developer documentation](book.open-falcon.com), which contains articles describing complex use cases. (Some use cases are also listed briefly in this API reference under Use Cases).If you still have a question, fire a issue on [Github](https://github.com/xiaomi/open-falcon/issues).

# API Design References
+ [API Blueprint Specification](https://github.com/apiaryio/api-blueprint/blob/master/API%20Blueprint%20Specification.md)
+ [API Blueprint Examples 1](https://raw.github.com/apiaryio/api-blueprint/master/examples/15.%20Advanced%20JSON%20Schema.md)
+ [GooData APIs](https://developer.gooddata.com/api#/introduction/getting-started-with-the-gooddata-apis/typical-server-responses)
+ [Best Practices for Designing a Pragmatic RESTful API](http://www.vinaysahni.com/best-practices-for-a-pragmatic-restful-api)

# API List

```
        Agent (Port 1988)
            /ips
            /page/cpu/usage
            /page/df
            /page/diskio
            /page/memory
            /page/system/loadavg
            /page/system/uptime
            /plugin/reset
            /plugin/update
            /plugins
            /proc/cpu/mhz
            /proc/cpu/num
            /proc/cpu/usage
            /proc/kernel/hostname
            /proc/kernel/maxfiles
            /proc/kernel/maxproc
            /proc/kernel/version
            /proc/memory
            /proc/system/loadavg
            /proc/system/uptime
            /run
            /system/date
            /v1/push
        Alarm (Port 9912)
            /event/solve
        
        Dashboard (Port 8081)
            /api/endpoints
            /api/counters
            /api/tmpgraph
        Fe (Port 1234)
            /about/:name:string
            /auth/login
            /auth/register
            /me/team/c
            /root
            /sso/logout/:sig:string
            /sso/sig
            /sso/user/:sig:string
            /team/all
            /team/query
            /team/users
            /user/in
            /user/qrcode/:id:int
            /user/query
        Graph (Port 6071)
            /api/recv/
            /count
            /counter/all
            /history/
            /index/cache/
            /index/update/
            /index/updateAll
            /index/updateAll/concurrent
            /last/
            /statistics/all
            /v2/api/recv
            /v2/history
            /v2/index/cache
            /v2/last
        
        Heartbeat Server (Port 6031)
            /expressions cache.ExpressionCache.Get()
            /plugins/ cache.GetPlugins()
        
        Judge (Port 6081)
            /count
            /expression/
            /history/
            /strategy/
        
        Links (Port 5090)
            /store
        
        Portal (Port 5050)
            /api/action/<action_id>
            /api/metric/query
            /api/pings
            /api/template/<tpl_id>
            /api/template/query
            /api/uic/group
            /api/version
            /group/bind/template
            /group/create
            /group/delete/<group_id>
            /group/rename
            /group/templates/<grp_id>
            /group/update/<group_id>
            /host/<host_id>/groups
            /host/<host_id>/templates
            /host/add
            /host/maintain
            /host/remove
            /host/reset
            /host/unbind
            /plugin/bind
            /plugin/delete/<plugin_id>
            /strategy/<sid>
            /strategy/delete/<sid>
            /strategy/update
            /template/bind/node
            /template/create
        Query
            /counter/all
            /graph/history
            /graph/info
            /graph/last
            /graph/last/raw
            /graph/history/one (Not Found)
            /graph/info/one (Not Found)
        
        Task (Port 8002)
            /index/delete
            /index/updateAll
            /statistics/all
        
        Transfer
            /filter/
            /trace/
```
