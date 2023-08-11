---
layout: post
title:  "Apple Clang C++ standards support is embarrassingly bad!"
date:   2023-08-11 12:52:26 +0300
tags:   cpp clang
---

Recently I was doing a test task for a C++ developer position and decided to use macOS as my development platform. I haven't used macOS in that role for a very long time favouring Windows with Visual Studio.

So, one of the additional subtasks in the test task was to implement some computation in parallel. And since this computation was simple enough to be implemented with just one of the algorithms from the C++ standard library I thought I will just use C++17 parallel algorithms and that is gone be it. Now imagine my surprise when I found out that Apple Clang C++ compiler [does not support](https://en.cppreference.com/w/cpp/compiler_support/17) the above mentioned C++17 feature! 

![](/images/cpp17-library-features.png)

As you can see from the table above even the most recent Clang supports C++17 parallel algorithms only partially while its forks, such as, for example, Apple Clang, does not support this feature at all. Yes, you got it right, a C++17 feature is missing from Apple Clang compiler in the year 2023! 

Interestingly, Apple Clang C and C++ compilers also do not directly support OpenMP which is de-facto standard for shared memory parallel programming.
All of this makes me think that Apple is trying vendor lock-in us with their own proprietary parallel programming technology known as the [Grand Central Dispatch](https://developer.apple.com/documentation/DISPATCH). And I think it's disgusting.
