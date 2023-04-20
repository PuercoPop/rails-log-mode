# Rails Log Mode

Major mode for viewing Rails log files.

## Installation

````elisp
(add-to-list 'load-path "path/to/rails-log-mode/dir")
(require 'rails-log-mode)
````

## Usage

Run `M-x rails-log` from any buffer inside the project folder. This prompt you
for an environment log file to open and run `tail -f` it. All the file paths in
the log are navigatable. Pressing `Enter` will open a file in the stack trace.

Uses project.el to find the project root if for some reason the built-in `vc`
backend doesn't work for your project layout, consider using something like:

```elisp
(defun project-try-ruby (dir)
  (when-let ((project-root (locate-dominating-file default-directory "Gemfile")))
    (cons 'ruby project-root)))
```
