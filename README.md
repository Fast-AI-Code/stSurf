# My build of Suckless Surf

## Patches applied

- 0.6-navhist
- 2.0-externalpipe
- 2.0-homepage
- bookmarks-20170722-723ff26
- clipboard-20200112-a6a8878
- git-20170323-webkit2-searchengines
- playexternal-20190724-b814567
- scrollmultiply-2.0
- websearch-20190510-d068a38

## Keybinds

#define HOMEPAGE "https://duckduckgo.com/"
/* modifier              keyval          function    arg */
{ MODKEY,                GDK_KEY_g,      spawn,      SETPROP("_SURF_URI", "_SURF_GO", PROMPT_GO) },
{ MODKEY,                GDK_KEY_d, externalpipe, { .v = linkselect_curwin } },
{ GDK_SHIFT_MASK|MODKEY, GDK_KEY_d, externalpipe, { .v = linkselect_newwin } },
{ MODKEY,                GDK_KEY_o, externalpipe, { .v = editscreen        } },
{ MODKEY,                GDK_KEY_o,      spawn,      SEARCH() },
{ MODKEY,                GDK_KEY_f,      spawn,      SETPROP("_SURF_FIND", "_SURF_FIND", PROMPT_FIND) },
{ MODKEY,                GDK_KEY_slash,  spawn,      SETPROP("_SURF_FIND", "_SURF_FIND", PROMPT_FIND) },
{ MODKEY,                GDK_KEY_m,      spawn,      BM_ADD("_SURF_URI") },

{ MODKEY,                GDK_KEY_v,      playexternal, { 0 } },

{ 0,                     GDK_KEY_Escape, stop,       { 0 } },
{ MODKEY,                GDK_KEY_c,      stop,       { 0 } },

{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_r,      reload,     { .i = 1 } },
{ MODKEY,                GDK_KEY_r,      reload,     { .i = 0 } },

{ MODKEY,                GDK_KEY_l,      navigate,   { .i = +1 } },
{ MODKEY,                GDK_KEY_h,      navigate,   { .i = -1 } },
/* vertical and horizontal scrolling, in viewport percentage */
{ MODKEY,                GDK_KEY_j,      scrollv,    { .i = +20 } },
{ MODKEY,                GDK_KEY_k,      scrollv,    { .i = -20 } },
{ MODKEY,                GDK_KEY_space,  scrollv,    { .i = +50 } },
{ MODKEY,                GDK_KEY_b,      scrollv,    { .i = -50 } },
{ MODKEY,                GDK_KEY_i,      scrollh,    { .i = +10 } },
{ MODKEY,                GDK_KEY_u,      scrollh,    { .i = -10 } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_j,      zoom,       { .i = -1 } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_k,      zoom,       { .i = +1 } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_q,      zoom,       { .i = 0  } },
{ MODKEY,                GDK_KEY_minus,  zoom,       { .i = -1 } },
{ MODKEY,                GDK_KEY_plus,   zoom,       { .i = +1 } },
{ MODKEY,                GDK_KEY_p,      clipboard,  { .i = 1 } },
{ MODKEY,                GDK_KEY_y,      clipboard,  { .i = 0 } },

{ MODKEY,                GDK_KEY_n,      find,       { .i = +1 } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_n,      find,       { .i = -1 } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_p,      print,      { 0 } },
{ MODKEY,                GDK_KEY_t,      showcert,   { 0 } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_a,      togglecookiepolicy, { 0 } },
{ 0,                     GDK_KEY_F11,    togglefullscreen, { 0 } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_o,      toggleinspector, { 0 } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_c,      toggle,     { .i = CaretBrowsing } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_f,      toggle,     { .i = FrameFlattening } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_g,      toggle,     { .i = Geolocation } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_s,      toggle,     { .i = JavaScript } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_i,      toggle,     { .i = LoadImages } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_v,      toggle,     { .i = Plugins } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_b,      toggle,     { .i = ScrollBars } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_t,      toggle,     { .i = StrictTLS } },
{ MODKEY|GDK_SHIFT_MASK, GDK_KEY_m,      toggle,     { .i = Style } },
