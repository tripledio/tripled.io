# TripleD Blog
This repository contains the sources for the TripleD blog.


###Use jekyll with docker

>*docker run -it -v `pwd`:/srv/jekyll  -p 4000:4000 jekyll/jekyll /bin/bash*

### Start server
>*jekyll serve*

Go to localhost:4000 in browser.
All changes made to source repository will trigger site regeneration and be immediately visible.

### Run server with drafts

>*jekyll serve --drafts*

This will let jekyll serve with the drafts included as posts