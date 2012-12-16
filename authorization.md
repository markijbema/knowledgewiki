It's a good thing to centralize authorization logic. Otherwise you will endup with

```
  if user.admin? or content.created_by == user
```

And if you want to change that other users can access the content as well, you suddenly have to change it all over the place.

There are a few gems which make it easy to do this. One is CanCan, which is great, and gives easy to use code (using a DSL). Disadvantage is that for each request you need to load all permissions.

A simpler, cleaner framework is Pundit. It uses plain ruby objects, and only does checks, needing no large initialisation.
https://github.com/elabs/pundit
