- [Config](#org5484262)
  - [Usage](#orgaa9305b)
    - [Export to Markdown/HTML/PDF](#orgb14caf7)
    - [Tangle Config](#org60de5e5)
  - [Emacs](#orgf50d29c)
    - [packages.el](#orgda69922)
    - [init.el](#org681e427)
    - [config.el](#org6e285d7)
    - [Snippets](#orgd890538)
  - [zsh](#orga89aa7e)
    - [.zshrc](#org9e4d340)
  - [Alacritty](#orgef6e7ba)
  - [Git](#org22c4229)



<a id="org5484262"></a>

# Config


<a id="orgaa9305b"></a>

## Usage


<a id="orgb14caf7"></a>

### Export to Markdown/HTML/PDF

For a literate reading you can export this file as Markdown/HTML/PDF etc. Some examples:

-   GitHub Flavored Markdown: `org-gfm-export-to-markdown`
-   HTML: `org-html-export-to-html`


<a id="org60de5e5"></a>

### Tangle Config

Each code block that is meant to be tangled will have their destination in their respective headers. All you need to do is to run `org-babel-tangle`. Do not run this if you&rsquo;re just browsing this repository, it will create (or overwrite) my config files to your system.


<a id="orgf50d29c"></a>

## Emacs


<a id="orgda69922"></a>

### packages.el

**These are the packages that I grab from MELPA**

```elisp
;; -*- no-byte-compile: t; -*-
;; ASDF for Common Lisp
(package! sly-asdf)

;; Beautiful HTML export from org-mode
(package! htmlize)

;; GitHub Flavored Markdown export from org-mode
(package! ox-gfm)

;; CoffeeScript
(package! coffee-mode)

;; Dash in Emacs (Unmaintained)
;; (package! helm-dash)

;; DevDocs in Emacs
(package! devdocs)
```


<a id="org681e427"></a>

### init.el

**These are the modules that I enable**

**Input:**

```elisp
:input
;;chinese
;;japanese
;;layout            ; auie,ctsrnm is the superior home row
```

**Completion:**

```elisp
:completion
company             ; the ultimate code completion backend
;;helm              ; the *other* search engine for love and life
;;ido               ; the other *other* search engine...
ivy                 ; a search engine for love and life
;;vertico           ; the search engine of the future
```

**UI:**

```elisp
:ui
;;deft              ; notational velocity for Emacs
doom                ; what makes DOOM look the way it does
doom-dashboard      ; a nifty splash screen for Emacs
doom-quit           ; DOOM quit-message prompts when you quit Emacs
;;(emoji +unicode)  ; ????
hl-todo             ; highlight TODO/FIXME/NOTE/DEPRECATED/HACK/REVIEW
;;hydra
indent-guides       ; highlighted indent columns
ligatures           ; ligatures and symbols to make your code pretty again
;;minimap           ; show a map of the code on the side
modeline            ; snazzy, Atom-inspired modeline, plus API
;;nav-flash         ; blink cursor line after big motions
;;neotree           ; a project drawer, like NERDTree for vim
ophints             ; highlight the region an operation acts on
(popup +defaults)   ; tame sudden yet inevitable temporary windows
;;tabs              ; a tab bar for Emacs
treemacs            ; a project drawer, like neotree but cooler
;;unicode           ; extended unicode support for various languages
vc-gutter           ; vcs diff in the fringe
vi-tilde-fringe     ; fringe tildes to mark beyond EOB
;;window-select     ; visually switch windows
workspaces          ; tab emulation, persistence & separate workspaces
;;zen               ; distraction-free coding or writing
```

**Editor:**

```elisp
:editor
(evil +everywhere)  ; come to the dark side, we have cookies
file-templates      ; auto-snippets for empty files
fold                ; (nigh) universal code folding
;;(format+onsave)    ; automated prettiness
;;god               ; run Emacs commands without modifier keys
;;lispy             ; vim for lisp, for people who don't like vim
multiple-cursors    ; editing in many places at once
;;objed             ; text object editing for the innocent
;;parinfer          ; turn lisp into python, sort of
;;rotate-text       ; cycle region at point between text candidates
snippets            ; my elves. They type so I don't have to
;;word-wrap         ; soft wrapping with language-aware indent
```

**Emacs:**

```elisp
:emacs
dired             ; making dired pretty [functional]
electric          ; smarter, keyword-based electric-indent
;;ibuffer         ; interactive buffer management
undo              ; persistent, smarter undo for your inevitable mistakes
vc                ; version-control and Emacs, sitting in a tree
```

**Term:**

```elisp
:term
;;eshell            ; the elisp shell that works everywhere
;;shell             ; simple shell REPL for Emacs
term                ; basic terminal emulator for Emacs
;;vterm             ; the best terminal emulation in Emacs
```

**Checkers:**

```elisp
:checkers
syntax              ; tasing you for every semicolon you forget
;;(spell +flyspell) ; tasing you for misspelling mispelling
;;grammar           ; tasing grammar mistake every you make
```

**Tools:**

```elisp
:tools
;;ansible
;;debugger          ; FIXME stepping through code, to help you add bugs
;;direnv
;;docker
editorconfig        ; let someone else argue about tabs vs spaces
;;ein               ; tame Jupyter notebooks with emacs
(eval +overlay)     ; run code, run (also, repls)
;;gist              ; interacting with github gists
lookup              ; navigate your code and its documentation
lsp                 ; M-x vscode
magit               ; a git porcelain for Emacs
make                ; run make tasks from Emacs
;;pass              ; password manager for nerds
;;pdf               ; pdf enhancements
;;prodigy           ; FIXME managing external services & code builders
;;rgb               ; creating color strings
;;taskrunner        ; taskrunner for all your projects
;;terraform         ; infrastructure as code
;;tmux              ; an API for interacting with tmux
;;upload            ; map local to remote projects via ssh/ftp
```

**OS:**

```elisp
:os
(:if IS-MAC macos)  ; improve compatibility with macOS
;;tty               ; improve the terminal Emacs experience
```

**Lang:**

```elisp
:lang
;;cc                ; C > C++ == 1
;;clojure           ; java with a lisp
common-lisp         ; if you've seen one lisp, you've seen them all
crystal             ; (+lsp) ; ruby at the speed of c
;;data              ; config/data formats
;;elixir            ; erlang done right
;;elm               ; care for a cup of TEA?
emacs-lisp          ; drown in parentheses
;;erlang            ; an elegant language for a more civilized age
;;ess               ; emacs speaks statistics
;;factor
;;gdscript          ; the language you waited for
(go +lsp)           ; the hipster dialect
json                ; At least it ain't XML
;;(java +lsp)       ; the poster child for carpal tunnel syndrome
(javascript +lsp)   ; all(hope(abandon(ye(who(enter(here))))))
;;julia             ; a better, faster MATLAB
;;kotlin            ; a better, slicker Java(Script)
;;latex             ; writing papers in Emacs has never been so fun
;;lua               ; one-based indices? one-based indices
markdown            ; writing docs for people to ignore
;;(nim +lsp)        ; python + lisp at the speed of c
;;nix               ; I hereby declare "nix geht mehr!"
;;ocaml             ; an objective camel
org                 ; organize your plain life in plain text
;;plantuml          ; diagrams for confusing people more
;;python            ; beautiful is better than ugly
;;qt                ; the 'cutest' gui framework ever
;;racket            ; a DSL for DSLs
;;rest              ; Emacs as a REST client
;;rst               ; ReST in peace
(ruby +lsp)         ; (+rails) ; 1.step {|i| p "Ruby is #{i.even? ? 'love' : 'life'}"}
;;rust              ; Fe2O3.unwrap().unwrap().unwrap().unwrap()
;;(scheme +guile)   ; a fully conniving family of lisps
sh                  ; she sells {ba,z,fi}sh shells on the C xor
web                 ; the tubes
yaml                ; JSON, but readable
;;zig               ; C, but simpler
```

**Email:**

```elisp
:email
;;(mu4e +org +gmail)
;;notmuch
;;(wanderlust +gmail)
```

**App:**

```elisp
:app
;;calendar
;;emms
;;everywhere        ; *leave* Emacs!? You must be joking
;;irc               ; how neckbeards socialize
;;(rss +org)        ; emacs as an RSS reader
;;twitter           ; twitter client https://twitter.com/vnought
```

**Config:**

```elisp
:config
;;literate
(default +bindings +smartparens)
```

**Assemble the file:**

```elisp
;;; init.el -*- lex ical-binding: t; -*-
(doom!
       <<doom-input>>

       <<doom-completion>>

       <<doom-ui>>

       <<doom-editor>>

       <<doom-emacs>>

       <<doom-term>>

       <<doom-checkers>>

       <<doom-tools>>

       <<doom-os>>

       <<doom-lang>>

       <<doom-email>>

       <<doom-app>>

       <<doom-config>>
)
```


<a id="org6e285d7"></a>

### config.el

**Config for Doom to load**

**Core editor settings:**

```elisp
(setq user-full-name "sourceweaver"
      user-mail-address "sw.git@pm.me")

(setq display-line-numbers-type t)
(setq-default fill-column 120)
(setq fancy-splash-image "~/Pictures/MTG/Brainstorm.jpg")

;; Display indent guides:
(setq highlight-indent-guides-method 'column)

;; Set whitespace style:
(setq-default whitespace-style '(face tabs tab-mark spaces space-mark trailing))

;; Turn whitespace mode on globally:
;; (global-whitespace-mode +1)

;; Start emacs fullscreen:
; ;(add-hook 'after-init-hook 'toggle-frame-fullscreen)
```

**Theme and visual settings:**

```elisp
(setq doom-theme 'doom-miramare)

;; Other themes that I like:
;; (setq doom-theme 'doom-xcode)
;; (setq doom-theme 'doom-monokai-octagon)
;; (setq doom-theme 'doom-gruvbox)

;; Themes that are good for exporting:
;; (setq doom-theme 'doom-tango)
;; (setq doom-theme 'doom-plain)

;; Font settings:
;; TODO: Find out where doom-variable-pitch-font and doom-serif-font is used.
(setq-default line-spacing 0.20)
(setq-default doom-font (font-spec :family "JetBrains Mono Medium" :size 24)
              doom-variable-pitch-font (font-spec :family "JetBrains Mono" :size 24)
              doom-big-font (font-spec :family "JetBrains Mono Bold" :size 24)
              doom-unicode-font (font-spec :family "IBM Plex Mono")
              doom-serif-font (font-spec :family "IBM Plex Sans"))

;; Set cursor faces and colors:
(setq evil-normal-state-cursor '(box "cyan")
      evil-insert-state-cursor '(box "light cyan")
      evil-visual-state-cursor '(hollow "purple"))

```

**Org mode settings:**

```elisp
;; Completed items get timestamped:
(setq org-log-done 'time)

;; Multiline emphasis is allowed(up-to 5 lines):
(setq org-emphasis-regexp-components
      '("-[:space:]('\"{" "-[:space:].,:!?;'\")}\\[" "[:space:]" "." 5))

;; Load languages for org-babel:
(org-babel-do-load-languages
 'org-babel-load-languages
 '((crystal . t)
   (ruby . t)
   (js . t)))

;; Number and order footnotes:
(setq org-footnote-auto-adjust t)
```

**Crystal mode settings:**

```elisp
;; Register Crystalline as a language backend:
;; NOTE: Enable (+lsp) on `init.el` for this to take effect.
;; (with-eval-after-load 'lsp-mode
;;   (add-to-list 'lsp-language-id-configuration
;;                '(crystal-mode . "crystal"))
;;   (lsp-register-client
;;    (make-lsp-client :new-connection (lsp-stdio-connection '("crystalline" "--stdio"))
;;                     :activation-fn (lsp-activate-on "crystal")
;;                     :completion-in-comments? nil
;;                     :priority 1
;;                     :server-id 'crystalline)))
```

**Go mode settings:**

```elisp
;; Format with `goimports` instead of `gofmt`:
(setq gofmt-command "goimports")

;; Set lint rules using flycheck-golangci-lint:
;; (setq flycheck-golangci-lint-enable-all t)

;; Making flycheck work with LSP
;; See: https://github.com/weijiangan/flycheck-golangci-lint/issues/8
;;(defvar-Local flycheck-local-checkers nil)
;;  (defun +flycheck-checker-get(fn checker property)
;;    (or (alist-get property (alist-get checker flycheck-local-checkers))
;;        (funcall fn checker property)))
;;  (advice-add 'flycheck-checker-get :around '+flycheck-checker-get)

;;(add-hook 'go-mode-hook (lambda()
;;                            (flycheck-golangci-lint-setup)
;;                            (setq flycheck-local-checkers '((lsp . ((next-checkers . (golangci-lint))))))))
```

**Web mode settings:**

```elisp
;; Register extensions as web-mode targets:
(add-to-list 'auto-mode-alist '("\\.gohtml\\'" . web-mode))
(add-to-list 'auto-mode-alist '("\\.ecr\\'" . web-mode))
(add-to-list 'auto-mode-alist '("\\.erb\\'" . web-mode))

;; Use the ERB engine in ECR files:
(setq web-mode-engines-alist
      '(("erb" . "\\.ecr\\'")))
```

**JS2 mode settings:**

```elisp
(setq-hook! 'js2-mode-hook flycheck-checker 'javascript-eslint)
```

**LSP mode settings:**

```elisp
;; Lsp tries to render links on treemacs, destroying its functionality.
;; as a work around we disable this offending setting.
(setq lsp-enable-links nil)

;; lsp performance tuning:
;; (setq gc-cons-threshold 100000000)
;; (setq read-process-output-max (* 1024 1024))

;; Slow lsp down:
(setq lsp-idle-delay 0.2)
(setq company-idle-delay 0.1)

;; Add more entries to ignored directories:
(after! lsp-mode
  (add-to-list 'lsp-file-watch-ignored-directories "[/\\\\]\\.cache\\'")
  (add-to-list 'lsp-file-watch-ignored-directories "[/\\\\]\\.parcel-cache\\'")
  (add-to-list 'lsp-file-watch-ignored-directories "[/\\\\]\\.git\\'")
  (add-to-list 'lsp-file-watch-ignored-directories "[/\\\\]\\build\\'")
  (add-to-list 'lsp-file-watch-ignored-directories "[/\\\\]\\lib\\'")
  (add-to-list 'lsp-file-watch-ignored-directories "[/\\\\]\\node_modules\\'"))
```

**Common Lisp mode settings:**

```elisp
;; Make sly open vertically instead of horizontally:
(after! sly
  (set-popup-rule! "^\\*sly-mrepl" :ignore t))
```

**Treemacs settings:**

```elisp
;; Make treemacs display only the current project:
(add-hook 'projectile-after-switch-project-hook 'treemacs-display-current-project-exclusively)
;; Make treemacs display colorful icons:
(setq doom-themes-treemacs-theme "doom-colors")

;; Add missing icons for some extensions:
;; FIXME:
;; Issue #1: The icons don't load unless you manually run doom/reload.
;; Issue #2: Alignments are a bit off compared to pre-configured icons.
(treemacs-define-custom-icon (format "  %s"(all-the-icons-fileicon "crystal" :height .9 :width .9 :face 'all-the-icons-purple)) "cr")
(treemacs-define-custom-icon (format "  %s"(all-the-icons-alltheicon "html5" :height .9 :width .9 :face 'all-the-icons-orange)) "ecr")
(treemacs-define-custom-icon (format "  %s"(all-the-icons-fileicon "gnu" :height .9 :width .9 :face 'all-the-icons-silver)) "Makefile")

;; Provide a way to ignore specific extensions/globs/regexps:
(after! treemacs
  (defvar treemacs-file-ignore-extensions '()
    "File extension which `treemacs-ignore-filter' will ensure are ignored")
  (defvar treemacs-file-ignore-globs '()
    "Globs which will are transformed to `treemacs-file-ignore-regexps' which `treemacs-ignore-filter' will ensure are ignored")
  (defvar treemacs-file-ignore-regexps '()
    "RegExps to be tested to ignore files, generated from `treeemacs-file-ignore-globs'")
  (defun treemacs-file-ignore-generate-regexps ()
    "Generate `treemacs-file-ignore-regexps' from `treemacs-file-ignore-globs'"
    (setq treemacs-file-ignore-regexps (mapcar 'dired-glob-regexp treemacs-file-ignore-globs)))
  (if (equal treemacs-file-ignore-globs '()) nil (treemacs-file-ignore-generate-regexps))
  (defun treemacs-ignore-filter (file full-path)
    "Ignore files specified by `treemacs-file-ignore-extensions', and `treemacs-file-ignore-regexps'"
    (or (member (file-name-extension file) treemacs-file-ignore-extensions)
        (let ((ignore-file nil))
          (dolist (regexp treemacs-file-ignore-regexps ignore-file)
            (setq ignore-file (or ignore-file (if (string-match-p regexp full-path) t nil)))))))
  (add-to-list 'treemacs-ignored-file-predicates #'treemacs-ignore-filter))

;; Actually ignore things:
(setq treemacs-file-ignore-extensions
      '("log"
        ))
(setq treemacs-file-ignore-globs
      '("*/.log"
        "*/node_modules"
        "*.parcel-cache"))
```

**Custom keymap:**:

```elisp
(setq evil-escape-key-sequence "jj")

(map! :leader
      :desc "toggle whitespace mode"
      "t w" 'whitespace-mode)

(map! :leader
      :desc "toggle whitespace mode"
      "t W" 'global-whitespace-mode)

(map! :leader
      :desc "toggle documentation"
      "t k" 'lsp-ui-doc-glance)

(map! :leader
      :desc "comment line"
      "l c" 'comment-line)

(map! :after go-mode
      :map go-mode-map
      :leader
      :desc "gofmt"
      "m f" 'gofmt)

(map! :after crystal-mode
      :map crystal-mode-map
      :leader
      :desc "crystal format"
      "m f" 'crystal-tool-format)

(map! :after go-mode
      :map go-mode-map
      :leader
      :desc "godoc at point"
      "m k" 'godoc-at-point)

(map! :after rjsx-mode
      :map rjsx-mode-map
      :leader
      :desc "lsp format"
      "m f" 'lsp-format-buffer)

(map! :after web-mode
      :map web-mode-map
      :leader
      :desc "editorconfig format"
      "m f" 'editorconfig-format-buffer)

(map! :after scss-mode
      :map scss-mode-map
      :leader
      :desc "editorconfig format"
      "m f" 'editorconfig-format-buffer)

(map! :leader
      :desc "reload/doom"
      "x" 'doom/reload)

(map! :leader
      :desc "edit code block in org-mode"
      "o c" 'org-edit-src-code)

(map! :leader
      :desc "Projectile replace with regex"
      "p r" 'projectile-replace-regexp)

(map! :leader
      :desc "Display dev docs"
      "t d" 'devdocs-lookup)
```

**Company mode settings:**

```elisp
;; NOTE: Following lists are experimental. Extract the repeating code once you're certain
;; with the order of things:

;; Ruby:
(set-company-backend! 'ruby-mode 'company-dabbrev 'company-keywords 'company-semantic 'company-etags 'company-files 'company-yasnippet 'company-capf)

;; Crystal:
(set-company-backend! 'crystal-mode 'company-dabbrev 'company-keywords 'company-semantic 'company-etags 'company-files 'company-yasnippet 'company-capf)

;; Org-mode:
(set-company-backend! 'org-mode 'company-dabbrev 'company-keywords 'company-semantic 'company-etags 'company-files 'company-yasnippet 'company-capf)
```

**Devdocs Settings:**

```elisp
(add-hook 'crystal-mode-hook
          (lambda () (setq-local devdocs-current-docs '("crystal"))))
```

**Assemble the file:**

```elisp
;;; $DOOMDIR/config.el -*- lexical-binding: t; -*-
<<core_settings>>

<<theme_settings>>

<<org_settings>>

<<crystal_settings>>

<<go_settings>>

<<web_settings>>

<<js2_settings>>

<<lsp_settings>>

<<lisp_settings>>

<<treemacs_settings>>

<<keymap_settings>>

<<company_settings>>

<<devdocs_settings>>
```


<a id="orgd890538"></a>

### Snippets

1.  Crystal

    **Comment result:**
    
    ```snippet
    # -*- mode: snippet -*-
    # name: comment_result
    # key: /cmnt-res
    # --
    # => $1
    ```

2.  Markdown

    **Ruby code fence:**
    
    ```snippet
    # -*- mode: snippet -*-
    # name: ruby-block
    # key: /rb-block
    # --
    \`\`\`ruby
    $1
    \`\`\`
    ```
    
    **Crystal code fence:**
    
    ```snippet
    # -*- mode: snippet -*-
    # name: crystal-block
    # key: /cr-block
    # --
    \`\`\`cr
    $1
    \`\`\`
    ```
    
    **README preamble:**
    
    ```snippet
    # -*- mode: snippet -*-
    # name: readme-pre
    # key: /readme-pre
    # --
    
    # $1
    
    ## Build Status
    <dl>
      <dt>Debian(x86_64)</dt>
      <dd>
        <a href="https://builds.sr.ht/~sourceweaver/???/commits/debian.yml.svg">
          <img src="https://builds.sr.ht/~sourceweaver/???/commits/debian.yml.svg" alt="Build status for ???" />
        </a>
      </dd>
    </dl>
    
    ## About
    
    $1 is a...
    
    You can get the source code from [SourceHut][1] or [Github][2]. SourceHut is the official repo
    where development happens, and the GitHub repo is an official mirror.
    
    ## Usage
    
    ## Report Issues
    
    ## License
    
    [1]: https://git.sr.ht/~sourceweaver/???
    [2]: https://github.com/sourceweaver/???
    ```

3.  Org

    **Crystal code block:**
    
    ```snippet
    # -*- mode: snippet -*-
    # name: crystal-src
    # key: /crsrc
    # --
    #+begin_src crystal :results output
    $1
    #+end_src
    ```


<a id="orga89aa7e"></a>

## zsh


<a id="org9e4d340"></a>

### .zshrc

**A simplified \`.zshrc\`**

**Core settings:**

```shell
export ZSH="/home/itsme/.oh-my-zsh"

ZSH_THEME="lambda"
COMPLETION_WAITING_DOTS="true"
HIST_STAMPS="dd/mm/yyyy"

plugins=()

source $ZSH/oh-my-zsh.sh

export LANG="en_US.UTF-8"
export LC_ALL="en_US.UTF-8"
export LANGUAGE="en_US.UTF-8"
```

**Path to tools:**

```shell
# User binaries
export PATH=$HOME/local/bin:$PATH
export PATH=$HOME/bin:$PATH

# Emacs:
export PATH=$HOME/emacs/bin:$PATH

# Go:
export GOPATH=$HOME/dev/go
export GOBIN=$HOME/local/go/bin
export PATH=$GOBIN:$PATH
export GO111MODULE=on

# GraalVM [Java]:
# To install other components run `gu available` and then e.g. `gu install ruby`
export PATH=$HOME/local/graalvm-ce-java17-22.2.0/bin:$PATH

# Node.js:
NODE_VERSION='v16.14.2'
NODE_DISTRO='linux-x64'
export PATH=$HOME/local/node-$NODE_VERSION-$NODE_DISTRO/bin:$PATH

# Crystal:
CRYSTAL_COMPILER='1.6.0-1-llvm14-glibc'
export PATH=$HOME/local/crystal-$CRYSTAL_COMPILER/bin:$PATH

# Ruby:
export PATH=$HOME/local/ruby/bin:$PATH

# Nvim:
export PATH=$HOME/local/nvim/bin:$PATH
```

**Aliases:**

```shell
# These aliases override zsh plugins.
# For a full list of aliases, run `alias`.
# ZSH
alias zshconfig="vim ~/.zshrc"
alias ohmyzsh='vim ~/.oh-my-zsh'

# TERM
alias x='exit'
alias q='exit'
alias c='clear'

# GIT
alias gts='git status'
alias gta='git add .'

# UNIX
alias top='htop'
alias vim='nvim'
```

**Functions:**

```shell
# GIT
gtc()     { git commit -m $1 } # $1: fixed bugs
gtp()     { git push $1 $2   } # $1: origin $2: master

# PERFORMANCE
cpu_perf_mode() { echo performance | sudo tee /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor } # Get mode
cpu_eco_mode()  { echo powersave | sudo tee /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor   } # Set Power Save
cpu_mode()      { cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor                         } # Set Perf

# GENERATORS
spawn_editorconfig() { cp ~/dev/conf/editor_config/.editorconfig $PWD }
spawn_ruby() {
    if [[ $# -eq 0 ]] ; then
        cat <<EOF
No project name provided
Usage:
spawn_ruby mandelbrot
EOF
        return 1
    fi

    cp -R ~/dev/templates/ruby $PWD/$1
}
```

**Assemble the file:**

```shell
<<zsh_core_settings>>

<<zsh_path>>

<<zsh_alias>>

<<zsh_functions>>
```


<a id="orgef6e7ba"></a>

## Alacritty

**Alacritty config:**

**Window & Scrolling:**

```yaml
window:
  decorations: none
  opacity: 0.9
  padding:
    x: 2
    y: 2
  class:
    instance: Alacritty
    general: Alacritty

scrolling:
  history: 10000
  multiplier: 3
```

**Font & Typography:**

```yaml
font:
  normal:
    family: JetBrains Mono Nerd Font
    style: Medium
  bold:
    family: JetBrains Mono Nerd Font
    style: Bold
  italic:
    family: Jetbrains Mono
    style: Italic
  size: 19
draw_bold_text_with_bright_colors: true
```

**Colors:**

```yaml
colors:
  primary:
    # high-contrast:
    background : '0x1d2021'
    # normal-contrast:
    # background: '0x282828'
    # soft-contrast:
    # background = '0x32302f'
    foreground: '0xebdbb2'
  # Normal colors:
  normal:
    black:   '0x282828'
    red:     '0xcc241d'
    green:   '0x98971a'
    yellow:  '0xd79921'
    blue:    '0x458588'
    magenta: '0xb16286'
    cyan:    '0x689d6a'
    white:   '0xa89984'
  # Bright colors:
  bright:
    black:   '0x928374'
    red:     '0xfb4934'
    green:   '0xb8bb26'
    yellow:  '0xfabd2f'
    blue:    '0x83a598'
    magenta: '0xd3869b'
    cyan:    '0x8ec07c'
    white:   '0xebdbb2'
```

**Misc & Keybinds:**

```yaml
selection:
  save_to_clipboard: false
shell:
  program: /usr/bin/zsh

key_bindings:
  - { key: Return, mods: Super|Shift, action: SpawnNewInstance }
```

```yaml
<<alacritty_core>>
<<alacritty_typography>>
<<alacritty_colors>>
<<alacritty_misc>>
```


<a id="org22c4229"></a>

## Git

**Baseline Git config:**

```conf
[filter "lfs"]
    clean    = git-lfs clean -- %f
    smudge   = git-lfs smudge -- %f
    required = true

[core]
    editor   = vim
    autocrlf = input

[user]
    name       = sourceweaver
    email      = sw.git@pm.me
    signingkey = CD3CFF04D7BD8619

[commit]
    template = ~/.gitmessage
    gpgsign = true

[url "git@gitlab.com:"]
    insteadOf = https://gitlab.com/

[url "git@github.com:"]
    insteadOf = https://github.com/

```

**Git commit message template:**

```conf
Subject line (try to keep under 60 characters)

# Multi-line description of commit,
# feel free to be detailed.
Signed-off-by: sourceweaver <sw.git@pm.me>
```
