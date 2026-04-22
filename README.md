![Status](https://img.shields.io/badge/status-archived-red)


> ⚠️ Repository Archived ⚠️
> =========================
>
> This repository is archived and no longer maintained.
>
> Please refer to the [upstream repository](https://github.com/pmitros/ConceptXBlock) directly. No further development or support will be provided here.
> 
> See the migration discussion: [openedx/xblocks-extra#7](https://github.com/openedx/xblocks-extra/issues/5).
>
> **Note:** This fork is many commits ahead of the upstream repository; feel free to push to upstream if required.

ConceptXBlock
===========

This is a simple XBlock which will allows one to tag problems with
concepts. To be useful, it requires a concept server. There is one in
the matching concept-tag-server repo.

Usage: 

       <Concept server="http://www.sample-concept-demo-server.org:7000/">

This displays: 

![ConceptXBlock screenshot](learning_objectives.png)

In the bottom left, you can search for learning objectives, and drag
them into one of the top three bins. The bins are: 

* Taught: For concepts which the item introduces. For example, a video
  explaining the quadaratic equation would be tagged as teach the
  quadratic equation. Perhaps should be renamed to 'introduced'? 
* Exercised: For concepts which the problem is explicitly designed to
  practice. For example, "Solve 5x^2+6x=7" would exercise the
  quadratic equation.
* Required: For concepts implicitly required. For example, a physics
  problem on the path of a rocket might have the quadratic equation
  as a prerequisite, but not be explictly designed to exercise it. 

The edit button is a link back to the concept tag server, where we can
edit concept descriptions.

The system has a few serious issues: 

1. Performance. This is trivial to fix, but the system currently makes
   an AJAX request per objective on the page. Bulk requests would
   solve this.
2. 500 errors when e.g. a concept is not on the concept server. 
3. No test cases. 
4. Shown as a student (rather than instructor) view. This is a Studio
   limitation. 
5. Lack of configurability. It works on my taxonomy
   (taught/exercised/required), and not yours.
6. Horrific styling. In desperate need of a cleanup. 

It does have a few nice properties: 

1. Continues to develop edX-as-a-platform, rather than
   edX-as-a-product.
2. Natural path (via concept wiki) to coming up with a concept
   taxonomy. Next steps will be to split and join objectives.
3. Natural extension to other wise of tagging objectives (e.g. Bloom's
   taxonomy, etc.)