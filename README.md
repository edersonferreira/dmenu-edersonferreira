# My Dmenu build

This is my Dmenu build, with my patches and configs in `config.h`.

# Build

To build this Dmenu, use:

```
sudo make install
```

And install the fonts: `JetBrains Mono Bold Nerd Font Complete Mono.ttf` and `JetBrains Mono Bold Nerd Font Complete.ttf` in a fonts directory, like moving to `~/.fonts`

And the Dmenu will be compiled and installed.

# Patches

- dmenu-border-4.9.diff
- dmenu-center-20200111-8cd37e1.diff
- dmenu-fuzzymatch-4.9.diff
- dmenu-highlight-4.9.diff
- dmenu-highpriority-4.9.diff
- dmenu-lineheight-5.0.diff
- dmenu-morecolor-20190922-4bf895b.diff
- dmenu-mousesupport-5.0.diff
- dmenu-navhistory-20200709.diff

# config.h

```c
/* See LICENSE file for copyright and license details. */
/* Default settings; can be overriden by command line. */

static int topbar = 0;                      /* -b  option; if 0, dmenu appears at bottom     */
static int centered = 1;                    /* -c option; centers dmenu on screen */
static int min_width = 1000;                    /* minimum width when centered */
static int fuzzy = 1;                      /* -F  option; if 0, dmenu doesn't use fuzzy matching     */
static unsigned int maxhist    = 64;
static int histnodup           = 0;	/* if 0, record repeated histories */

/* -fn option overrides fonts[0]; default X11 font or font set */
static const char *fonts[] = {
	"JetBrainsMono Nerd Font:size=12:style=Bold"
};
static const char *prompt      = NULL;      /* -p  option; prompt to the left of input field */
static const char *colors[SchemeLast][2] = {
	/*     fg         bg       */
	[SchemeNorm] = { "#DDDDDD", "#0C0A0F" },
	[SchemeSel] = { "#FFFFFF", "#2B7DF0" },
	[SchemeOut] = { "#000000", "#00FFFF" },
	[SchemeNormHighlight] = { "#32BCD9", "#222222" },
	[SchemeSelHighlight] = { "#32BCD9", "#161419" },
	[SchemeHp] = { "#bbbbbb", "#333333" },


};
/* -l option; if nonzero, dmenu uses vertical list with given number of lines */
static unsigned int lines      = 0;

/*
 * Characters not considered part of a word while deleting words
 * for example: " /?\"&[]"
 */
static const char worddelimiters[] = " ";

/* Size of the window border */
static const unsigned int border_width = 3;
```
