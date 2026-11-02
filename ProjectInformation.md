The reasoning for picking this project and subject matter is the following:
I've been trying to get into the Site Reliability Sphere in Software Development, and this project would automate assessing logs, that would otherwise have to be interpreted manually. This project seeks to automate the process.
I have had some work in the sector, assessing logs and I saw a gap in technology that could be filled with something to automate the assessment process for logs.
> Note: You still have a copy of the Log files on the Laptop. They can be found there. In retrospect, they're kind of useless to me actually.

## Language and Technology Choices
* Go: The Go language is a good starting point for a project like this because it is a stateless, high-throughput, and is good with concurrency, which this project if implemented at any reasonable scale, would have quite a lot of.
* Docker: This project will have multiple services talking to each other. Docker is a great natural fit for this, as it's designed for this exact purpose.
* PostgreSQL: The best database tech. Imagine giving Larry Ellison your money you absolute cuck lol. Of course, I COULD use MariaDB, but I've used that 100 times before, so.
* NATS: I'm going to implement NATS instead of a different messaging queue service, it seems to be the meta with Go, not RabbitMQ or other messaging services.

## Project Structure
### Log Files
One example of a log that might be found in the log file. I think I might automatically generate these, rather than serve actual internet traffic. There's no real point in doing that.
```json
{
    "CacheResponseStatus":200,
    "ClientASN":15395,
    "ClientCountry":"gb",
    "ClientIP":"162.13.194.49",
    "ClientRequestHost":"www.website.com",
    "ClientRequestMethod":"POST",
    "ClientRequestURI":"/edge/rest/v2/offers",
    "ClientRequestUserAgent":"Mozilla/5.0 (Windows NT 10.0; WOW64; rv:50.0) Gecko/20100101 Firefox/50.0",
    "EdgeColoID":21,
    "EdgeEndTimestamp":1617702676620000000,
    "EdgeRateLimitAction":"",
    "EdgeRateLimitID":0,
    "EdgeResponseBytes":1192,
    "EdgeResponseStatus":200,
    "EdgeStartTimestamp":1617702676583000000,
    "OriginIP":"51.89.192.10",
    "OriginResponseStatus":200,
    "OriginResponseTime":15000000,
    "RayID":"63ba1de0ad515475",
    "WAFAction":"unknown",
    "WAFFlags":"0",
    "WAFRuleID":"",
    "ZoneID":14140753
}
```
