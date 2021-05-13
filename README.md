# Integration @ CrossKnowledge knowledge base

You can access this site here:

[https://crossknowledgeintegration.github.io](https://crossknowledgeintegration.github.io/index.html)

If you need to run this website locally (development), you can run this command in your terminal (Docker is required):
```bash
docker run --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" -e JEKYLL_ENV="development" -it jekyll/jekyll:3.8 jekyll serve
```

If you are under Windows with WSL or WSL2, you need to map a port as well. Then you can access using localhost (in this example, http://localhost:8080):

```bash
docker run -p 8080:4000 --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" -e JEKYLL_ENV="development" -it jekyll/jekyll:3.8 jekyll serve
```

Thanks to:

* [Template used](http://idratherbewriting.com/documentation-theme-jekyll/index.html)
* Contributors


The integration team!