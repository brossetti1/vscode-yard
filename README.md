# YARD Documenter

[![Build Status](https://travis-ci.org/pavlitsky/vscode-yard.svg?branch=master)](https://travis-ci.org/pavlitsky/vscode-yard)
[![Maintainability](https://api.codeclimate.com/v1/badges/54361b514cbeb2dd279c/maintainability)](https://codeclimate.com/github/pavlitsky/vscode-yard/maintainability)

Extension helps to document Ruby source code with [YARD](https://yardoc.org/) comments.

See [Readme](http://www.rubydoc.info/gems/yard/file/README.md) for more information on this tool.

## Features

Extension prepends methods, classes, modules etc with documentation snippets.
No need to remember a formatting tags and styling, just type and describe your code.

## Usage

Position cursor on a definition you wish to document.

```ruby
def foo(bar, baz = false) # <- put cursor at any place of this line
end
```

Hit `Ctrl+Alt+Enter` (`Cmd+Alt+Enter` on macOS) or invoke `Document with YARD` from the command
palette.

```ruby
  #
  # <Description>
  #
  # @param [<Type>] bar <description>
  # @param [<Type>] baz <description>
  #
  # @return [<Type>] <description>
  #
  def foo(bar, baz = false)
  end
```

Documentation snippet appears on top of the method.

Use `Tab` and `Shift+Tab` keys to navigate and fill in placeholders.

Extension can document:

* Methods: instance methods, initializers, class methods.
* Classes and Modules.
* Constants.

## Details

List of supported tags: `@author`, `@option`, `@param`, `@return`.

## Configuration

```ts
"yard.spacers.beforeDescription" // Prepend an empty line to descriptive texts
"yard.spacers.afterDescription" // Append an empty line to descriptive texts
"yard.spacers.beforeTags" // Prepend an empty line to all method's tags
"yard.spacers.separateTags" // Separate method's tags of the same name (@params and @return) with an empty line
"yard.spacers.afterTags" // Append an empty line to all method's tags
"yard.spacers.beforeSingleTag" // Prepend an empty line to a single tag documentation (for example a constant)
"yard.spacers.afterSingleTag" // Append an empty line to a single tag documentation (for example a constant)
"yard.tags.author" // Append @author tag to Class and Module documentation
```

## TODO

* Ability to document attributes: `attr_reader`, `attr_writer`, `attr_accessor`.
* Ability to document blocks: `@yield`, `@yieldparam`, `@yieldreturn`.
* Support for non-empty options hash parameters.
* Resolve `@author` information from environment or settings.
* Ability to update existing documentation.
* (maybe) Editor snippets for tags (`@option`, `@param` etc) or tags autocompletion
* (maybe) A better support for array / keyword args splats, see
  [comment](https://github.com/lsegal/yard/issues/439#issuecomment-3292412).

## Troubleshooting

If hotkey isn't working open VS Code Keyboard Shortcuts and check for keybinging conflicts.

This also may happen if destination is already documented. In this case extension silently does
nothing.
