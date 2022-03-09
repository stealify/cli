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

## Implement the idea of rollup-config adjustments
https://github.com/rollup/rollup-init

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


## Roadmap
- [] - Typescript Server needs to run on GraalJS
- [] - Rollup needs to run on GraalJs
- [] - pnpm needs to run on GraalJs
- [] - nodejs gradle parser based on acorn as kotlin groovy are relativ compatible with ECMAScript
- [] - Apply Quarkus ES4X Concepts with the node_modules/.bin hack bin never gets cleaned up! in normal situations so we can store class files there which would indicate that we want that dependencies and that works because we use node resolve to do the relativ patching and depend on node_modules but adding a extra es4x_modules would be beneficial
- [] - finish the tooling for the justjs workers concept just jsworkers are more then highly efficent and they are able to get loadbalanced via haproxy with high scalability messured 20x performance of Cloudflares Worker Implementation as we can use systemd socket activation this leads to the most performant worker framework at present prooved by emtech power benchmarks rank!
- [] - stealify vm build compile tooling.
- [] - carlo puppeteer open pwa tooling and running (Installer)
