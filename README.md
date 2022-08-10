# Minimal beanstalk django

Because the docs are found wanting.

```
zip -r ebdjango.zip ./
```

Consider using [Another web service](https://anotherwebservice.com/) instead.

## Things I always do wrong with aws

### 1. I can't `zip` a file and include the .hidden files (which .ebextensions is one of them)

Today I learnt:

```
zip -r foo.zip ./*
```

Will miss/not include .ebextentions (hidden files/folders) 😢.

```
zip -r foo.zip ./
```

Will include hidden files in zip file 😃.

Why does this happen?

Perhaps because linux users are so used to doing "cp ./*" 

### 2. Zipping the wrong folder

Your brain (like mine did) might assume you need to zip the 'parent'
directory of your app. Nope. Zip the *contents* of your app.

### 3. Using zips in the first place.

Don't use zips. Store the app in an object store.
