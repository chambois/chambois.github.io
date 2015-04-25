---
layout: post
title:  "Test driven learning: hack your skills"
date:   2014-05-11 15:06:00
categories: 
---

## Intro
* Where you set the scene and tell your readers everything they need to know to
understand why what you’re about to say is important
* spark interest
* where does the story start?

Feel like you grasp the concept of something new one day, only to struggle to
retrieve it later? Have to learn things again and again? And again?

Illusion of competence. Reading is not enough. Analogy with TDD. Just as tests
improve production code, tests of recall improve working knowledge.

Skimming the surface

(Deliberate) Practise!

Your learning, it's your responsibility!

Example problem - learning design patterns - Observer
  so you read about the design pattern, good first step
    how about reading from multiple sources? (interleaving)
      wikipedia
      sourcemaking
      book
    how about trying to apply it? (practise)
    how about trying to apply it in different contexts?  (practise/interleaving)

  the observer pattern
    chunking it
    using it in context
    repeat.

  practise
    code a basic example
      in different languages
    draw a (uml) diagram
    knowl base
    uml to code, code to uml
    teach!
    momentum
      sometimes just start small on something easy
    persistence
    recall
      test context - when to apply
      multi-choice
        how to write a good test?
      rubber duck technique
      questions
        what is the difference between pub/sub and observer? When would you
        use one vs the other?
          pub/sub can have multiple channels. publisher may not know of the
          subscribers at all, whereas subject in observer pattern has
          references to the observers.
        name three contexts which could be good candidates for the observer
        pattern
          ajax
          ui events
        what are the two names given to the object with the data to send?
          publisher
          subject
        what are the two names given to the object that receives the data?
          observer
          subscriber
    sandbox 
      refactoring
      creation
    real-world

    class Subject

      def initialize
        @observers = []
      end

      def add_observer(observer)
        @observers.push(observer)
      end

      def remove_observer(observer)
        #TODO is this the right way to remove element from array?
        @observers.pop(observer)
      end
        
      def notify_observers
        #TODO pass some data to observers
        @observers.each { |observer| observer.update }
      end

    end


    class Observer

      def initialize(subject)
        subject.add_observer(self)
      end

      def notify(data)
        # do something with data
      end

    end




## Inciting incident
* The question that your story is asking OR when the protagonist is faced with a
challenge

## Raise the stakes
* A series of moments that give weight and context to the inciting incident
(details).

## Main event
* inciting incident come to a head (aka the climax). This is either the answer
to the question we asked in the second beat or where the protagonist solves
his or her dilemma — a pivot or a change (even if it's just a shift in
attitude) should occur.

## Resolution
* highlight what makes the story unique. If you've just described a failure or
challenge, this would be the time to reflect on what you learned. 


