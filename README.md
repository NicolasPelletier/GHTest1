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

But if you execute the following command, it works:
```
$ npm run eslint

> GHTest1@1.0.0 eslint /tmp/GH%2FTest1
> ./node_modules/eslint/bin/eslint.js .

$
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

### Conclusion

When calling the script with the full path, it works. So it seems that when the folder has %2F in its name, npm has trouble resolving the path. It should be able to find the script to run in /node_modules/.bin but it does not.


#### Note: Adding text to see the CLA
