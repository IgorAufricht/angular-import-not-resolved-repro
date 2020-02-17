# Problem reproduction

This is a reproduction repo for a "Appears in the NgModule.imports of AppModule, but could not be resolved to an NgModule class" problem, which shows when using `npm link` (such as when using lerna). Linked Angular issue: [#35447](https://github.com/angular/angular/issues/35447)

## Steps to reproduce
* checkout the repo
* `npm install`
* `ng build lib1 --prod && ng build --prod` (builds correctly)
* `cd projects/lib1 && npm link && cd ../.. && npm link lib1`
* `ng build lib1 --prod && ng build --prod` (fails)

## Creation of the repo
These are the steps used to create this repo:
* `ng new import-not-resolved-repro`
* `cd import-not-resolved-repro`
* `ng generate library lib1`
* modify `src/app/app.module.ts` to load `Lib1Module` from `lib1`
