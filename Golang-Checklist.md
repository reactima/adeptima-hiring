## Golang Developer Check List
Here’s that we discuss during the interview.

- Have you pass Go Tour, https://tour.golang.org/welcome/1
- Have you read Effective Go, https://golang.org/doc/effective_go.html
- Have you tried to reinvent MVC frameworks patterns in Go?
    * Which Go framework is the best from your perspective and why?
    * Did you use any tool from [Gorilla Toolkit](http://www.gorillatoolkit.org/)?
    * What’s your opinion on Echo? [Echo - High performance, minimalist Go web framework](https://echo.labstack.com/)
- What did you use for dependency management?
- What package did you use for logging: log, logrus, zap etc.?
- Did you use panic/recover and why?
- Did you know what is virtual methods table and does it present in the Go?
- What is Go good for? Concurrency / Networking? What else?
- Golang and its features
    * How to handle Context for logging and monitor system resources?
    * What’s the potential source for Race condition / Data race / Deadlocks in Go?
    * Do you understand Async programming patterns in Go?
    * Would you avoid using ORM? If - yes, why?
    * When not to use Reflect?
    * Do you understand Interfaces implementation in Go?
    * Is Go a OOP (Object Oriented Programming) language, and why?
    * When should you use and not dynamic array args?
    * Assert or not Assert during testing? [Testing in Golfing](https://medium.com/@thejasbabu/testing-in-golang-c378b351002d)
- What is the difference and use cases for WebSocket, http/2 SSE and [gRPC](https://grpc.io/)
    * [Will WebSocket survive HTTP/2?](https://www.infoq.com/articles/websocket-and-http2-coexist)
- What would be criteria for choosing Messaging, In-Memory solution in your project?
    * [Kafka vs. Redis: Log Aggregation Capabilities and Performance](https://logz.io/blog/kafka-vs-redis/)
- What’s your level of confidence with SQL, JSON, Stored Procedures in Postgres?
- How indexes works (BTree, GIN/GIST).
- When should you use popular DevOps tools and why? Ex. CI, Docker, Etcd, Kubernetes
- How would you handle security in Go?
    * Check [Top 10 2017-Top 10 - OWASP](https://www.owasp.org/index.php/Top_10_2017-Top_10) if not sure
- Who is the most impressive person in Go community?

### Must Read
* https://github.com/quii/learn-go-with-tests
* https://blog.golang.org/ 
* https://github.com/hoanhan101/ultimate-go
* https://github.com/Alikhll/golang-developer-roadmap
* https://github.com/ardanlabs/gotraining/blob/master/topics/go/README.md#design-guidelines
* http://sijinjoseph.com/programmer-competency-matrix/
* RFD 106 Engineering Guide - Go Best Practices https://github.com/joyent/rfd/blob/master/rfd/0106/README.adoc
* !!!! Security https://github.com/guardrailsio/awesome-golang-security 

#### People
* Rob Pike Twitter: [@rob_pike](https://twitter.com/rob_pike) [github.com/robpike](https://github.com/robpike)
* Russ Cox Twitter: [@_rsc](https://twitter.com/_rsc) [github.com/rsc](https://github.com/rsc)
* Dave Cheney Blog: https://dave.cheney.net/ [@davecheney](https://twitter.comdavecheney) [github.com/davecheney](https://github.com/davecheney)
* [Подкаст GolangShow](https://golangshow.com/)
* https://golangnews.com

#### Communities
- https://www.ardanlabs.com/ 
- https://golangweekly.com/issues
- https://golangnews.com/
- https://github.com/trending/go?since=monthly
- https://www.reddit.com/r/golang/
- https://github.com/avelino/awesome-go


## Submitting a patch in Go

  1. It's generally best to start by opening a new issue describing the bug or
     feature you're intending to fix.  Even if you think it's relatively minor,
     it's helpful to know what people are working on.  Mention in the initial
     issue that you are planning to work on that bug or feature so that it can
     be assigned to you.

  2. Follow the normal process of [forking][] the project, and setup a new
     branch to work in.  It's important that each group of changes be done in
     separate branches in order to ensure that a pull request only includes the
     commits related to that bug or feature.

  3. Go makes it very simple to ensure properly formatted code, so always run
     `go fmt` on your code before committing it.

  4. Any significant changes should almost always be accompanied by tests.  The
     project already has good test coverage, so look at some of the existing
     tests if you're unsure how to go about it.

  5. Do your best to have [well-formed commit messages][] for each change.
     This provides consistency throughout the project, and ensures that commit
     messages are able to be formatted properly by various git tools.

  6. Finally, push the commits to your fork and submit a [pull request][].

[forking]: https://help.github.com/articles/fork-a-repo
[well-formed commit messages]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
[squash]: http://git-scm.com/book/en/Git-Tools-Rewriting-History#Squashing-Commits
[pull request]: https://help.github.com/articles/creating-a-pull-request
