# josephbleroy-website

This is the repository for the [my personal] website. I'm using [Hugo], a static site generator written in [Go].

### Deployment

Right now I'm deploying directly to my production server using rsync:

```
rsync -a public username@server:/var/www/josephbleroy.com/html
```

### To Do

1. Implement [CircleCI] to send to staging server (local-->github-->master branch-->circleci-->staging server).
2. Setup a script to rsync between staging server and production server.

[my personal]: https://www.josephbleroy.com
[CircleCI]: https://circleci.com
[Hugo]: https://www.gohugo.io
[Go]: https://golang.org
