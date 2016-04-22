GHTest1
=======

### Bad behaviour
To demonstrate a failure of npm to run script when the folder containing the project is badly name, do the following:

```
git clone git@github.com:NicolasPelletier/GHTest1.git GH%2FTest1
cd GH%2FTest1
npm install
npm test
```

If you execute the commands above, you will see npm returning an error, such as the following:
```
$ npm test

> GHTest1@1.0.0 test /tmp/GH%2FTest1
> eslint .

sh: 1: eslint: not found
npm ERR! Test failed.  See above for more details.
```



### Control behaviour
If you execute the following commands and use a boring folder name, it works.


```
git clone git@github.com:NicolasPelletier/GHTest1.git
cd GHTest1
npm install
npm test
```

In this case you get something like this:
```
$ npm test

> GHTest1@1.0.0 test /tmp/GHTest1
> eslint .

$
```
