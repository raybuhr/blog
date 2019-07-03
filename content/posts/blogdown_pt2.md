+++
title =  "Blogdown (Part 2)"
date = 2019-07-02T21:55:00-05:00
tags = []
featured_image = ""
description = "Why I ditched Blogdown in favor of Hugo"
+++

I built this blog using R and the packages `rmarkdown` and `blogdown` a little over two years ago. 
I haven't been very good about updating it since. 
A big reason why is that it was really annoying using `blogdown`!
I really liked the idea of keeping everything in R.
I still think `rmarkdown` is fantastic and still plan to use it,
but I ditched the `blogdown` package and am using the command 
line static site generator `hugo` that `blogdown` called for me directly instead.

**What was wrong with `blogdown`?**

For starters, a big reason I wanted to use that package was it was 
built on top of `hugo`, which is a really fast, easy to use, and open source tool to build static websites like a blog.
A major selling point of `hugo` is that it renders plain markdown
into templated html using themes that can be swapped out in seconds.
Another major selling point for me was that `hugo` does not re-render
a markdown file if it hasn't changed. I imagined writing some analysis
in `rmarkdown` once and `blogdown` automatically knowing not to knit 
and build it again thanks to `hugo`. That's not what happened, though.

Instead, `blogdown` outputs to `html_document` by default (just like the other popular package based on this tooling, `bookdown`). 
The `blogdown` package has a great [online book](https://bookdown.org/yihui/blogdown/output-format.html) for how to use it, 
having this to say,

>Of course, the output format for websites should be HTML.

Well, actually... if you change that to out `md_document` instead,
that allows `hugo` to take over rendering the content to html and 
not re-rendering if nothing changed. Keeping the default `html_document`
actually causes each blog post to have to be ran and knit everytime you
update your blog, which is super annoying and unnecessary! I'm sure
the package authors had good intentions there, but I think it was the wrong default to choose.

**So why can't you just change the output format?**

Great question! You can, on every single new blog post. Which is not
a big deal, though a tad tedious. However, I realized that what blogdown
was actually giving me was only a wrapper to the `hugo` command line.
I can see why that might seem less scary to some people, but I don't 
think it ended up providing any advantages at all. Instead, if I want 
to use `rmarkdown` for a post, I write a post as a `.Rmd` and render 
to `.md`, then let `hugo` do all the complex markdown to html 
rendering. This is actually much faster than `blogdown` and doesn't 
need to do any work at all if the `.md` file didn't change. 

**Is that it?**

Actually, not quite. The last thing I really wanted to fix is not having
a separate repository for the code to create the blog website, and the
rendered html that gets deployed by GitHub pages. I knew that GitHub 
pages give you some options here -- either from `master` branch, from `gh-pages` branch, or from the `docs/` directory on `master` branch.
I figured out how to change the default directory that `hugo` renders
to by simply adding `publishDir = "docs"` to my site `config.toml` 
file. However, when using GitHubs default user page trick -- i.e. name
the repository `<your-gh-name>.github.io` -- you can only deploy to 
`master` branch at the top level. I ended up deciding to run my blog 
off a different repo, `blog` and deploy from the `docs/` directory.
So the new URL to my blog is [https://raybuhr.github.io/blog/]([https://raybuhr.github.io/blog/).

**My new workflow**

<ol>
<li>Go to a single repo, <code>blog</code></li> 
<li>Create a new a blog post file in <code>content/posts/</code> using either markdown or <code>rmarkdown</code> rendered to markdown with 

{{< highlight r >}}
rmarkdown::render('new-post.Rmd', output_format='md_document')
{{< / highlight >}}
</li>
<li>render my new content to html by running the single command <code>hugo</code></li>

<li>run the local server with <code>hugo server</code> to preview my changes</li>

<li>make any edits necessary</li>

<li>commit my changes and push to GitHub</li>
</ol>




This might not seem like a big difference, but I can now cut out a few
important steps:

- copying the rendered html to a different repo and pushing that to GitHub
- making sure I have all the R packages installed from my old posts (because `blogdown` will always try to re-render them)

**In Conclusion**

Don't be afraid of command line tools. They are often easier and faster
to use that packages in other programming languages that try to wrap 
them up. In addition, don't always assume that incredibly smart people
who have a history of making excellent software packages made the best
choice for _your needs_. Only you can really decide that. Try to keep
in my your goals and be ok with trusting your gut instead of relying 
on the experts.
