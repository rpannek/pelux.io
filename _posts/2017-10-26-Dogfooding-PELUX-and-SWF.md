---
layout: post
title:  "Dogfooding PELUX and Software Factory"
date:   2017-10-26 15:48:00 +0200
author: Richard Pannek
---

PELUX and the Software Factory are quite ambitious projects. One is a yocto base platform for other automotive projects and the other is a set of best practices, howtos and processes which serves as a starting point for bigger projects. So how does [Pelagicore](http://www.pelagicore.com/) know that this way of working actually works well?

For many years [Pelagicore](http://www.pelagicore.com/), which now is part of [Luxoft](https://www.luxoft.com/), has been helping big automotive OEM's and Tier 1's to kickstart prove of concepts and production projects. We have seen what works and what absolutelly doesn't. For some time we've been trying to write down our findings in a structured way, so that this information can be reused by our colegues, customers and everyone else who could benefit from this.

This is why we are developing both projects in the open, on GitHub.

But this is not the main reason why we think this works well, the main reason is that we use both projects internally together with our customers as basis for PoCs and bigger, more advanced projects. By doing so we constantly refine the documentation and our Yocto platform.

## PELUX

## Software Factory

Basically how this works is that we use the [Software Factory Blueprint](https://github.com/pelagicore/software-factory-blueprint) as kind of a library for articles which are not project specific.

One example would be a how-to install Jenkins, we have done it in a couple of different ways during the years. After some time a good way of how to do this emerged so we wrote a how to about it and put it into the [SWF Blueprint](https://github.com/Pelagicore/software-factory-blueprint/blob/master/docs/articles/infrastructure/ci-cd/jenkins.rst). Now that article can be used in project specific deployment of the Software Factory. The PELUX Software Factory is one of those project specific deployments which also happens to be a open source project and it uses the blueprint as a git submodule and pulls the articles which it needs to it's own SWF. The result can be seen here: [pelux.io CI Jenkins](http://pelux.io/software-factory/swf-blueprint/docs/articles/infrastructure/ci-cd/jenkins.html).

We have such a deployment which reuses the open source blueprint articles for many of our internal and customer projects. This way other people have used the documentation and reported bugs, or even upstreamed refinements. It is also a really nice way of streamlining how we work in different projects. For our customers the biggest benefit is that they can, with our help, kickstart a project and have a lot of documentation already in place from day one which they can extend with project specific articles.
