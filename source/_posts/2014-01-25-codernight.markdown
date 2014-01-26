---
layout: post
title: "codernight"
date: 2014-01-25 20:13:37 -0500
comments: true
categories: newb programming ruby
---

Here in Tampa we have a [Codernight](http://www.meetup.com/codernight)
meetup where we're given a programming puzzle and meet a few weeks later
to critique and discuss our solutions anonymously. This months puzzle was
[Robots vs. Lasers](http://www.puzzlenode.com/puzzles/4-robots-vs-lasers).

In this puzzle the input consisted of diagrams representing conveyor belts.

``` text sample-input.txt
#|#|#|##
---X----
###||###

##|#|#|#
----X---
###||###

##|#|#|#
----X---
###|||##
```
the X's represent the robots initial position on the conveyor and the pipes
are lasers north and south of the belt. On every even step if there's a north
laser the robot takes damage. On every odd step a south laser also causes damage.
The puzzle asked you to find the direction of least damage for each conveyor.

I spent a few nights working (and re-working) [my solution](https://github.com/TampaRuby/tampa-coder-night-012/tree/master/006)
and was pretty happy with it. I chose simple array-walking for finding the damage.

``` ruby robots_vs_lasers.rb
def damage(range)
  range.each.with_index.inject(0) do |damage,(n,step)|
    if @north_lasers[n] == '|' and step.even?
      damage + 1
    elsif @south_lasers[n] == '|' and step.odd?
      damage + 1
    else
      damage
    end
  end
end
```
Most of the other entrants summed the pipes in steps for each side to find damage.
I don't know how much faster that approach is but I imagine it's more efficient.
I think I'll rewrite my program sometime with that idea.

I wish my entry would of gotten more scrutiny but I did come away with some useful
feedback. First in my test file I was leaving some code behind from early TDD rounds,
such as

``` ruby robots_vs_lasers_test.rb
def test_conveyor_exists
  refute @conveyor nil?
end
```
This was considered noise by the other rubyists and could be deleted after
other tests start indirectly testing this.

I've refactored my program a few times since the meeting, the result is
[here](https://github.com/dave-maldonado/robots_vs_lasers). I was initially
very nervous about doing this as I've never had my code reviewed like this
but I'm very glad I did. It really helped in getting past my
[imposter syndrome](http://en.wikipedia.org/wiki/Imposter_syndrome). I'm really
starting to feel like my studying and practice is starting to pay off.
