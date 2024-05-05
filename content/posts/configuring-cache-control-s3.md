+++
author = "David Salter"
title = "Configuring Cache Control For S3 Hosted Resources"
date = "2022-01-01"
description = "When doing web development, one of the most important aspects is to get a site performing well with SEO (Search Engine Optimisation). One contributing factor to this (there are many), is effective resource caching. In this article, I’m going to show how to achieve this when resources are stored within a S3 bucket."
tags = [
    "s3",
    "aws",
    "cloud"
]
+++
When doing web development, one of the most important aspects is to get a site performing well with SEO (Search Engine Optimisation). One contributing factor to this (there are many), is effective resource caching. In this article, I’m going to show how to achieve this when resources are stored within a S3 bucket.

![S3 Cache Control](/static/assets/marc-olivier-jodoin-NqOInJ-ttqM-unsplash.jpg)

## Lighthouse Report

Within Chrome, we can generate a Lighthouse report which will identify any images that are not cached correctly.

![](/static/assets/lighthouse.png)

In this image, we can see that the default “cache policy” applied to resources in a S3 bucket is to tell the browser to _not_ cache the resource.

## Cache-Control HTTP Header

To cache an resource, we need to send a Cache-Control HTTP header with a suitable timeout to cache. The timeout is measured in seconds and is identified as the `max-age` of the resource.

So for example, to tell the browser to cache resources for 1 day, we would use a `max-age` of `60s * 60m * 24h = 86400`. To tell the browser to cache for 1 week, we would use a `max-age` of `60s * 60m * 24h * 7d = 604800`.

So, how do we configure S3 to specify a cache time ?

## S3 Cache Configuration

Within the S3 Console, we can select either an individual resource, or an entire directory and specify this value. To do this, we select to edit the Metadata of the selected objects.

![](/static/assets/editmetadata.png)

On the resulting screen, we select the Add Metadata section and add a System Defined piece of metadata with a key of `Cache-Control` and a value of `max-age=<number of seconds>`

![](/static/assets/addmetadata.png)

In this image, you can see that I’ve set the `max-age` to `7 days` (60s _ 60m _ 24h \* 7d).

That’s all there is to it! Save the changes to the metadata and S3 will start hosting your resources with an effective cache control.

## Credits

Photo by <a href="https://unsplash.com/@marcojodoin?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Marc-Olivier Jodoin</a> on <a href="https://unsplash.com/photos/NqOInJ-ttqM?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>


