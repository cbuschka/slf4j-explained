# slf4j artifacts explained

## In short

### REQUIRED: [slf4j-api](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-api)
This is the api you use for log statements within your app.

### CHOOSE ONE _AND ONLY ONE_: Logging backend
* [logback-classic](https://search.maven.org/search?q=g:ch.qos.logback%20a:logback-classic) - logback is a logging framework that natively implements slf4j
* [slf4j-log4j12](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-log4j12) - make slf4j log over log4j12, requires log4j in the classpath
* [slf4j-simple](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-simple) - adds a very basic slf4j logger
* [slf4j-nop](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-nop) - makes slf4j to suppress all log messages
* [slf4j-jcl](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-jcl) - let slf4j log to java commons logging
* [slf4j-jdk14](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-jdk14) - let slf4j log over java.util.logging

### OPTIONAL: Bridges - adapt old code
* [jul-to-slf4j](https://search.maven.org/search?q=g:org.slf4j%20a:jul-to-slf4j) - redirect java.util.logging calls to slf4j
* [jcl-over-slf4j](https://search.maven.org/search?q=g:org.slf4j%20a:jcl-over-slf4j) - redirect java commons logging calls to slf4j
* [log4j-over-slf4j](https://search.maven.org/search?q=g:org.slf4j%20a:log4j-over-slf4j) - redirect log4j calls to slf4j

### DONTS: Circular logging setup
* NEVER [log4j-over-slf4j](https://search.maven.org/search?q=g:org.slf4j%20a:log4j-over-slf4j) -> [slf4j-api](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-api) -> [slf4j-log4j12](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-log4j12)
* NEVER [jcl-over-slf4j](https://search.maven.org/search?q=g:org.slf4j%20a:jcl-over-slf4j) -> [slf4j-api](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-api) -> [slf4j-jcl](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-jcl) 
* NEVER [jul-to-slf4j](https://search.maven.org/search?q=g:org.slf4j%20a:jul-to-slf4j) -> [slf4j-api](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-api) -> [slf4j-jdk14](https://search.maven.org/search?q=g:org.slf4j%20a:slf4j-jdk14)

## References
* [slf4j bridge doc](https://www.slf4j.org/legacy.html)