# Refactoring with Joyride

## Intro.

### Look here first

[Formatting with Calva](https://calva.io/formatting/)

[Refactoring with Calva](https://calva.io/refactoring/)

### Developing your own refactorings

Setting up joyride repl, etc. for easy experimentation.

Testing your refactorings

### References for refactorings

Point to rewrite-clj prior art

Why isn't there a rewrite-clj cookbook?

## Getting the code

Imports
```clojure
            ["vscode" :as vscode]
            ["ext://betterthantomorrow.calva$v0" :as calva]
            [joyride.core :as joyride]
            [promesa.core :as p]
            [util.editor :as editor-utils]
```

### Get the current selection

(editor-utils/current-selection-text)

#### Handling a selection that is not a valid form

##### How to tell if the selection isn't a current form

But you might know already, because it was intentional.

### Get the current form

### Get the enclosing form

### Get the top level form

### Get top level def*

### Getting a file

todo: how to navigate the workspace

```clojure
(util.workspace/slurp-file+ <todo>)
```

#### Getting something from the internet/github repo?

### Using built in search 

## Manipulating the code

### with rewrite-clj

### with clojure.walk

### with vscode built-ins

```clojure
(defn ignore-current-form []
  (p/let [[range text] (calva/ranges.currentEnclosingForm)]
    (calva/editor.replace vscode/window.activeTextEditor range (str "#_" text))))
```

### with ???

[clojure-symbols](../examples/.joyride/src/clojure_symbols.cljs)

## Writing the changed code

Describe Positions, ranges, etc.

### Straight calva

```clojure
 (calva/editor.replace vscode/window.activeTextEditor range (str "#_" text))
 ```
 
### joyride/utils.editor

insert-text!+, delete-range!+, replace-range!+
 
### Writing out a file

## Larger scope

### Selecting among refactoring (quickpick, storing/retriving config files)

### Getting user input during the refactor

#### input

#### quickpick

#### webview

This will be awesome!

## Keeping it close to hand

### Binding to keys

#### vscode when clauses and keybindings
