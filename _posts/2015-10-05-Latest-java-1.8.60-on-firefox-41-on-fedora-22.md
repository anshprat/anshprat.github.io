---
layout: post
title: Latest java 1.8.60 on firefox 41 on fedora 22 
date: 2014-10-05 14:00:00.000000000 +05:30
categories: []
tags: []
status: publish
type: post
published: true
meta:
  _edit_last: '1'
  _publicize_twitter_user: '@anshprat'
  _wpas_done_all: '1'
  _wpas_skip_2752212: '1'
author: 
---

I updated my java to the latest 1.8.60 on my fedora 22. After the latest java update, I lost the java firefox plugin.
The browser did not detect any local java at all. The link at http://www.java.com/en/download/installed.jsp?detect=jre failed to detect any java.
I reinstalled the java rpm but to no avail. A reboot did not help either.
I then used the documentation at http://www.oracle.com/technetwork/java/javase/manual-plugin-install-linux-136395.html to create a manual symlink at ~/.mozilla/plugin and voila. It all started working fine :)

