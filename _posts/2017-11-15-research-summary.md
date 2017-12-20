---
layout: post
title: "Summary of Researches on iData Lab"
description: "researches in Tongji University"
categories: [research]
tags: [research, data_mining]
redirect_from:
  - /2017/11/15/
---

* Kramdown table of contents
{:toc .toc}

This is a summary of my researches during master life in iData Laboratory, School of Software Engineering, Tongji University.

# Network Traffic Anomaly Detection

We applied several kinds of algorithms on detecting the anomalous IPs from the network traffic. 

## Propagation Based Detection

Here is the [source code](https://github.com/yszhong/AnomalyDetection "code") of this part. Basic idea is provided by one of my fellow students *Shupei Wang*[^2]. I refined some of the iteration rules according to the shape of data.

## Clustering

Another fellow _Yudi Tang_ did some clusterings with our data [[source code](https://github.com/tangyudi/Clustering "code")], while I applied affinity propagation clustering to the data after the preprocessing offered by Tang. 

## Email Anomaly Detection

We also find the email contact of Hacking Team. [Here](http://chinavis.org/2016/challenge.html "data") is the dataset. Our purpose is to find the email users who act anomalously.

We generated the graph below.

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

![series](https://github.com/yszhong/yszhong.github.io/raw/master/_posts/pic/series.jpg "series"){:height="50%" width="50%"}

We submitted a paper in this topic[^1], and Our codes can be seen [here](https://github.com/yszhong/SeriesTopic "code"). My graduate paper is also about this. 

[^1]: Yunsong Zhong, Qinpei Zhao, Weixiong Rao, Predicting stock market indexes with world news, *International Conference on Systems and Informatics*, 2017

[^2]: Shi Y., Wang S., Zhao Q., Li J. (2017) A Hybrid Approach of HTTP Anomaly Detection. In: Song S., Renz M., Moon YS. (eds) Web and Big Data. APWeb-WAIM 2017. Lecture Notes in Computer Science, vol 10612. Springer, Cham
