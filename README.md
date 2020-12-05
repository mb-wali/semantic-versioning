# Semantic versioning
A semantic version is a number that consists of three numbers separated by a
period. For example, 1.4.10 is a semantic version. Each of the numbers has a
specific meaning.

![](images/version.JPG?raw=true)


| Major change | Minor change | Patch change |
| -----------  | ----------- | ----------- |
| The first number is a Major change,meaning it has a breaking change. | The second number is a Minor change, meaning it adds functionality.  |The third number is a Patch change, meaning it includes a bug fix. |

```
It is easier to look at semantic versioning as Breaking . Feature . Fix.
It is a more precise way of describing a version number that doesn’t leave any room for interpretation.
```

# Commit format

To make sure that we are releasing the correct version — by correctly
incrementing the semantic version number — we need to standardize our commit
messages. By having a standardized format for commit messages, we can know when
to increment which number and easily generate a release note.

We use [Angular commit message
convention](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#commit)
as our starting point and extend it in some parts.

It goes like this:
```
<header>
<optional body>
<optional footer>
```

## Each commit message consists of a header, a body, and a footer.

![](images/commit_header.png?raw=true)

### The commit header
The header is mandatory. It has a special format that includes a type, an
optional scope, and a subject.

The header’s type is a mandatory field that tells what impact the commit
contents have on the next version. It has to be one of the following types:

* **feature**: New feature
* **bugfix**: Bug fix
* **docs**: Change to the documentation (also used for spelling and grammar
  corrections)
* **style**: Changes that do not affect the meaning of the code (e.g.
  white-space, formatting, missing semi-colons, etc.)
* **modification**: Changes that neither fix a bug nor add a feature (e.g. 
Changes in ui-text, placeholder, names, fields)
* **refactor**: Changes that neither fix a bug nor add a feature
* **performance**: Change that improves performance
* **test**: Add missing tests or corrections to existing ones
* **build**: Changes to the build process or dependencies
* **ci**: Changes to our CI configuration files and scripts

The scope is a grouping property that specifies what subsystem the commit is
related to, like an API, or the dashboard of an app, or user accounts, etc. If
the commit modifies more than one subsystem, then we can use an asterisk (*)
instead.

The header subject should hold a short description of what has been done. There
are a few rules when writing one:

* Use the imperative, present tense (e.g. “change” instead of “changed” or
  “changes”)
* Lowercase the first letter on the first word.
* Leave out a period (.) at the end.
* Avoid writing subjects longer than 80 characters

### The commit body.


Just like the header subject, use the imperative, present tense for the body.

The body of the commit message should elaborate the why of the necessity of the
commit.

For the type **feature**:

* [*mandatory*] describe the problem the feature solves
* [*mandatory*] describe how the feature is working

For the type **bugfix**:

* [*mandatory*] describe the bug
* [*mandatory*] describe how it is solved by this commit
* [*optional*] describe why this solution is implemented and not possible other
  solutions

For the type **refactor**:

* [*mandatory*] describe the reason of the refactoring
* [*mandatory*] describe why it is easier to use/read now

For the type **performance**:

* [*mandatory*] describe the bottleneck
* [*mandatory*] describe why it is faster now
* [*optional*] describe why this solution is implemented and not possible other
  solutions

For the types **test, build and ci**:

* [*mandatory*] describe the solved problem

### The commit footer

The footer should contain any information about **breaking changes** and is also
the place to reference issues that this commit closes.

Breaking change information should start with ```BREAKING CHANGE:``` followed by
a space or two new lines. The rest of the commit message goes here.


### Example

```git
git commit -m "feature(dev): enable flask-debugtoolbar." -m "
  *This closes #12." -m "docs(todo): add to documentation."
  
```

*commit header*
```feature(dev): enable flask-debugtoolbar.```

*commit body* 
```* This closes #12.```

*commit footer*
```Todo(docs): add to documentation.```


copyrights &copy; Marko Ilic, Mojib Wali, Christoph Ladurner
