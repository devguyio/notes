# Stateful Serverless and the Elephant in the room
## Notes
- Speaker is CTO and flink cofounder
- Putting non scalable applications on scalable infrastructure won't make it scalable, we need scalable building blocks
- Scalable computation have (Scalable state, consistent state, secure & observable)
- The requiest/response model from traditional databases is not a great match for this goal
- Influenced by paper: [Life beyond distributed transactions: an Apostate's Opinion - Pat Helland](https://www.ics.uci.edu/~cs223/papers/cidr07p15.pdf)
- Stateful Functions: A project to provide scalable building blocks for building scalable applications
- Being built on existing frameworks (Knative or Lambda)
- Polyglot event-drive functions for distributed stateful applications
- API for building distributed stateful applications: Building block: Functions, Mult-language support, scale to zero
- Consistent state: Functions have access to local state which is persistent and integrated with messaging
- Out-of-box exactly once-state access/updates & messages
- Think of it as a transactionally consistent actor system.
- Built using snapshots not a database. Uses Flink's distributed snapshots model.
- Runtime deployment looks as : Events ingress + Flink StateFun Cluster + Functions + event egress -> can be deployed anywhere
- Compared to traditional database applications, the dependency is inversed , where the database calls the application 

## Personal Impression:
- IMHO the current hype of stateful functions is yet another validation for the importance of the actor model.
- I feel that Knative will have to cater to the stateful functions runtime needs at some point.
- Interested to see the future of "topologies" and "functions relationships and hierarchies" similar to Akka actors
- I'm still not sure what consitutes a winning stateful funciton framewrok, but this one has some key winning features for sure
in comparison to what is here in mind
- I'll keep an eye on this one. It looks really promising.
