# Unit testing in Ionic3 with Karma and Jasmine
This is basically an addendum to [Josh Morony's article](https://www.joshmorony.com/introduction-to-testing-ionic-2-applications-with-testbed/) with minor updates for Ionic 3 (4/2/18). It is my intention that this repo fulfill the same purpose as Ionic's 'blank' app with karma already set up.

yarn:  
`yarn add global karma-cli`

```
yarn add @angular/cli codecov jasmine-core jasmine-spec-reporter karma karma-chrome-launcher karma-jasmine karma-mocha-reporter karma-remap-istanbul ts-node tslint tslint-eslint-rules @types/jasmine @types/node --dev
```
**NOTE** the following instructions can also be done with [yarn](https://yarnpkg.com/en/) if you have it installed. Only npm directions will follow. I'm leaving in the above because its a faster install.

npm (same as the article with updated @angular/cli):  

```
npm install -g karma-cli
npm install @angular/cli --save-dev
npm install codecov --save-dev
npm install jasmine-core --save-dev
npm install jasmine-spec-reporter --save-dev
npm install karma --save-dev
npm install karma-chrome-launcher --save-dev
npm install karma-jasmine --save-dev
npm install karma-mocha-reporter --save-dev
npm install karma-remap-istanbul --save-dev
npm install ts-node --save-dev
npm install tslint --save-dev
npm install tslint-eslint-rules --save-dev
npm install @types/jasmine --save-dev
npm install @types/node --save-dev
```

Then replace zone.js dependency in package.json with this line:  

`"zone.js": "git://github.com/JiaLiPassion/zone.js#jasmine-dist"`  

then run  

`npm install`

**NOTE** this is a temporary fix and may not be needed anymore. See [this thread](https://github.com/angular/zone.js/issues/1035) for more info.  


Now run `karma init`, select the defaults, and replace the newly created `karma.conf.js` file with the one in this repo.

The rest of the files in the article should be fine the way they are, but feel free to grab them from this repo:

**NOTE** `/angular-cli.json` stays the same. Don't change its name unless you change the reference to it in karma.conf.js under `angularCli:config:`.  

```
/angular-cli.json
/src/environments/*
/src/mocks.ts
/src/polyfills.ts
/src/test.ts
/src/tsconfig.test.json
```

Finally, add `"test": "ng test"` under `scripts:` in `package.json`. Drop a .spec.ts file somewhere in the src dir and `npm test`

Happy Testing :scorpion: