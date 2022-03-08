# cli
A CLI for the stealify tooling inspired by yeoman pnpm donejs 

## Consolidate CLI CLient features and make them more generic
Later we will also daemonize this process but we will use a uniq approach to that we detect if it is running already if it is it will use the running instance
if not get forced to not do so.
- quarkus
  - install 
  - configure build 
  - dev server
- donejs
  - installIfMissing
  - installDoneJSPackages
  - run yeoman generators
  - run npm commands
  - dev server
- rollup
  - installIfMissing
  - dev server
- pnpm
  - run package.json commands
- typescript
  - tsc *
  - dev server
- codecov based on tsc is always 100% 
  - assert calls and tests should be compile able away

## Implement the idea of rollup-generators
Maybe it is more clever to have something that logs what did got choosen on cli settings it is not so clever to not log it to a file
when we would implement something like a config file parser for rollup we could maybe get much better results.

## Implement the idea of a rollup loader
a rollup loader would use the ability of dynamic import to use string based imports we did consider that in the ECMAScript draft already.
- also waiting for import.meta.resolve(moduleId, baseUrl)

## Implement the idea of a rollup test runner 
as rollup as loader also enables again mocking and injection we could also run good tests. 

## Implement rollup + pnpm + typescript + gradle shared daemon
We know about the Heap implementation in nodejs that it will win a lot of speed when we can share the data structure of that 3 projects as all have the same data.
and each part only adds some little more infos i guess that will we the basic ecmascript implementation of the stealify lang eco system.



## Design decisions
- rollup delivers a highly qualifyed plugin system that is able to run workers and get feedback back runs on NodeJS and GraalVM
 - needs pnpm to match up with gradle as ECMAScript Packages are not unified you need rollup to consume them.
- gradle delivers a highly qualifyed plugin system that is able to run workers and get feedback back runs on GraalVM but the DSL syntax can be read by NodeJS without problems via the ECMAScript ast parser as groovy and kotlin DSL are valid ECMAScript!
- typescript can check ecmascript it runs on ECMAScript so GraalVM and NodeJS
