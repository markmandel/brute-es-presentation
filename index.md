title: Entity Component Systems with Brute
author:
  name: Mark Mandel
  twitter: Neurotic
  email: mark@compoundtheory.com
  url: http://www.compoundtheory.com
style: style.css
--
# Entity Component Systems with Brute
--
# What's The Problem?

- Does a camera shoot people?
- Can a bullet accept input from a player?

--
# Entity Systems Allow Anything to Become Anything
--

# What is an Entity
## It's a unique ID

--
# What is a Component?
## Labels an entity as having a particular aspect, and stores the relevent Data

-- 
# What is a System
## A System performs global actions on entities that contain relevent component(s)

- Physics
- Rendering
- Animation
- AI
- Input

--
# ES and FP
## Entity and Components are JUST DATA

```clojure
{ 1 [ { :type :player }
      { :type :accepts-input }
      { :type :sprite :image "dog.png" :x 10 :y 30 } ]
  2 [ { :type :enemy }
      { :type :ai :action :kill }
      { :type :sprite :image "robot.png" :x 50 :y 30 } ]
  3 [ { :type :bullet }
      { :type :physics :velocity { :x 5 :y 0 } }
      { :type :sprite :image "bullet.png" :x 20 :y 30 } ] }
```

--
# ES and FP
## Systems can be JUST FUNCTIONS

```clojure
(defn process-one-game-tick [system delta]
  ; Do some sort of cool thing here
  )
```

--
## Common ES System Functions

- `(create-entity)`
- `(add-entity system)`
- `(add-component system component)`
- `(get-component system entity type)`
- `(remove-component system entity instance)`
- `(kill-entity system entity)`

-- 
#Brute
## A simple and lightweight Entity Component System library for writing games with Clojure.

--
## Learn More
- https://github.com/markmandel/brute
- https://github.com/markmandel/brute-play-pong
- http://entity-systems.wikidot.com/
- http://t-machine.org/index.php/category/entity-systems/
- https://github.com/oakes/play-clj
- http://libgdx.badlogicgames.com/