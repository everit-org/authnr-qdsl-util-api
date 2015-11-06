# authnr-qdsl-util-api

Utility API to create the permission checks easly for Querydsl based SQL 
queries. This API is an extension of the [authorization-qdsl-util-api][1]. The 
difference is that there is no authorizedResourceId  in the parameter list of 
the ```AuthnrQdslUtil.authorizationPredicate()``` method, it must be provided 
by the implementation.

## Example usage

```
QBook book = QBook.book;
BooleanExpression authrPredicate = 
    authnrQdslUtil.authorizationPredicate(book.resourceId, "read", "edit");

SQLQuery query = new SQLQuery(connection, configuration);

return query.select(...)...from(book)...where(authrPredicate)...fetch();
```

For more information check the javadoc of the 
__org.everit.authnr.qdsl.util.AuthnrQdslUtil__ interface.

[![Analytics](https://ga-beacon.appspot.com/UA-15041869-4/everit-org/authnr-qdsl-util-api)](https://github.com/igrigorik/ga-beacon) 

[1]: https://github.com/everit-org/authorization-qdsl-util-api
