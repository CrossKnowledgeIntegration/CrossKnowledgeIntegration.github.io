# Integration @ CrossKnowledge knowledge base

You can access this site here:

[https://crossknowledgeintegration.github.io](https://crossknowledgeintegration.github.io/index.html)

If you need to run this website locally (development), you can run this command in your terminal (Docker is required). You can change the mapped port to your need (in this example, http://localhost:8080):

```bash
docker run -p 8080:4000 --rm --volume="$PWD:/srv/jekyll" --volume="$PWD/vendor/bundle:/usr/local/bundle" -e JEKYLL_ENV="development" -it jekyll/jekyll:3.8 jekyll serve
```

Thanks to:

* [Template used](http://idratherbewriting.com/documentation-theme-jekyll/index.html)
* Contributors


The integration team!