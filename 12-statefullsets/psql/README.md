# StatefulSets

```s
$ kubectl exec -it pgstateful-0  /bin/bash
root@pgstateful-0:/# psql -U user -d pgdb
pgdb=#
```

```sql
CREATE TABLE users (name VARCHAR (100));
INSERT INTO users values ('pg-0');
INSERT INTO users values ('pg-1');
SELECT * FROM users;
```

https://man7.org/linux/man-pages/man7/capabilities.7.html
