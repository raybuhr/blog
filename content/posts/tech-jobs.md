---
title: "Are Tech Jobs Really Down This Year?"
date: 2016-07-14
draft: false
---

A few weeks ago, one of my fellow MIDS colleagues shared this article,
*[Tech job postings are down 40% and nobody’s talking about
it.](https://medium.com/@cameronmoll/tech-hiring-is-down-40-and-nobodys-talking-about-it-3d6f658d9faf#.tsoc36d6g)*
As a data skeptic, I wondered if it was true.

<br>

![](https://cdn-images-1.medium.com/max/800/1*ptKtTWdeh0XfGPrWsrPt0A.png)

<br>

Surely, this source had insight that I didn’t and maybe it was skewed to
the job markets that company operates in, but I have really only seen
more and more growth of tech jobs here in Chicago. Albeit, that was my
feeling from receiving daily alerts to my email… which meant I was
sitting on a pile of data I could use to test that hypothesis!

Using a python CLI tool called
[Got-Your-Back](https://github.com/jay0lee/got-your-back/wiki) I was
able to download messages based on search and store them in a local
SQLite database. Keep in mind this is a pretty limited sample as I was
only signed up for “python” or “Data Scientist” job searches in the
Chicago area. Also job descriptions posted don’t always get tagged
correctly, but at least I have 2 years of data…

Turns out my data was pretty messy due to alerts not going through for
almost two months and minimal postings on the weekends. I tried
summarizing on a weekly basis in order to smooth out some of the noise,
but as you can see below there is still missing data and large outliers.

<br>

### Job Posts to Indeed.com for searches matching Data Scientist or python by Week

<!--html_preserve-->

<script type="application/json" data-for="htmlwidget-581dc5e15d66ef9585b2">{"x":{"attrs":{"axes":{"x":{"pixelsPerLabel":60,"drawGrid":false},"y":{"drawGrid":false}},"labels":["week","Data Scientist","python"],"legend":"auto","retainDateWindow":false,"showRangeSelector":true,"rangeSelectorHeight":40,"rangeSelectorPlotFillColor":" #A7B1C4","rangeSelectorPlotStrokeColor":"#808FAB","interactionModel":"Dygraph.Interaction.defaultModel"},"scale":"weekly","annotations":[],"shadings":[],"events":[],"format":"date","data":[["2014-06-04T00:00:00.000Z","2014-06-11T00:00:00.000Z","2014-06-18T00:00:00.000Z","2014-06-25T00:00:00.000Z","2014-07-02T00:00:00.000Z","2014-07-09T00:00:00.000Z","2014-07-16T00:00:00.000Z","2014-07-23T00:00:00.000Z","2014-07-30T00:00:00.000Z","2014-08-06T00:00:00.000Z","2014-08-13T00:00:00.000Z","2014-08-20T00:00:00.000Z","2014-08-27T00:00:00.000Z","2014-09-03T00:00:00.000Z","2014-09-10T00:00:00.000Z","2014-09-17T00:00:00.000Z","2014-09-24T00:00:00.000Z","2014-09-27T00:00:00.000Z","2014-10-01T00:00:00.000Z","2014-10-08T00:00:00.000Z","2014-10-15T00:00:00.000Z","2014-10-22T00:00:00.000Z","2014-10-29T00:00:00.000Z","2014-11-05T00:00:00.000Z","2014-11-12T00:00:00.000Z","2014-11-19T00:00:00.000Z","2014-11-26T00:00:00.000Z","2014-12-03T00:00:00.000Z","2014-12-10T00:00:00.000Z","2014-12-17T00:00:00.000Z","2014-12-24T00:00:00.000Z","2014-12-31T00:00:00.000Z","2015-01-01T00:00:00.000Z","2015-01-08T00:00:00.000Z","2015-01-15T00:00:00.000Z","2015-01-22T00:00:00.000Z","2015-01-29T00:00:00.000Z","2015-02-05T00:00:00.000Z","2015-02-12T00:00:00.000Z","2015-02-19T00:00:00.000Z","2015-02-26T00:00:00.000Z","2015-03-05T00:00:00.000Z","2015-03-12T00:00:00.000Z","2015-03-19T00:00:00.000Z","2015-03-26T00:00:00.000Z","2015-04-02T00:00:00.000Z","2015-04-09T00:00:00.000Z","2015-04-10T00:00:00.000Z","2015-04-16T00:00:00.000Z","2015-04-23T00:00:00.000Z","2015-04-30T00:00:00.000Z","2015-05-07T00:00:00.000Z","2015-05-14T00:00:00.000Z","2015-05-21T00:00:00.000Z","2015-05-28T00:00:00.000Z","2015-06-04T00:00:00.000Z","2015-06-11T00:00:00.000Z","2015-06-18T00:00:00.000Z","2015-06-19T00:00:00.000Z","2015-06-25T00:00:00.000Z","2015-07-02T00:00:00.000Z","2015-07-09T00:00:00.000Z","2015-07-16T00:00:00.000Z","2015-07-23T00:00:00.000Z","2015-07-30T00:00:00.000Z","2015-08-06T00:00:00.000Z","2015-08-13T00:00:00.000Z","2015-08-20T00:00:00.000Z","2015-08-27T00:00:00.000Z","2015-09-03T00:00:00.000Z","2015-09-10T00:00:00.000Z","2015-09-17T00:00:00.000Z","2015-09-24T00:00:00.000Z","2015-10-01T00:00:00.000Z","2015-10-08T00:00:00.000Z","2015-10-15T00:00:00.000Z","2015-10-22T00:00:00.000Z","2015-10-29T00:00:00.000Z","2015-11-05T00:00:00.000Z","2015-11-12T00:00:00.000Z","2015-11-19T00:00:00.000Z","2015-11-27T00:00:00.000Z","2015-11-28T00:00:00.000Z","2015-12-03T00:00:00.000Z","2015-12-04T00:00:00.000Z","2015-12-10T00:00:00.000Z","2015-12-17T00:00:00.000Z","2015-12-24T00:00:00.000Z","2015-12-25T00:00:00.000Z","2015-12-31T00:00:00.000Z","2016-01-01T00:00:00.000Z","2016-01-08T00:00:00.000Z","2016-01-15T00:00:00.000Z","2016-01-22T00:00:00.000Z","2016-01-29T00:00:00.000Z","2016-02-05T00:00:00.000Z","2016-02-12T00:00:00.000Z","2016-02-13T00:00:00.000Z","2016-02-19T00:00:00.000Z","2016-02-20T00:00:00.000Z","2016-02-26T00:00:00.000Z","2016-03-04T00:00:00.000Z","2016-03-05T00:00:00.000Z","2016-03-12T00:00:00.000Z","2016-03-18T00:00:00.000Z","2016-03-19T00:00:00.000Z","2016-03-25T00:00:00.000Z","2016-04-01T00:00:00.000Z","2016-04-02T00:00:00.000Z","2016-05-28T00:00:00.000Z","2016-06-03T00:00:00.000Z","2016-06-10T00:00:00.000Z","2016-06-17T00:00:00.000Z","2016-06-24T00:00:00.000Z","2016-07-01T00:00:00.000Z","2016-07-08T00:00:00.000Z","2016-07-09T00:00:00.000Z"],[30,16,23,24,36,24,31,18,16,23,24,31,19,22,34,21,24,null,64,34,35,31,28,26,28,20,13,33,35,29,17,5,17,30,38,32,27,29,62,69,62,66,55,72,58,49,54,null,49,28,45,56,29,31,31,56,51,37,null,29,30,50,39,58,49,45,37,61,51,53,57,48,59,55,50,61,66,44,33,52,38,2,null,null,41,59,68,null,6,8,54,25,37,42,52,62,null,54,null,55,37,null,32,32,null,78,66,50,null,28,31,50,60,43,61,48,null],[null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,50,118,107,94,90,82,71,93,129,69,84,118,108,56,10,96,96,114,128,109,106,117,123,136,147,119,125,105,97,null,115,92,97,118,118,140,81,136,137,124,null,100,99,93,142,118,116,159,124,140,120,114,97,137,155,144,135,137,152,129,133,87,153,128,null,94,152,null,87,98,60,null,null,81,113,102,114,110,155,150,null,111,null,108,117,null,66,125,null,139,null,105,58,125,142,127,149,118,null,100]]},"evals":["attrs.interactionModel"],"jsHooks":[]}</script>
<!--/html_preserve-->

<br>

**With a little help from the R language and the [ggplot2
package](http://docs.ggplot2.org/current/) we can see the trends a bit
more clearly.**

<br>

### Weekly Trends in Job posts Indeed.com for Data Scientist and python

    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'
    ## `geom_smooth()` using method = 'loess' and formula 'y ~ x'

![](tech-jobs_files/figure-markdown_strict/unnamed-chunk-2-1.png)

Sure enough, it does look like jobs for these searchs peaked last
summer, but that said the trend is not downward. If anything, it just
looks like jobs matching *Data Scientist* or *python* have stabilized.

I’m really curious to see what this data shows a few months from now. In
the meantime, I’ve started collect job alerts for other data science
related searchs and different sources as well. I’ll try to update and
repost later this year.
