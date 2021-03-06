# Neocons, a Clojure client for the Neo4J REST API

Neocons is a feature rich idiomatic [Clojure client for the Neo4J REST API](http://clojureneo4j.info).


## Supported Features

Neocons currently supports the following features (all via REST API, so [you can use open source Neo4J Server edition for commercial projects](http://neo4j.org/licensing-guide/)):

 * Create, read, update and delete nodes
 * Create, read, update and delete relationships
 * Fetch relationships for given node
 * Create and delete indexes
 * Index nodes
 * Query node indexes for exact matches and using full text search queries
 * Query automatic node index
 * Traverse nodes, relationships and paths
 * Find shortest path or all paths between nodes
 * Predicates over paths, for example, if they include specific nodes/relationships
 * [Cypher queries](http://docs.neo4j.org/chunked/stable/cypher-query-lang.html)
 * Basic HTTP authentication, including [Heroku Neo4J add-on](https://devcenter.heroku.com/articles/neo4j) compatibility
 * Efficient multi-get via [Cypher queries](http://docs.neo4j.org/chunked/stable/cypher-query-lang.html)
 * Convenience functions for working with relationships and paths
 * Neo4J 2.0 [transactions](http://docs.neo4j.org/chunked/milestone/rest-api-transactional.html)
 * Neo4J 2.0 [labels](http://docs.neo4j.org/chunked/milestone/rest-api-node-labels.html)
 * Neo4J 2.0 [constraints](http://docs.neo4j.org/chunked/milestone/rest-api-schema-constraints.html)


## Documentation & Examples

To get started and see what using Neocons feels like, please use our [Getting started with Clojure and Neo4J Server](http://clojureneo4j.info/articles/getting_started.html) guide.

[Documentation guides](http://clojureneo4j.info) are mostly complete.
For more examples, see our [test suite](test).


## Community

[Neocons has a mailing list](https://groups.google.com/group/clojure-neo4j). Feel free to join it and ask any questions you may have.

To subscribe for announcements of releases, important changes and so on, please follow [@ClojureWerkz](https://twitter.com/#!/clojurewerkz) on Twitter.


## Project Maturity

Neocons is not a young project: as of October 2013, it is about 2
years old, with active production use from week 1. It is now moving
towards `2.0` release. Nearly API parts are set in stone and most
documentation guides in good shape.



## Maven Artifacts

### The Most Recent Release

Neocons artifacts are [released to Clojars](https://clojars.org/clojurewerkz/neocons). If you are using Maven, add the following repository
definition to your `pom.xml`:

``` xml
<repository>
  <id>clojars.org</id>
  <url>http://clojars.org/repo</url>
</repository>
```

### The Most Recent Stable Release

With Leiningen:

    [clojurewerkz/neocons "2.0.0-beta3"]

With Maven:

    <dependency>
      <groupId>clojurewerkz</groupId>
      <artifactId>neocons</artifactId>
      <version>2.0.0-beta3</version>
    </dependency>



## Continuous Integration

[![Continuous Integration status](https://secure.travis-ci.org/michaelklishin/neocons.png)](http://travis-ci.org/michaelklishin/neocons)


CI is hosted by [travis-ci.org](http://travis-ci.org)


## Supported Clojure versions

Neocons requires Clojure 1.4+.
The most recent stable Clojure release is highly recommended.


## Supported Neo4J Server versions

### Neocons 2.0 (master)

Neocons `2.0` tracks Neo4J Server 2.0 changes, although currently
the test suite also passes against 1.9.x.

There are incompatible changes in 1.9 and 2.0 in mutating Cypher
syntax, so Neo4j Server 1.8 compatibility is less than perfect.

### Neocons 1.1

Neocons `1.1` supports Neo4J Server 1.5.0 and later versions. For the
[Cypher query
language](http://docs.neo4j.org/chunked/stable/cypher-query-lang.html)
support, 1.6 is the minimum recommended versions because Cypher is
supported by the REST API directly without any plugins. Some features
(in Cypher in particular) may be specific to a later version. We
recommend using the most recent stable release. Neocons is actively
tested against bleeding edge Neo4J Server snapshots and we try to
support important new features before stable server releases come out.

If you use OpsCode Chef, there is a [Neo4J Server Chef cookbook](https://github.com/michaelklishin/neo4j-server-chef-cookbook).


## Neocons Is a ClojureWerkz Project

Neocons is part of the [group of libraries known as ClojureWerkz](http://clojurewerkz.org), together with
[Monger](https://github.com/michaelklishin/monger), [Langohr](https://github.com/michaelklishin/langohr), [Welle](https://github.com/michaelklishin/welle), [Quartzite](https://github.com/michaelklishin/quartzite), [Validateur](https://github.com/michaelklishin/validateur) and several others.


## Development

Neocons uses [Leiningen 2](https://github.com/technomancy/leiningen/blob/master/doc/TUTORIAL.md). Make sure you have it installed and then run tests against
all supported Clojure versions using

    lein2 all test

Then create a branch and make your changes on it. Once you are done with your changes and all tests pass, submit
a pull request on Github.


## License

Copyright (C) 2011-2013 Michael S. Klishin, Alex Petrov

Double licensed under the [Eclipse Public License](http://www.eclipse.org/legal/epl-v10.html) (the same as Clojure) or
the [Apache Public License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html).


## FAQ

### Will embedding be supported in the future?

Because Neo4J is GPL software, linking against it will require your project to be open source. While there are
perfectly valid use cases for this, Neocons was developed to be used in commercial projects and Neocons
authors strongly prefer business-friendly licenses and Clojure community commitment to the Eclipse Public License v1.

Neocons namespace structure leave the door open for future Neo4J Server features like the binary protocol but it
is highly unlikely that it will ever cover embedding, should Neo4J license stay GPL forever.

If you need a solid well-maintained EPLv1-licensed embeddable graph database for Clojure 1.3.0 and later, please
take a look at [Titanium](http://titanium.clojurewerkz.org) and [Jiraph](https://github.com/flatland/jiraph).
