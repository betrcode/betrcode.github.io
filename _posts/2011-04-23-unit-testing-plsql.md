---
layout: post
title: "Unit testing pl/sql"
tags: [java, oracle, plsql, testing]
---
<!--more-->

## My situation
I currently have an assignment where there is a large PLSQL code base. It's been developed actively for about 12 years and works quite well. I am not saying it's flawless, but quite mature. There's lots of room for improvement and lots of dead code that needs to be removed.

Some of the plsql is called from the Java DAO layer of a front-end web application, but most of it is used for backoffice functionality. The parts that are accessed from the Java layer are tested through integration tests based on JUnit, but the large part that is only used from the backoffice has no unit test coverage.

## Doing something about it
I've known about the utPLSQL framework for many years, but never gotten around to actually use it in a Continuous Integration environment. I decided it was time to do something about it and started by adding the installation of utPLSQL to the already in place automated database reinstallation build. The installation part was quite easy, I just dropped the utPLSQL install scripts into our own source control repository and made it part of our db install. Uninstalling utPLSQL was a bit tricker since it creates public synonyms and those are not dropped when the Oracle db user/schema is dropped. (And that's how we "uninstall" our other schemas normally.) And if I let those public synonyms stay there, I would get errors on the next install. So I simply need to create a small script that dropped those public synonyms as part of the uninstall/install (reinstall :) ) process.

After utPLSQL was part of our db installation, I created a couple of sample utPLSQL tests and tried them out. No problems there. I could run them from the SQL prompt without problem. But what I really wanted was to make them part of the build process in Hudson. So I started writing a JUnit test that would wrap the utPLSQL tests and then it would be runnable from Hudson.

After I while it struck me that I was writing something that someone else had probably written already and after a quick google I found the maven-utplsql-plugin. (insert holy graal sound here) Since we use Maven for the builds, this seemed like a perfect match. However, there were some pitfalls.

## Some pitfalls
The maven-utplsql-plugin is currently not available in any public Maven repository. So, I had to download it and install it add it manually to our local Maven repo. The only problem was that our Maven repo was setup not to accept SNAPSHOT releases, and since we didn't want to change that, I had to HACK the source files in the zip file and replace SNAPSHOT with STABLE in order for our Maven repo to accept the new artifact. In fact, this may lead to that I have to do some contributions to the dev team of the maven-utplsql-plugin to get it up to a RELEASE version and maybe even up on a public repository?

## The happy ending
Finally, I added a new task to our db-reinstall profile in Maven. The new task simply calls the plugin which runs the tests. SUCCESS!

## My sources
Here's the Maven plugin for utplsql: [https://sourceforge.net/projects/utplsql/](https://sourceforge.net/projects/utplsql/)

The utPLSQL project: [https://sourceforge.net/projects/utplsql/](https://sourceforge.net/projects/utplsql/)
