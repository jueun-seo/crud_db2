```
uv add "fastapi[standard]" sqlalchemy "psycopg[binary]"
```

## ORM vs SQL

- read

```
db.scalars(select(Post)).all()
=> SELECT * FROM posts

db.get(Post, 1)
=> SELECT * FROM posts WHERE id = 1;
```

- create

```
post = Post(title='hihi', content='hihihi')
db.add(post)
db.commit()

=> INSERT INTO posts (title, content) VALUES (hihi, hihihi);
```

- update

```
post.title = 'hello'
db.commit()
```

- delete

```
db.delete(post)
db.commit()
```