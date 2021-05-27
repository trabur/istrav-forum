AAGHC.COM
========

```bash
# development
<<<<<<< HEAD
$ npm run dev
=======
export PORT=5000; npm run dev
>>>>>>> 4cc8e6a7badeffa73fb1829957aaa9bbd04264aa
```

```bash
npm install
npm run build
npm start
```

```bash
git push
git tag
git tag v0.6
git push --tags
git push --delete origin v0.6
```

# git submodules used
```fish
$ git submodule add https://github.com/trabur/istrav-headless farmerless

$ cd farmerless
$ npm install
```

# pull latest git changes
```fish
$ git submodule update --init --recursive && git submodule foreach --recursive git fetch && git submodule foreach git merge origin master
```