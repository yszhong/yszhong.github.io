---
layout: post
title: "Summary of Researches in Tongji"
description: "Summary of Researches in Tongji"
categories: [research]
tags: [research, data_mining]
redirect_from:
  - /2017/11/15/
---

* Kramdown table of contents
{:toc .toc}

This is a summary of my researches during master life in School of Software Engineering, Tonji University.

# Network Traffic Anomaly Detection

We applied several kinds of algorithms on detecting the anomalous IPs from the network traffic. 

## Propagation Based Detection

Here is the [source code](https://github.com/yszhong/AnomalyDetection "code") of this part. Basic idea is provided by my fellow Shupei Wang[^2].

## Email Anomaly Detection

We also find the email contact of Hacking Team. [Here](http://chinavis.org/2016/challenge.html "data") is the dataset.

We plotted the picture below.

![bassi](https://github.com/yszhong/yszhong.github.io/raw/master/_posts/pic/bassi.jpg "bassi")

# Predict Stock Market Indices

We predicted Dow Jones Industrial Average with the news selected from [Reddit](https://www.reddit.com/ "reddit"). 

Our idea is described below. 

{% highlight python %}
for time in all_time:
	first[p] = RandomForestRegression(series[time-p, time])
	topic_distribution = dynamicLDA(documents[time])
	second = RandomForestRegression(topic_distribution)
for time in all_time:
	predict[p] = AutoRegressiveExogenous(first,second)
{% endhighlight %}

The result is shown below. 

![series](https://github.com/yszhong/yszhong.github.io/raw/master/_posts/pic/series.jpg "series")

We submitted a paper in this topic[^1], and Our codes can be seen [here](https://github.com/yszhong/SeriesTopic "code"). My graduate paper is also about this. 

[^1]: Y. Zhong, Q. Zhao, W. Rao, Predicting stock market indexes with world news, *International Conference on Systems and Informatics*, 2017

[^2]: Shi Y., Wang S., Zhao Q., Li J. (2017) A Hybrid Approach of HTTP Anomaly Detection. In: Song S., Renz M., Moon YS. (eds) Web and Big Data. APWeb-WAIM 2017. Lecture Notes in Computer Science, vol 10612. Springer, Cham
