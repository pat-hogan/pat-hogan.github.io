<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>LeagueStats</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>




<style type="text/css">
    pre { line-height: 125%; }
td.linenos pre { color: #000000; background-color: #f0f0f0; padding-left: 5px; padding-right: 5px; }
span.linenos { color: #000000; background-color: #f0f0f0; padding-left: 5px; padding-right: 5px; }
td.linenos pre.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
span.linenos.special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
.highlight .hll { background-color: var(--jp-cell-editor-active-background) }
.highlight { background: var(--jp-cell-editor-background); color: var(--jp-mirror-editor-variable-color) }
.highlight .c { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment */
.highlight .err { color: var(--jp-mirror-editor-error-color) } /* Error */
.highlight .k { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword */
.highlight .o { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator */
.highlight .p { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation */
.highlight .ch { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Multiline */
.highlight .cp { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Preproc */
.highlight .cpf { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Single */
.highlight .cs { color: var(--jp-mirror-editor-comment-color); font-style: italic } /* Comment.Special */
.highlight .kc { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Pseudo */
.highlight .kr { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: var(--jp-mirror-editor-keyword-color); font-weight: bold } /* Keyword.Type */
.highlight .m { color: var(--jp-mirror-editor-number-color) } /* Literal.Number */
.highlight .s { color: var(--jp-mirror-editor-string-color) } /* Literal.String */
.highlight .ow { color: var(--jp-mirror-editor-operator-color); font-weight: bold } /* Operator.Word */
.highlight .w { color: var(--jp-mirror-editor-variable-color) } /* Text.Whitespace */
.highlight .mb { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Bin */
.highlight .mf { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Float */
.highlight .mh { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Hex */
.highlight .mi { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer */
.highlight .mo { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Oct */
.highlight .sa { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Affix */
.highlight .sb { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Backtick */
.highlight .sc { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Char */
.highlight .dl { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Delimiter */
.highlight .sd { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Doc */
.highlight .s2 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Double */
.highlight .se { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Escape */
.highlight .sh { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Heredoc */
.highlight .si { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Interpol */
.highlight .sx { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Other */
.highlight .sr { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Regex */
.highlight .s1 { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Single */
.highlight .ss { color: var(--jp-mirror-editor-string-color) } /* Literal.String.Symbol */
.highlight .il { color: var(--jp-mirror-editor-number-color) } /* Literal.Number.Integer.Long */
  </style>



<style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
 * Mozilla scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */
[data-jp-theme-scrollbars='true'] {
  scrollbar-color: rgb(var(--jp-scrollbar-thumb-color))
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar. These selectors
 * will match lower in the tree, and so will override the above */
[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
}

/*
 * Webkit scrollbar styling
 */

/* use standard opaque scrollbars for most nodes */

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-corner {
  background: var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-thumb {
  background: rgb(var(--jp-scrollbar-thumb-color));
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-right: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

[data-jp-theme-scrollbars='true'] ::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
  border-bottom: var(--jp-scrollbar-endpad) solid
    var(--jp-scrollbar-background-color);
}

/* for code nodes, use a transparent style of scrollbar */

[data-jp-theme-scrollbars='true'] .CodeMirror-hscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true'] .CodeMirror-vscrollbar::-webkit-scrollbar,
[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-corner,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-corner {
  background-color: transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-thumb,
[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
  border: var(--jp-scrollbar-thumb-margin) solid transparent;
  background-clip: content-box;
  border-radius: var(--jp-scrollbar-thumb-radius);
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-hscrollbar::-webkit-scrollbar-track:horizontal {
  border-left: var(--jp-scrollbar-endpad) solid transparent;
  border-right: var(--jp-scrollbar-endpad) solid transparent;
}

[data-jp-theme-scrollbars='true']
  .CodeMirror-vscrollbar::-webkit-scrollbar-track:vertical {
  border-top: var(--jp-scrollbar-endpad) solid transparent;
  border-bottom: var(--jp-scrollbar-endpad) solid transparent;
}

/*
 * Phosphor
 */

.lm-ScrollBar[data-orientation='horizontal'] {
  min-height: 16px;
  max-height: 16px;
  min-width: 45px;
  border-top: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] {
  min-width: 16px;
  max-width: 16px;
  min-height: 45px;
  border-left: 1px solid #a0a0a0;
}

.lm-ScrollBar-button {
  background-color: #f0f0f0;
  background-position: center center;
  min-height: 15px;
  max-height: 15px;
  min-width: 15px;
  max-width: 15px;
}

.lm-ScrollBar-button:hover {
  background-color: #dadada;
}

.lm-ScrollBar-button.lm-mod-active {
  background-color: #cdcdcd;
}

.lm-ScrollBar-track {
  background: #f0f0f0;
}

.lm-ScrollBar-thumb {
  background: #cdcdcd;
}

.lm-ScrollBar-thumb:hover {
  background: #bababa;
}

.lm-ScrollBar-thumb.lm-mod-active {
  background: #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal'] .lm-ScrollBar-thumb {
  height: 100%;
  min-width: 15px;
  border-left: 1px solid #a0a0a0;
  border-right: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='vertical'] .lm-ScrollBar-thumb {
  width: 100%;
  min-height: 15px;
  border-top: 1px solid #a0a0a0;
  border-bottom: 1px solid #a0a0a0;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-left);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='horizontal']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-right);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='decrement'] {
  background-image: var(--jp-icon-caret-up);
  background-size: 17px;
}

.lm-ScrollBar[data-orientation='vertical']
  .lm-ScrollBar-button[data-action='increment'] {
  background-image: var(--jp-icon-caret-down);
  background-size: 17px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Widget, /* </DEPRECATED> */
.lm-Widget {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  cursor: default;
}


/* <DEPRECATED> */ .p-Widget.p-mod-hidden, /* </DEPRECATED> */
.lm-Widget.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-CommandPalette, /* </DEPRECATED> */
.lm-CommandPalette {
  display: flex;
  flex-direction: column;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-CommandPalette-search, /* </DEPRECATED> */
.lm-CommandPalette-search {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-content, /* </DEPRECATED> */
.lm-CommandPalette-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  min-height: 0;
  overflow: auto;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-CommandPalette-header, /* </DEPRECATED> */
.lm-CommandPalette-header {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}


/* <DEPRECATED> */ .p-CommandPalette-item, /* </DEPRECATED> */
.lm-CommandPalette-item {
  display: flex;
  flex-direction: row;
}


/* <DEPRECATED> */ .p-CommandPalette-itemIcon, /* </DEPRECATED> */
.lm-CommandPalette-itemIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemContent, /* </DEPRECATED> */
.lm-CommandPalette-itemContent {
  flex: 1 1 auto;
  overflow: hidden;
}


/* <DEPRECATED> */ .p-CommandPalette-itemShortcut, /* </DEPRECATED> */
.lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-CommandPalette-itemLabel, /* </DEPRECATED> */
.lm-CommandPalette-itemLabel {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-DockPanel, /* </DEPRECATED> */
.lm-DockPanel {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-widget, /* </DEPRECATED> */
.lm-DockPanel-widget {
  z-index: 0;
}


/* <DEPRECATED> */ .p-DockPanel-tabBar, /* </DEPRECATED> */
.lm-DockPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-DockPanel-handle, /* </DEPRECATED> */
.lm-DockPanel-handle {
  z-index: 2;
}


/* <DEPRECATED> */ .p-DockPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-DockPanel-handle:after, /* </DEPRECATED> */
.lm-DockPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal'] {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical'] {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='horizontal']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='horizontal']:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-DockPanel-handle[data-orientation='vertical']:after,
/* </DEPRECATED> */
.lm-DockPanel-handle[data-orientation='vertical']:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}


/* <DEPRECATED> */ .p-DockPanel-overlay, /* </DEPRECATED> */
.lm-DockPanel-overlay {
  z-index: 3;
  box-sizing: border-box;
  pointer-events: none;
}


/* <DEPRECATED> */ .p-DockPanel-overlay.p-mod-hidden, /* </DEPRECATED> */
.lm-DockPanel-overlay.lm-mod-hidden {
  display: none !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-Menu, /* </DEPRECATED> */
.lm-Menu {
  z-index: 10000;
  position: absolute;
  white-space: nowrap;
  overflow-x: hidden;
  overflow-y: auto;
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-Menu-content, /* </DEPRECATED> */
.lm-Menu-content {
  margin: 0;
  padding: 0;
  display: table;
  list-style-type: none;
}


/* <DEPRECATED> */ .p-Menu-item, /* </DEPRECATED> */
.lm-Menu-item {
  display: table-row;
}


/* <DEPRECATED> */
.p-Menu-item.p-mod-hidden,
.p-Menu-item.p-mod-collapsed,
/* </DEPRECATED> */
.lm-Menu-item.lm-mod-hidden,
.lm-Menu-item.lm-mod-collapsed {
  display: none !important;
}


/* <DEPRECATED> */
.p-Menu-itemIcon,
.p-Menu-itemSubmenuIcon,
/* </DEPRECATED> */
.lm-Menu-itemIcon,
.lm-Menu-itemSubmenuIcon {
  display: table-cell;
  text-align: center;
}


/* <DEPRECATED> */ .p-Menu-itemLabel, /* </DEPRECATED> */
.lm-Menu-itemLabel {
  display: table-cell;
  text-align: left;
}


/* <DEPRECATED> */ .p-Menu-itemShortcut, /* </DEPRECATED> */
.lm-Menu-itemShortcut {
  display: table-cell;
  text-align: right;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-MenuBar, /* </DEPRECATED> */
.lm-MenuBar {
  outline: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-MenuBar-content, /* </DEPRECATED> */
.lm-MenuBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: row;
  list-style-type: none;
}


/* <DEPRECATED> */ .p--MenuBar-item, /* </DEPRECATED> */
.lm-MenuBar-item {
  box-sizing: border-box;
}


/* <DEPRECATED> */
.p-MenuBar-itemIcon,
.p-MenuBar-itemLabel,
/* </DEPRECATED> */
.lm-MenuBar-itemIcon,
.lm-MenuBar-itemLabel {
  display: inline-block;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-ScrollBar, /* </DEPRECATED> */
.lm-ScrollBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='horizontal'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-ScrollBar[data-orientation='vertical'],
/* </DEPRECATED> */
.lm-ScrollBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-ScrollBar-button, /* </DEPRECATED> */
.lm-ScrollBar-button {
  box-sizing: border-box;
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-track, /* </DEPRECATED> */
.lm-ScrollBar-track {
  box-sizing: border-box;
  position: relative;
  overflow: hidden;
  flex: 1 1 auto;
}


/* <DEPRECATED> */ .p-ScrollBar-thumb, /* </DEPRECATED> */
.lm-ScrollBar-thumb {
  box-sizing: border-box;
  position: absolute;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-SplitPanel-child, /* </DEPRECATED> */
.lm-SplitPanel-child {
  z-index: 0;
}


/* <DEPRECATED> */ .p-SplitPanel-handle, /* </DEPRECATED> */
.lm-SplitPanel-handle {
  z-index: 1;
}


/* <DEPRECATED> */ .p-SplitPanel-handle.p-mod-hidden, /* </DEPRECATED> */
.lm-SplitPanel-handle.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-SplitPanel-handle:after, /* </DEPRECATED> */
.lm-SplitPanel-handle:after {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  content: '';
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle {
  cursor: ew-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle {
  cursor: ns-resize;
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='horizontal'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='horizontal'] > .lm-SplitPanel-handle:after {
  left: 50%;
  min-width: 8px;
  transform: translateX(-50%);
}


/* <DEPRECATED> */
.p-SplitPanel[data-orientation='vertical'] > .p-SplitPanel-handle:after,
/* </DEPRECATED> */
.lm-SplitPanel[data-orientation='vertical'] > .lm-SplitPanel-handle:after {
  top: 50%;
  min-height: 8px;
  transform: translateY(-50%);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabBar, /* </DEPRECATED> */
.lm-TabBar {
  display: flex;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='horizontal'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] {
  flex-direction: row;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='vertical'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-content, /* </DEPRECATED> */
.lm-TabBar-content {
  margin: 0;
  padding: 0;
  display: flex;
  flex: 1 1 auto;
  list-style-type: none;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='horizontal'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='horizontal'] > .lm-TabBar-content {
  flex-direction: row;
}


/* <DEPRECATED> */
.p-TabBar[data-orientation='vertical'] > .p-TabBar-content,
/* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] > .lm-TabBar-content {
  flex-direction: column;
}


/* <DEPRECATED> */ .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar-tab {
  display: flex;
  flex-direction: row;
  box-sizing: border-box;
  overflow: hidden;
}


/* <DEPRECATED> */
.p-TabBar-tabIcon,
.p-TabBar-tabCloseIcon,
/* </DEPRECATED> */
.lm-TabBar-tabIcon,
.lm-TabBar-tabCloseIcon {
  flex: 0 0 auto;
}


/* <DEPRECATED> */ .p-TabBar-tabLabel, /* </DEPRECATED> */
.lm-TabBar-tabLabel {
  flex: 1 1 auto;
  overflow: hidden;
  white-space: nowrap;
}


/* <DEPRECATED> */ .p-TabBar-tab.p-mod-hidden, /* </DEPRECATED> */
.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}


/* <DEPRECATED> */ .p-TabBar.p-mod-dragging .p-TabBar-tab, /* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab {
  position: relative;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='horizontal'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='horizontal'] .lm-TabBar-tab {
  left: 0;
  transition: left 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging[data-orientation='vertical'] .p-TabBar-tab,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging[data-orientation='vertical'] .lm-TabBar-tab {
  top: 0;
  transition: top 150ms ease;
}


/* <DEPRECATED> */
.p-TabBar.p-mod-dragging .p-TabBar-tab.p-mod-dragging
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ .p-TabPanel-tabBar, /* </DEPRECATED> */
.lm-TabPanel-tabBar {
  z-index: 1;
}


/* <DEPRECATED> */ .p-TabPanel-stackedPanel, /* </DEPRECATED> */
.lm-TabPanel-stackedPanel {
  z-index: 0;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/

@charset "UTF-8";
/*!

Copyright 2015-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
html{
  -webkit-box-sizing:border-box;
          box-sizing:border-box; }

*,
*::before,
*::after{
  -webkit-box-sizing:inherit;
          box-sizing:inherit; }

body{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400;
  color:#182026;
  font-family:-apple-system, "BlinkMacSystemFont", "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Open Sans", "Helvetica Neue", "Icons16", sans-serif; }

p{
  margin-top:0;
  margin-bottom:10px; }

small{
  font-size:12px; }

strong{
  font-weight:600; }

::-moz-selection{
  background:rgba(125, 188, 255, 0.6); }

::selection{
  background:rgba(125, 188, 255, 0.6); }
.bp3-heading{
  color:#182026;
  font-weight:600;
  margin:0 0 10px;
  padding:0; }
  .bp3-dark .bp3-heading{
    color:#f5f8fa; }

h1.bp3-heading, .bp3-running-text h1{
  line-height:40px;
  font-size:36px; }

h2.bp3-heading, .bp3-running-text h2{
  line-height:32px;
  font-size:28px; }

h3.bp3-heading, .bp3-running-text h3{
  line-height:25px;
  font-size:22px; }

h4.bp3-heading, .bp3-running-text h4{
  line-height:21px;
  font-size:18px; }

h5.bp3-heading, .bp3-running-text h5{
  line-height:19px;
  font-size:16px; }

h6.bp3-heading, .bp3-running-text h6{
  line-height:16px;
  font-size:14px; }
.bp3-ui-text{
  text-transform:none;
  line-height:1.28581;
  letter-spacing:0;
  font-size:14px;
  font-weight:400; }

.bp3-monospace-text{
  text-transform:none;
  font-family:monospace; }

.bp3-text-muted{
  color:#5c7080; }
  .bp3-dark .bp3-text-muted{
    color:#a7b6c2; }

.bp3-text-disabled{
  color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-text-disabled{
    color:rgba(167, 182, 194, 0.6); }

.bp3-text-overflow-ellipsis{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal; }
.bp3-running-text{
  line-height:1.5;
  font-size:14px; }
  .bp3-running-text h1{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h1{
      color:#f5f8fa; }
  .bp3-running-text h2{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h2{
      color:#f5f8fa; }
  .bp3-running-text h3{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h3{
      color:#f5f8fa; }
  .bp3-running-text h4{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h4{
      color:#f5f8fa; }
  .bp3-running-text h5{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h5{
      color:#f5f8fa; }
  .bp3-running-text h6{
    color:#182026;
    font-weight:600;
    margin-top:40px;
    margin-bottom:20px; }
    .bp3-dark .bp3-running-text h6{
      color:#f5f8fa; }
  .bp3-running-text hr{
    margin:20px 0;
    border:none;
    border-bottom:1px solid rgba(16, 22, 26, 0.15); }
    .bp3-dark .bp3-running-text hr{
      border-color:rgba(255, 255, 255, 0.15); }
  .bp3-running-text p{
    margin:0 0 10px;
    padding:0; }

.bp3-text-large{
  font-size:16px; }

.bp3-text-small{
  font-size:12px; }
a{
  text-decoration:none;
  color:#106ba3; }
  a:hover{
    cursor:pointer;
    text-decoration:underline;
    color:#106ba3; }
  a .bp3-icon, a .bp3-icon-standard, a .bp3-icon-large{
    color:inherit; }
  a code,
  .bp3-dark a code{
    color:inherit; }
  .bp3-dark a,
  .bp3-dark a:hover{
    color:#48aff0; }
    .bp3-dark a .bp3-icon, .bp3-dark a .bp3-icon-standard, .bp3-dark a .bp3-icon-large,
    .bp3-dark a:hover .bp3-icon,
    .bp3-dark a:hover .bp3-icon-standard,
    .bp3-dark a:hover .bp3-icon-large{
      color:inherit; }
.bp3-running-text code, .bp3-code{
  text-transform:none;
  font-family:monospace;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
  background:rgba(255, 255, 255, 0.7);
  padding:2px 5px;
  color:#5c7080;
  font-size:smaller; }
  .bp3-dark .bp3-running-text code, .bp3-running-text .bp3-dark code, .bp3-dark .bp3-code{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#a7b6c2; }
  .bp3-running-text a > code, a > .bp3-code{
    color:#137cbd; }
    .bp3-dark .bp3-running-text a > code, .bp3-running-text .bp3-dark a > code, .bp3-dark a > .bp3-code{
      color:inherit; }

.bp3-running-text pre, .bp3-code-block{
  text-transform:none;
  font-family:monospace;
  display:block;
  margin:10px 0;
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
  background:rgba(255, 255, 255, 0.7);
  padding:13px 15px 12px;
  line-height:1.4;
  color:#182026;
  font-size:13px;
  word-break:break-all;
  word-wrap:break-word; }
  .bp3-dark .bp3-running-text pre, .bp3-running-text .bp3-dark pre, .bp3-dark .bp3-code-block{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
  .bp3-running-text pre > code, .bp3-code-block > code{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    padding:0;
    color:inherit;
    font-size:inherit; }

.bp3-running-text kbd, .bp3-key{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  min-width:24px;
  height:24px;
  padding:3px 6px;
  vertical-align:middle;
  line-height:24px;
  color:#5c7080;
  font-family:inherit;
  font-size:12px; }
  .bp3-running-text kbd .bp3-icon, .bp3-key .bp3-icon, .bp3-running-text kbd .bp3-icon-standard, .bp3-key .bp3-icon-standard, .bp3-running-text kbd .bp3-icon-large, .bp3-key .bp3-icon-large{
    margin-right:5px; }
  .bp3-dark .bp3-running-text kbd, .bp3-running-text .bp3-dark kbd, .bp3-dark .bp3-key{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
    background:#394b59;
    color:#a7b6c2; }
.bp3-running-text blockquote, .bp3-blockquote{
  margin:0 0 10px;
  border-left:solid 4px rgba(167, 182, 194, 0.5);
  padding:0 20px; }
  .bp3-dark .bp3-running-text blockquote, .bp3-running-text .bp3-dark blockquote, .bp3-dark .bp3-blockquote{
    border-color:rgba(115, 134, 148, 0.5); }
.bp3-running-text ul,
.bp3-running-text ol, .bp3-list{
  margin:10px 0;
  padding-left:30px; }
  .bp3-running-text ul li:not(:last-child), .bp3-running-text ol li:not(:last-child), .bp3-list li:not(:last-child){
    margin-bottom:5px; }
  .bp3-running-text ul ol, .bp3-running-text ol ol, .bp3-list ol,
  .bp3-running-text ul ul,
  .bp3-running-text ol ul,
  .bp3-list ul{
    margin-top:5px; }

.bp3-list-unstyled{
  margin:0;
  padding:0;
  list-style:none; }
  .bp3-list-unstyled li{
    padding:0; }
.bp3-rtl{
  text-align:right; }

.bp3-dark{
  color:#f5f8fa; }

:focus{
  outline:rgba(19, 124, 189, 0.6) auto 2px;
  outline-offset:2px;
  -moz-outline-radius:6px; }

.bp3-focus-disabled :focus{
  outline:none !important; }
  .bp3-focus-disabled :focus ~ .bp3-control-indicator{
    outline:none !important; }

.bp3-alert{
  max-width:400px;
  padding:20px; }

.bp3-alert-body{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-alert-body .bp3-icon{
    margin-top:0;
    margin-right:20px;
    font-size:40px; }

.bp3-alert-footer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:reverse;
      -ms-flex-direction:row-reverse;
          flex-direction:row-reverse;
  margin-top:10px; }
  .bp3-alert-footer .bp3-button{
    margin-left:10px; }
.bp3-breadcrumbs{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:wrap;
      flex-wrap:wrap;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  margin:0;
  cursor:default;
  height:30px;
  padding:0;
  list-style:none; }
  .bp3-breadcrumbs > li{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }
    .bp3-breadcrumbs > li::after{
      display:block;
      margin:0 5px;
      background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.71 7.29l-4-4a1.003 1.003 0 0 0-1.42 1.42L8.59 8 5.3 11.29c-.19.18-.3.43-.3.71a1.003 1.003 0 0 0 1.71.71l4-4c.18-.18.29-.43.29-.71 0-.28-.11-.53-.29-.71z' fill='%235C7080'/%3e%3c/svg%3e");
      width:16px;
      height:16px;
      content:""; }
    .bp3-breadcrumbs > li:last-of-type::after{
      display:none; }

.bp3-breadcrumb,
.bp3-breadcrumb-current,
.bp3-breadcrumbs-collapsed{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  font-size:16px; }

.bp3-breadcrumb,
.bp3-breadcrumbs-collapsed{
  color:#5c7080; }

.bp3-breadcrumb:hover{
  text-decoration:none; }

.bp3-breadcrumb.bp3-disabled{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-breadcrumb .bp3-icon{
  margin-right:5px; }

.bp3-breadcrumb-current{
  color:inherit;
  font-weight:600; }
  .bp3-breadcrumb-current .bp3-input{
    vertical-align:baseline;
    font-size:inherit;
    font-weight:inherit; }

.bp3-breadcrumbs-collapsed{
  margin-right:2px;
  border:none;
  border-radius:3px;
  background:#ced9e0;
  cursor:pointer;
  padding:1px 5px;
  vertical-align:text-bottom; }
  .bp3-breadcrumbs-collapsed::before{
    display:block;
    background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cg fill='%235C7080'%3e%3ccircle cx='2' cy='8.03' r='2'/%3e%3ccircle cx='14' cy='8.03' r='2'/%3e%3ccircle cx='8' cy='8.03' r='2'/%3e%3c/g%3e%3c/svg%3e") center no-repeat;
    width:16px;
    height:16px;
    content:""; }
  .bp3-breadcrumbs-collapsed:hover{
    background:#bfccd6;
    text-decoration:none;
    color:#182026; }

.bp3-dark .bp3-breadcrumb,
.bp3-dark .bp3-breadcrumbs-collapsed{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumbs > li::after{
  color:#a7b6c2; }

.bp3-dark .bp3-breadcrumb.bp3-disabled{
  color:rgba(167, 182, 194, 0.6); }

.bp3-dark .bp3-breadcrumb-current{
  color:#f5f8fa; }

.bp3-dark .bp3-breadcrumbs-collapsed{
  background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-breadcrumbs-collapsed:hover{
    background:rgba(16, 22, 26, 0.6);
    color:#f5f8fa; }
.bp3-button{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  min-width:30px;
  min-height:30px; }
  .bp3-button > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-button > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-button::before,
  .bp3-button > *{
    margin-right:7px; }
  .bp3-button:empty::before,
  .bp3-button > :last-child{
    margin-right:0; }
  .bp3-button:empty{
    padding:0 !important; }
  .bp3-button:disabled, .bp3-button.bp3-disabled{
    cursor:not-allowed; }
  .bp3-button.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button.bp3-align-right,
  .bp3-align-right .bp3-button{
    text-align:right; }
  .bp3-button.bp3-align-left,
  .bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026; }
    .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-button:not([class*="bp3-intent-"]):active, .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active:hover, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-button.bp3-intent-primary{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover, .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#106ba3; }
    .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0e5a8a;
      background-image:none; }
    .bp3-button.bp3-intent-primary:disabled, .bp3-button.bp3-intent-primary.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(19, 124, 189, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-success{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#0f9960;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-success:hover, .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-success:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#0d8050; }
    .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#0a6640;
      background-image:none; }
    .bp3-button.bp3-intent-success:disabled, .bp3-button.bp3-intent-success.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(15, 153, 96, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-warning{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#d9822b;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover, .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#bf7326; }
    .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a66321;
      background-image:none; }
    .bp3-button.bp3-intent-warning:disabled, .bp3-button.bp3-intent-warning.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(217, 130, 43, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-danger{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#db3737;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover, .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
      background-color:#c23030; }
    .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#a82a2a;
      background-image:none; }
    .bp3-button.bp3-intent-danger:disabled, .bp3-button.bp3-intent-danger.bp3-disabled{
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(219, 55, 55, 0.5);
      background-image:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
    stroke:#ffffff; }
  .bp3-button.bp3-large,
  .bp3-large .bp3-button{
    min-width:40px;
    min-height:40px;
    padding:5px 15px;
    font-size:16px; }
    .bp3-button.bp3-large::before,
    .bp3-button.bp3-large > *,
    .bp3-large .bp3-button::before,
    .bp3-large .bp3-button > *{
      margin-right:10px; }
    .bp3-button.bp3-large:empty::before,
    .bp3-button.bp3-large > :last-child,
    .bp3-large .bp3-button:empty::before,
    .bp3-large .bp3-button > :last-child{
      margin-right:0; }
  .bp3-button.bp3-small,
  .bp3-small .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-button.bp3-loading{
    position:relative; }
    .bp3-button.bp3-loading[class*="bp3-icon-"]::before{
      visibility:hidden; }
    .bp3-button.bp3-loading .bp3-button-spinner{
      position:absolute;
      margin:0; }
    .bp3-button.bp3-loading > :not(.bp3-button-spinner){
      visibility:hidden; }
  .bp3-button[class*="bp3-icon-"]::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    color:#5c7080; }
  .bp3-button .bp3-icon, .bp3-button .bp3-icon-standard, .bp3-button .bp3-icon-large{
    color:#5c7080; }
    .bp3-button .bp3-icon.bp3-align-right, .bp3-button .bp3-icon-standard.bp3-align-right, .bp3-button .bp3-icon-large.bp3-align-right{
      margin-left:7px; }
  .bp3-button .bp3-icon:first-child:last-child,
  .bp3-button .bp3-spinner + .bp3-icon:last-child{
    margin:0 -7px; }
  .bp3-dark .bp3-button:not([class*="bp3-intent-"]){
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover, .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"])[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-button:not([class*="bp3-intent-"]) .bp3-icon-large{
      color:#a7b6c2; }
  .bp3-dark .bp3-button[class*="bp3-intent-"]{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:active, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button[class*="bp3-intent-"]:disabled, .bp3-dark .bp3-button[class*="bp3-intent-"].bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-image:none;
      color:rgba(255, 255, 255, 0.3); }
    .bp3-dark .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
      stroke:#8a9ba8; }
  .bp3-button:disabled::before,
  .bp3-button:disabled .bp3-icon, .bp3-button:disabled .bp3-icon-standard, .bp3-button:disabled .bp3-icon-large, .bp3-button.bp3-disabled::before,
  .bp3-button.bp3-disabled .bp3-icon, .bp3-button.bp3-disabled .bp3-icon-standard, .bp3-button.bp3-disabled .bp3-icon-large, .bp3-button[class*="bp3-intent-"]::before,
  .bp3-button[class*="bp3-intent-"] .bp3-icon, .bp3-button[class*="bp3-intent-"] .bp3-icon-standard, .bp3-button[class*="bp3-intent-"] .bp3-icon-large{
    color:inherit !important; }
  .bp3-button.bp3-minimal{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button.bp3-minimal:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button.bp3-minimal:active, .bp3-button.bp3-minimal.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button.bp3-minimal:disabled, .bp3-button.bp3-minimal:disabled:hover, .bp3-button.bp3-minimal.bp3-disabled, .bp3-button.bp3-minimal.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-minimal{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-minimal:hover, .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button.bp3-minimal:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-minimal:disabled, .bp3-dark .bp3-button.bp3-minimal:disabled:hover, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover, .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover, .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover, .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover, .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-minimal.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }

a.bp3-button{
  text-align:center;
  text-decoration:none;
  -webkit-transition:none;
  transition:none; }
  a.bp3-button, a.bp3-button:hover, a.bp3-button:active{
    color:#182026; }
  a.bp3-button.bp3-disabled{
    color:rgba(92, 112, 128, 0.6); }

.bp3-button-text{
  -webkit-box-flex:0;
      -ms-flex:0 1 auto;
          flex:0 1 auto; }

.bp3-button.bp3-align-left .bp3-button-text, .bp3-button.bp3-align-right .bp3-button-text,
.bp3-button-group.bp3-align-left .bp3-button-text,
.bp3-button-group.bp3-align-right .bp3-button-text{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto; }
.bp3-button-group{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex; }
  .bp3-button-group .bp3-button{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    position:relative;
    z-index:4; }
    .bp3-button-group .bp3-button:focus{
      z-index:5; }
    .bp3-button-group .bp3-button:hover{
      z-index:6; }
    .bp3-button-group .bp3-button:active, .bp3-button-group .bp3-button.bp3-active{
      z-index:7; }
    .bp3-button-group .bp3-button:disabled, .bp3-button-group .bp3-button.bp3-disabled{
      z-index:3; }
    .bp3-button-group .bp3-button[class*="bp3-intent-"]{
      z-index:9; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:focus{
        z-index:10; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:hover{
        z-index:11; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:active, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-active{
        z-index:12; }
      .bp3-button-group .bp3-button[class*="bp3-intent-"]:disabled, .bp3-button-group .bp3-button[class*="bp3-intent-"].bp3-disabled{
        z-index:8; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:first-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:first-child){
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:-1px;
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-button-group.bp3-minimal .bp3-button{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none; }
    .bp3-button-group.bp3-minimal .bp3-button:hover{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(167, 182, 194, 0.3);
      text-decoration:none;
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(115, 134, 148, 0.3);
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button-group.bp3-minimal .bp3-button{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:inherit; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
        background:none;
        cursor:not-allowed;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
      color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
      color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:none;
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
  .bp3-button-group .bp3-popover-wrapper,
  .bp3-button-group .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-button-group .bp3-button.bp3-fill,
  .bp3-button-group.bp3-fill .bp3-button:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-button-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    vertical-align:top; }
    .bp3-button-group.bp3-vertical.bp3-fill{
      width:unset;
      height:100%; }
    .bp3-button-group.bp3-vertical .bp3-button{
      margin-right:0 !important;
      width:100%; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:first-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:first-child{
      border-radius:3px 3px 0 0; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:last-child .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:last-child{
      border-radius:0 0 3px 3px; }
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
    .bp3-button-group.bp3-vertical:not(.bp3-minimal) > .bp3-button:not(:last-child){
      margin-bottom:-1px; }
  .bp3-button-group.bp3-align-left .bp3-button{
    text-align:left; }
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    margin-right:1px; }
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-dark .bp3-button-group.bp3-vertical > .bp3-button:not(:last-child){
    margin-bottom:1px; }
.bp3-callout{
  line-height:1.5;
  font-size:14px;
  position:relative;
  border-radius:3px;
  background-color:rgba(138, 155, 168, 0.15);
  width:100%;
  padding:10px 12px 9px; }
  .bp3-callout[class*="bp3-icon-"]{
    padding-left:40px; }
    .bp3-callout[class*="bp3-icon-"]::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout.bp3-callout-icon{
    padding-left:40px; }
    .bp3-callout.bp3-callout-icon > .bp3-icon:first-child{
      position:absolute;
      top:10px;
      left:10px;
      color:#5c7080; }
  .bp3-callout .bp3-heading{
    margin-top:0;
    margin-bottom:5px;
    line-height:20px; }
    .bp3-callout .bp3-heading:last-child{
      margin-bottom:0; }
  .bp3-dark .bp3-callout{
    background-color:rgba(138, 155, 168, 0.2); }
    .bp3-dark .bp3-callout[class*="bp3-icon-"]::before{
      color:#a7b6c2; }
  .bp3-callout.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15); }
    .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-primary .bp3-heading{
      color:#106ba3; }
    .bp3-dark .bp3-callout.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-primary[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-primary > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-primary .bp3-heading{
        color:#48aff0; }
  .bp3-callout.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15); }
    .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-success .bp3-heading{
      color:#0d8050; }
    .bp3-dark .bp3-callout.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-success[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-success > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-success .bp3-heading{
        color:#3dcc91; }
  .bp3-callout.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15); }
    .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-warning .bp3-heading{
      color:#bf7326; }
    .bp3-dark .bp3-callout.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-warning[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-warning > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-warning .bp3-heading{
        color:#ffb366; }
  .bp3-callout.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15); }
    .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
    .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
    .bp3-callout.bp3-intent-danger .bp3-heading{
      color:#c23030; }
    .bp3-dark .bp3-callout.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25); }
      .bp3-dark .bp3-callout.bp3-intent-danger[class*="bp3-icon-"]::before,
      .bp3-dark .bp3-callout.bp3-intent-danger > .bp3-icon:first-child,
      .bp3-dark .bp3-callout.bp3-intent-danger .bp3-heading{
        color:#ff7373; }
  .bp3-running-text .bp3-callout{
    margin:20px 0; }
.bp3-card{
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
  background-color:#ffffff;
  padding:20px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-card.bp3-dark,
  .bp3-dark .bp3-card{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
    background-color:#30404d; }

.bp3-elevation-0{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }
  .bp3-elevation-0.bp3-dark,
  .bp3-dark .bp3-elevation-0{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

.bp3-elevation-1{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-1.bp3-dark,
  .bp3-dark .bp3-elevation-1{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-elevation-2{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 1px 1px rgba(16, 22, 26, 0.2), 0 2px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-2.bp3-dark,
  .bp3-dark .bp3-elevation-2{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.4), 0 2px 6px rgba(16, 22, 26, 0.4); }

.bp3-elevation-3{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-3.bp3-dark,
  .bp3-dark .bp3-elevation-3{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-elevation-4{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2); }
  .bp3-elevation-4.bp3-dark,
  .bp3-dark .bp3-elevation-4{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:hover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  cursor:pointer; }
  .bp3-card.bp3-interactive:hover.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }

.bp3-card.bp3-interactive:active{
  opacity:0.9;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  -webkit-transition-duration:0;
          transition-duration:0; }
  .bp3-card.bp3-interactive:active.bp3-dark,
  .bp3-dark .bp3-card.bp3-interactive:active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-collapse{
  height:0;
  overflow-y:hidden;
  -webkit-transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:height 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-collapse .bp3-collapse-body{
    -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-collapse .bp3-collapse-body[aria-hidden="true"]{
      display:none; }

.bp3-context-menu .bp3-popover-target{
  display:block; }

.bp3-context-menu-popover-target{
  position:fixed; }

.bp3-divider{
  margin:5px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  border-bottom:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-dialog-container{
  opacity:1;
  -webkit-transform:scale(1);
          transform:scale(1);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  min-height:100%;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-dialog-container.bp3-overlay-enter > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5); }
  .bp3-dialog-container.bp3-overlay-enter-active > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear-active > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-dialog-container.bp3-overlay-exit > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-dialog-container.bp3-overlay-exit-active > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5);
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }

.bp3-dialog{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:30px 0;
  border-radius:6px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ebf1f5;
  width:500px;
  padding-bottom:20px;
  pointer-events:all;
  -webkit-user-select:text;
     -moz-user-select:text;
      -ms-user-select:text;
          user-select:text; }
  .bp3-dialog:focus{
    outline:0; }
  .bp3-dialog.bp3-dark,
  .bp3-dark .bp3-dialog{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#293742;
    color:#f5f8fa; }

.bp3-dialog-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border-radius:6px 6px 0 0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  background:#ffffff;
  min-height:40px;
  padding-right:5px;
  padding-left:20px; }
  .bp3-dialog-header .bp3-icon-large,
  .bp3-dialog-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-dialog-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-dialog-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-dialog-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
    background:#30404d; }
    .bp3-dark .bp3-dialog-header .bp3-icon-large,
    .bp3-dark .bp3-dialog-header .bp3-icon{
      color:#a7b6c2; }

.bp3-dialog-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  margin:20px;
  line-height:18px; }

.bp3-dialog-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  margin:0 20px; }

.bp3-dialog-footer-actions{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:end;
      -ms-flex-pack:end;
          justify-content:flex-end; }
  .bp3-dialog-footer-actions .bp3-button{
    margin-left:10px; }
.bp3-drawer{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  padding:0; }
  .bp3-drawer:focus{
    outline:0; }
  .bp3-drawer.bp3-position-top{
    top:0;
    right:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter, .bp3-drawer.bp3-position-top.bp3-overlay-appear{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%); }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter-active, .bp3-drawer.bp3-position-top.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit-active{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-bottom{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter-active, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-left{
    top:0;
    bottom:0;
    left:0;
    width:50%; }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter, .bp3-drawer.bp3-position-left.bp3-overlay-appear{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%); }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter-active, .bp3-drawer.bp3-position-left.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit-active{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-position-right{
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter, .bp3-drawer.bp3-position-right.bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter-active, .bp3-drawer.bp3-position-right.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right):not(.bp3-vertical){
    top:0;
    right:0;
    bottom:0;
    width:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right).bp3-vertical{
    right:0;
    bottom:0;
    left:0;
    height:50%; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-enter-active, .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
      -webkit-transition-delay:0;
              transition-delay:0; }
  .bp3-drawer.bp3-dark,
  .bp3-dark .bp3-drawer{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background:#30404d;
    color:#f5f8fa; }

.bp3-drawer-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border-radius:0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  min-height:40px;
  padding:5px;
  padding-left:20px; }
  .bp3-drawer-header .bp3-icon-large,
  .bp3-drawer-header .bp3-icon{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px;
    color:#5c7080; }
  .bp3-drawer-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    margin:0;
    line-height:inherit; }
    .bp3-drawer-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-drawer-header{
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-drawer-header .bp3-icon-large,
    .bp3-dark .bp3-drawer-header .bp3-icon{
      color:#a7b6c2; }

.bp3-drawer-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  overflow:auto;
  line-height:18px; }

.bp3-drawer-footer{
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
  padding:10px 20px; }
  .bp3-dark .bp3-drawer-footer{
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4); }
.bp3-editable-text{
  display:inline-block;
  position:relative;
  cursor:text;
  max-width:100%;
  vertical-align:top;
  white-space:nowrap; }
  .bp3-editable-text::before{
    position:absolute;
    top:-3px;
    right:-3px;
    bottom:-3px;
    left:-3px;
    border-radius:3px;
    content:"";
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
  .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#137cbd; }
  .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(19, 124, 189, 0.4); }
  .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#0f9960; }
  .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px rgba(15, 153, 96, 0.4); }
  .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#d9822b; }
  .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px rgba(217, 130, 43, 0.4); }
  .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-input,
  .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#db3737; }
  .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px rgba(219, 55, 55, 0.4); }
  .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-editable-text:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(255, 255, 255, 0.15); }
  .bp3-dark .bp3-editable-text.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
  .bp3-dark .bp3-editable-text.bp3-disabled::before{
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary .bp3-editable-text-content{
    color:#48aff0; }
  .bp3-dark .bp3-editable-text.bp3-intent-primary:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4);
            box-shadow:0 0 0 0 rgba(72, 175, 240, 0), 0 0 0 0 rgba(72, 175, 240, 0), inset 0 0 0 1px rgba(72, 175, 240, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-primary.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #48aff0, 0 0 0 3px rgba(72, 175, 240, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success .bp3-editable-text-content{
    color:#3dcc91; }
  .bp3-dark .bp3-editable-text.bp3-intent-success:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4);
            box-shadow:0 0 0 0 rgba(61, 204, 145, 0), 0 0 0 0 rgba(61, 204, 145, 0), inset 0 0 0 1px rgba(61, 204, 145, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-success.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #3dcc91, 0 0 0 3px rgba(61, 204, 145, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning .bp3-editable-text-content{
    color:#ffb366; }
  .bp3-dark .bp3-editable-text.bp3-intent-warning:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4);
            box-shadow:0 0 0 0 rgba(255, 179, 102, 0), 0 0 0 0 rgba(255, 179, 102, 0), inset 0 0 0 1px rgba(255, 179, 102, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-warning.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ffb366, 0 0 0 3px rgba(255, 179, 102, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger .bp3-editable-text-content{
    color:#ff7373; }
  .bp3-dark .bp3-editable-text.bp3-intent-danger:hover::before{
    -webkit-box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4);
            box-shadow:0 0 0 0 rgba(255, 115, 115, 0), 0 0 0 0 rgba(255, 115, 115, 0), inset 0 0 0 1px rgba(255, 115, 115, 0.4); }
  .bp3-dark .bp3-editable-text.bp3-intent-danger.bp3-editable-text-editing::before{
    -webkit-box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #ff7373, 0 0 0 3px rgba(255, 115, 115, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-editable-text-input,
.bp3-editable-text-content{
  display:inherit;
  position:relative;
  min-width:inherit;
  max-width:inherit;
  vertical-align:top;
  text-transform:inherit;
  letter-spacing:inherit;
  color:inherit;
  font:inherit;
  resize:none; }

.bp3-editable-text-input{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  width:100%;
  padding:0;
  white-space:pre-wrap; }
  .bp3-editable-text-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-editable-text-input:focus{
    outline:none; }
  .bp3-editable-text-input::-ms-clear{
    display:none; }

.bp3-editable-text-content{
  overflow:hidden;
  padding-right:2px;
  text-overflow:ellipsis;
  white-space:pre; }
  .bp3-editable-text-editing > .bp3-editable-text-content{
    position:absolute;
    left:0;
    visibility:hidden; }
  .bp3-editable-text-placeholder > .bp3-editable-text-content{
    color:rgba(92, 112, 128, 0.6); }
    .bp3-dark .bp3-editable-text-placeholder > .bp3-editable-text-content{
      color:rgba(167, 182, 194, 0.6); }

.bp3-editable-text.bp3-multiline{
  display:block; }
  .bp3-editable-text.bp3-multiline .bp3-editable-text-content{
    overflow:auto;
    white-space:pre-wrap;
    word-wrap:break-word; }
.bp3-control-group{
  -webkit-transform:translateZ(0);
          transform:translateZ(0);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:stretch;
      -ms-flex-align:stretch;
          align-items:stretch; }
  .bp3-control-group > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select,
  .bp3-control-group .bp3-input,
  .bp3-control-group .bp3-select{
    position:relative; }
  .bp3-control-group .bp3-input{
    z-index:2;
    border-radius:inherit; }
    .bp3-control-group .bp3-input:focus{
      z-index:14;
      border-radius:3px; }
    .bp3-control-group .bp3-input[class*="bp3-intent"]{
      z-index:13; }
      .bp3-control-group .bp3-input[class*="bp3-intent"]:focus{
        z-index:15; }
    .bp3-control-group .bp3-input[readonly], .bp3-control-group .bp3-input:disabled, .bp3-control-group .bp3-input.bp3-disabled{
      z-index:1; }
  .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input{
    z-index:13; }
    .bp3-control-group .bp3-input-group[class*="bp3-intent"] .bp3-input:focus{
      z-index:15; }
  .bp3-control-group .bp3-button,
  .bp3-control-group .bp3-html-select select,
  .bp3-control-group .bp3-select select{
    -webkit-transform:translateZ(0);
            transform:translateZ(0);
    z-index:4;
    border-radius:inherit; }
    .bp3-control-group .bp3-button:focus,
    .bp3-control-group .bp3-html-select select:focus,
    .bp3-control-group .bp3-select select:focus{
      z-index:5; }
    .bp3-control-group .bp3-button:hover,
    .bp3-control-group .bp3-html-select select:hover,
    .bp3-control-group .bp3-select select:hover{
      z-index:6; }
    .bp3-control-group .bp3-button:active,
    .bp3-control-group .bp3-html-select select:active,
    .bp3-control-group .bp3-select select:active{
      z-index:7; }
    .bp3-control-group .bp3-button[readonly], .bp3-control-group .bp3-button:disabled, .bp3-control-group .bp3-button.bp3-disabled,
    .bp3-control-group .bp3-html-select select[readonly],
    .bp3-control-group .bp3-html-select select:disabled,
    .bp3-control-group .bp3-html-select select.bp3-disabled,
    .bp3-control-group .bp3-select select[readonly],
    .bp3-control-group .bp3-select select:disabled,
    .bp3-control-group .bp3-select select.bp3-disabled{
      z-index:3; }
    .bp3-control-group .bp3-button[class*="bp3-intent"],
    .bp3-control-group .bp3-html-select select[class*="bp3-intent"],
    .bp3-control-group .bp3-select select[class*="bp3-intent"]{
      z-index:9; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:focus,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:focus{
        z-index:10; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:hover,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:hover{
        z-index:11; }
      .bp3-control-group .bp3-button[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:active,
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:active{
        z-index:12; }
      .bp3-control-group .bp3-button[class*="bp3-intent"][readonly], .bp3-control-group .bp3-button[class*="bp3-intent"]:disabled, .bp3-control-group .bp3-button[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-html-select select[class*="bp3-intent"].bp3-disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"][readonly],
      .bp3-control-group .bp3-select select[class*="bp3-intent"]:disabled,
      .bp3-control-group .bp3-select select[class*="bp3-intent"].bp3-disabled{
        z-index:8; }
  .bp3-control-group .bp3-input-group > .bp3-icon,
  .bp3-control-group .bp3-input-group > .bp3-button,
  .bp3-control-group .bp3-input-group > .bp3-input-action{
    z-index:16; }
  .bp3-control-group .bp3-select::after,
  .bp3-control-group .bp3-html-select::after,
  .bp3-control-group .bp3-select > .bp3-icon,
  .bp3-control-group .bp3-html-select > .bp3-icon{
    z-index:17; }
  .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:-1px; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > *{
    margin-right:0; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > .bp3-button + .bp3-button{
    margin-left:1px; }
  .bp3-control-group .bp3-popover-wrapper,
  .bp3-control-group .bp3-popover-target{
    border-radius:inherit; }
  .bp3-control-group > :first-child{
    border-radius:3px 0 0 3px; }
  .bp3-control-group > :last-child{
    margin-right:0;
    border-radius:0 3px 3px 0; }
  .bp3-control-group > :only-child{
    margin-right:0;
    border-radius:3px; }
  .bp3-control-group .bp3-input-group .bp3-button{
    border-radius:3px; }
  .bp3-control-group > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-fill > *:not(.bp3-fixed){
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto; }
  .bp3-control-group.bp3-vertical{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-control-group.bp3-vertical > *{
      margin-top:-1px; }
    .bp3-control-group.bp3-vertical > :first-child{
      margin-top:0;
      border-radius:3px 3px 0 0; }
    .bp3-control-group.bp3-vertical > :last-child{
      border-radius:0 0 3px 3px; }
.bp3-control{
  display:block;
  position:relative;
  margin-bottom:10px;
  cursor:pointer;
  text-transform:none; }
  .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control:hover input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control:not(.bp3-align-right){
    padding-left:26px; }
    .bp3-control:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-26px; }
  .bp3-control.bp3-align-right{
    padding-right:26px; }
    .bp3-control.bp3-align-right .bp3-control-indicator{
      margin-right:-26px; }
  .bp3-control.bp3-disabled{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-control.bp3-inline{
    display:inline-block;
    margin-right:20px; }
  .bp3-control input{
    position:absolute;
    top:0;
    left:0;
    opacity:0;
    z-index:-1; }
  .bp3-control .bp3-control-indicator{
    display:inline-block;
    position:relative;
    margin-top:-3px;
    margin-right:10px;
    border:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    cursor:pointer;
    width:1em;
    height:1em;
    vertical-align:middle;
    font-size:16px;
    -webkit-user-select:none;
       -moz-user-select:none;
        -ms-user-select:none;
            user-select:none; }
    .bp3-control .bp3-control-indicator::before{
      display:block;
      width:1em;
      height:1em;
      content:""; }
  .bp3-control:hover .bp3-control-indicator{
    background-color:#ebf1f5; }
  .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#d8e1e8; }
  .bp3-control input:disabled ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed; }
  .bp3-control input:focus ~ .bp3-control-indicator{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:2px;
    -moz-outline-radius:6px; }
  .bp3-control.bp3-align-right .bp3-control-indicator{
    float:right;
    margin-top:1px;
    margin-left:10px; }
  .bp3-control.bp3-large{
    font-size:16px; }
    .bp3-control.bp3-large:not(.bp3-align-right){
      padding-left:30px; }
      .bp3-control.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
        margin-left:-30px; }
    .bp3-control.bp3-large.bp3-align-right{
      padding-right:30px; }
      .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
        margin-right:-30px; }
    .bp3-control.bp3-large .bp3-control-indicator{
      font-size:20px; }
    .bp3-control.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-top:0; }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    color:#ffffff; }
  .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    background-color:#106ba3; }
  .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background:#0e5a8a; }
  .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(19, 124, 189, 0.5); }
  .bp3-dark .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#106ba3; }
  .bp3-dark .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(14, 90, 138, 0.5); }
  .bp3-control.bp3-checkbox .bp3-control-indicator{
    border-radius:3px; }
  .bp3-control.bp3-checkbox input:checked ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M12 5c-.28 0-.53.11-.71.29L7 9.59l-2.29-2.3a1.003 1.003 0 0 0-1.42 1.42l3 3c.18.18.43.29.71.29s.53-.11.71-.29l5-5A1.003 1.003 0 0 0 12 5z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M11 7H5c-.55 0-1 .45-1 1s.45 1 1 1h6c.55 0 1-.45 1-1s-.45-1-1-1z' fill='white'/%3e%3c/svg%3e"); }
  .bp3-control.bp3-radio .bp3-control-indicator{
    border-radius:50%; }
  .bp3-control.bp3-radio input:checked ~ .bp3-control-indicator::before{
    background-image:radial-gradient(#ffffff, #ffffff 28%, transparent 32%); }
  .bp3-control.bp3-radio input:checked:disabled ~ .bp3-control-indicator::before{
    opacity:0.5; }
  .bp3-control.bp3-radio input:focus ~ .bp3-control-indicator{
    -moz-outline-radius:16px; }
  .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(167, 182, 194, 0.5); }
  .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(115, 134, 148, 0.5); }
  .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(92, 112, 128, 0.5); }
  .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5); }
    .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5); }
    .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(255, 255, 255, 0.8); }
  .bp3-control.bp3-switch:not(.bp3-align-right){
    padding-left:38px; }
    .bp3-control.bp3-switch:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-38px; }
  .bp3-control.bp3-switch.bp3-align-right{
    padding-right:38px; }
    .bp3-control.bp3-switch.bp3-align-right .bp3-control-indicator{
      margin-right:-38px; }
  .bp3-control.bp3-switch .bp3-control-indicator{
    border:none;
    border-radius:1.75em;
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    width:auto;
    min-width:1.75em;
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-control.bp3-switch .bp3-control-indicator::before{
      position:absolute;
      left:0;
      margin:2px;
      border-radius:50%;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
      background:#ffffff;
      width:calc(1em - 4px);
      height:calc(1em - 4px);
      -webkit-transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    left:calc(100% - 1em); }
  .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right){
    padding-left:45px; }
    .bp3-control.bp3-switch.bp3-large:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-45px; }
  .bp3-control.bp3-switch.bp3-large.bp3-align-right{
    padding-right:45px; }
    .bp3-control.bp3-switch.bp3-large.bp3-align-right .bp3-control-indicator{
      margin-right:-45px; }
  .bp3-dark .bp3-control.bp3-switch input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-control.bp3-switch:hover input ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.7); }
  .bp3-dark .bp3-control.bp3-switch input:not(:disabled):active ~ .bp3-control-indicator{
    background:rgba(16, 22, 26, 0.9); }
  .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator{
    background:rgba(57, 75, 89, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator{
    background:#137cbd; }
  .bp3-dark .bp3-control.bp3-switch:hover input:checked ~ .bp3-control-indicator{
    background:#106ba3; }
  .bp3-dark .bp3-control.bp3-switch input:checked:not(:disabled):active ~ .bp3-control-indicator{
    background:#0e5a8a; }
  .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5); }
    .bp3-dark .bp3-control.bp3-switch input:checked:disabled ~ .bp3-control-indicator::before{
      background:rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch .bp3-control-indicator::before{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background:#394b59; }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-control.bp3-switch .bp3-switch-inner-text{
    text-align:center;
    font-size:0.7em; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:first-child{
    visibility:hidden;
    margin-right:1.2em;
    margin-left:0.5em;
    line-height:0; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:last-child{
    visibility:visible;
    margin-right:0.5em;
    margin-left:1.2em;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:first-child{
    visibility:visible;
    line-height:1em; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:last-child{
    visibility:hidden;
    line-height:0; }
  .bp3-dark .bp3-control{
    color:#f5f8fa; }
    .bp3-dark .bp3-control.bp3-disabled{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-control .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0)); }
    .bp3-dark .bp3-control:hover .bp3-control-indicator{
      background-color:#30404d; }
    .bp3-dark .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background:#202b33; }
    .bp3-dark .bp3-control input:disabled ~ .bp3-control-indicator{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      cursor:not-allowed; }
    .bp3-dark .bp3-control.bp3-checkbox input:disabled:checked ~ .bp3-control-indicator, .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
      color:rgba(167, 182, 194, 0.6); }
.bp3-file-input{
  display:inline-block;
  position:relative;
  cursor:pointer;
  height:30px; }
  .bp3-file-input input{
    opacity:0;
    margin:0;
    min-width:200px; }
    .bp3-file-input input:disabled + .bp3-file-upload-input,
    .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(206, 217, 224, 0.5);
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6);
      resize:none; }
      .bp3-file-input input:disabled + .bp3-file-upload-input::after,
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
        outline:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(206, 217, 224, 0.5);
        background-image:none;
        cursor:not-allowed;
        color:rgba(92, 112, 128, 0.6); }
        .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active:hover,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active:hover{
          background:rgba(206, 217, 224, 0.7); }
      .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input, .bp3-dark
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
        -webkit-box-shadow:none;
                box-shadow:none;
        background:rgba(57, 75, 89, 0.5);
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after, .bp3-dark
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
          -webkit-box-shadow:none;
                  box-shadow:none;
          background-color:rgba(57, 75, 89, 0.5);
          background-image:none;
          color:rgba(167, 182, 194, 0.6); }
          .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-dark
          .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active{
            background:rgba(57, 75, 89, 0.7); }
  .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#182026; }
  .bp3-dark .bp3-file-input.bp3-file-input-has-selection .bp3-file-upload-input{
    color:#f5f8fa; }
  .bp3-file-input.bp3-fill{
    width:100%; }
  .bp3-file-input.bp3-large,
  .bp3-large .bp3-file-input{
    height:40px; }
  .bp3-file-input .bp3-file-upload-input-custom-text::after{
    content:attr(bp3-button-text); }

.bp3-file-upload-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  position:absolute;
  top:0;
  right:0;
  left:0;
  padding-right:80px;
  color:rgba(92, 112, 128, 0.6);
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-file-upload-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-file-upload-input:focus, .bp3-file-upload-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-file-upload-input[type="search"], .bp3-file-upload-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-file-upload-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-file-upload-input:disabled, .bp3-file-upload-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-file-upload-input::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    color:#182026;
    min-width:24px;
    min-height:24px;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    position:absolute;
    top:0;
    right:0;
    margin:3px;
    border-radius:3px;
    width:70px;
    text-align:center;
    line-height:24px;
    content:"Browse"; }
    .bp3-file-upload-input::after:hover{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
      background-clip:padding-box;
      background-color:#ebf1f5; }
    .bp3-file-upload-input::after:active, .bp3-file-upload-input::after.bp3-active{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#d8e1e8;
      background-image:none; }
    .bp3-file-upload-input::after:disabled, .bp3-file-upload-input::after.bp3-disabled{
      outline:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      cursor:not-allowed;
      color:rgba(92, 112, 128, 0.6); }
      .bp3-file-upload-input::after:disabled.bp3-active, .bp3-file-upload-input::after:disabled.bp3-active:hover, .bp3-file-upload-input::after.bp3-disabled.bp3-active, .bp3-file-upload-input::after.bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-file-upload-input:hover::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-file-upload-input:active::after{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-large .bp3-file-upload-input{
    height:40px;
    line-height:40px;
    font-size:16px;
    padding-right:95px; }
    .bp3-large .bp3-file-upload-input[type="search"], .bp3-large .bp3-file-upload-input.bp3-round{
      padding:0 15px; }
    .bp3-large .bp3-file-upload-input::after{
      min-width:30px;
      min-height:30px;
      margin:5px;
      width:85px;
      line-height:30px; }
  .bp3-dark .bp3-file-upload-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:disabled, .bp3-dark .bp3-file-upload-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover, .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
        background-color:#30404d; }
      .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
        background-color:#202b33;
        background-image:none; }
      .bp3-dark .bp3-file-upload-input::after:disabled, .bp3-dark .bp3-file-upload-input::after.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(57, 75, 89, 0.5);
        background-image:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-upload-input::after:disabled.bp3-active, .bp3-dark .bp3-file-upload-input::after.bp3-disabled.bp3-active{
          background:rgba(57, 75, 89, 0.7); }
      .bp3-dark .bp3-file-upload-input::after .bp3-button-spinner .bp3-spinner-head{
        background:rgba(16, 22, 26, 0.5);
        stroke:#8a9ba8; }
    .bp3-dark .bp3-file-upload-input:hover::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-file-upload-input:active::after{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }

.bp3-file-upload-input::after{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
.bp3-form-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0 0 15px; }
  .bp3-form-group label.bp3-label{
    margin-bottom:5px; }
  .bp3-form-group .bp3-control{
    margin-top:7px; }
  .bp3-form-group .bp3-form-helper-text{
    margin-top:5px;
    color:#5c7080;
    font-size:12px; }
  .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#106ba3; }
  .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#0d8050; }
  .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#bf7326; }
  .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#c23030; }
  .bp3-form-group.bp3-inline{
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-form-group.bp3-inline.bp3-large label.bp3-label{
      margin:0 10px 0 0;
      line-height:40px; }
    .bp3-form-group.bp3-inline label.bp3-label{
      margin:0 10px 0 0;
      line-height:30px; }
  .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-dark .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#48aff0; }
  .bp3-dark .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#3dcc91; }
  .bp3-dark .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#ffb366; }
  .bp3-dark .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#ff7373; }
  .bp3-dark .bp3-form-group .bp3-form-helper-text{
    color:#a7b6c2; }
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-label,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-text-muted,
  .bp3-dark .bp3-form-group.bp3-disabled .bp3-form-helper-text{
    color:rgba(167, 182, 194, 0.6) !important; }
.bp3-input-group{
  display:block;
  position:relative; }
  .bp3-input-group .bp3-input{
    position:relative;
    width:100%; }
    .bp3-input-group .bp3-input:not(:first-child){
      padding-left:30px; }
    .bp3-input-group .bp3-input:not(:last-child){
      padding-right:30px; }
  .bp3-input-group .bp3-input-action,
  .bp3-input-group > .bp3-button,
  .bp3-input-group > .bp3-icon{
    position:absolute;
    top:0; }
    .bp3-input-group .bp3-input-action:first-child,
    .bp3-input-group > .bp3-button:first-child,
    .bp3-input-group > .bp3-icon:first-child{
      left:0; }
    .bp3-input-group .bp3-input-action:last-child,
    .bp3-input-group > .bp3-button:last-child,
    .bp3-input-group > .bp3-icon:last-child{
      right:0; }
  .bp3-input-group .bp3-button{
    min-width:24px;
    min-height:24px;
    margin:3px;
    padding:0 7px; }
    .bp3-input-group .bp3-button:empty{
      padding:0; }
  .bp3-input-group > .bp3-icon{
    z-index:1;
    color:#5c7080; }
    .bp3-input-group > .bp3-icon:empty{
      line-height:1;
      font-family:"Icons16", sans-serif;
      font-size:16px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased; }
  .bp3-input-group > .bp3-icon,
  .bp3-input-group .bp3-input-action > .bp3-spinner{
    margin:7px; }
  .bp3-input-group .bp3-tag{
    margin:5px; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus),
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
    color:#5c7080; }
    .bp3-dark .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus), .bp3-dark
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus){
      color:#a7b6c2; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:not(:hover):not(:focus) .bp3-icon-large{
      color:#5c7080; }
  .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled,
  .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled{
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-standard, .bp3-input-group .bp3-input:not(:focus) + .bp3-button.bp3-minimal:disabled .bp3-icon-large,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-standard,
    .bp3-input-group .bp3-input:not(:focus) + .bp3-input-action .bp3-button.bp3-minimal:disabled .bp3-icon-large{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-input-group.bp3-disabled{
    cursor:not-allowed; }
    .bp3-input-group.bp3-disabled .bp3-icon{
      color:rgba(92, 112, 128, 0.6); }
  .bp3-input-group.bp3-large .bp3-button{
    min-width:30px;
    min-height:30px;
    margin:5px; }
  .bp3-input-group.bp3-large > .bp3-icon,
  .bp3-input-group.bp3-large .bp3-input-action > .bp3-spinner{
    margin:12px; }
  .bp3-input-group.bp3-large .bp3-input{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input-group.bp3-large .bp3-input[type="search"], .bp3-input-group.bp3-large .bp3-input.bp3-round{
      padding:0 15px; }
    .bp3-input-group.bp3-large .bp3-input:not(:first-child){
      padding-left:40px; }
    .bp3-input-group.bp3-large .bp3-input:not(:last-child){
      padding-right:40px; }
  .bp3-input-group.bp3-small .bp3-button{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small .bp3-tag{
    min-width:20px;
    min-height:20px;
    margin:2px; }
  .bp3-input-group.bp3-small > .bp3-icon,
  .bp3-input-group.bp3-small .bp3-input-action > .bp3-spinner{
    margin:4px; }
  .bp3-input-group.bp3-small .bp3-input{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input-group.bp3-small .bp3-input[type="search"], .bp3-input-group.bp3-small .bp3-input.bp3-round{
      padding:0 12px; }
    .bp3-input-group.bp3-small .bp3-input:not(:first-child){
      padding-left:24px; }
    .bp3-input-group.bp3-small .bp3-input:not(:last-child){
      padding-right:24px; }
  .bp3-input-group.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-input-group.bp3-round .bp3-button,
  .bp3-input-group.bp3-round .bp3-input,
  .bp3-input-group.bp3-round .bp3-tag{
    border-radius:30px; }
  .bp3-dark .bp3-input-group .bp3-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-input-group.bp3-disabled .bp3-icon{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-input-group.bp3-intent-primary .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-primary .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input-group.bp3-intent-primary .bp3-input:disabled, .bp3-input-group.bp3-intent-primary .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-primary > .bp3-icon{
    color:#106ba3; }
    .bp3-dark .bp3-input-group.bp3-intent-primary > .bp3-icon{
      color:#48aff0; }
  .bp3-input-group.bp3-intent-success .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-success .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input-group.bp3-intent-success .bp3-input:disabled, .bp3-input-group.bp3-intent-success .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-success > .bp3-icon{
    color:#0d8050; }
    .bp3-dark .bp3-input-group.bp3-intent-success > .bp3-icon{
      color:#3dcc91; }
  .bp3-input-group.bp3-intent-warning .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-warning .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input-group.bp3-intent-warning .bp3-input:disabled, .bp3-input-group.bp3-intent-warning .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-warning > .bp3-icon{
    color:#bf7326; }
    .bp3-dark .bp3-input-group.bp3-intent-warning > .bp3-icon{
      color:#ffb366; }
  .bp3-input-group.bp3-intent-danger .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input-group.bp3-intent-danger .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input-group.bp3-intent-danger .bp3-input:disabled, .bp3-input-group.bp3-intent-danger .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-input-group.bp3-intent-danger > .bp3-icon{
    color:#c23030; }
    .bp3-dark .bp3-input-group.bp3-intent-danger > .bp3-icon{
      color:#ff7373; }
.bp3-input{
  outline:none;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  background:#ffffff;
  height:30px;
  padding:0 10px;
  vertical-align:middle;
  line-height:30px;
  color:#182026;
  font-size:14px;
  font-weight:400;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none; }
  .bp3-input::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input:focus, .bp3-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-input[type="search"], .bp3-input.bp3-round{
    border-radius:30px;
    -webkit-box-sizing:border-box;
            box-sizing:border-box;
    padding-left:10px; }
  .bp3-input[readonly]{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15); }
  .bp3-input:disabled, .bp3-input.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(206, 217, 224, 0.5);
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6);
    resize:none; }
  .bp3-input.bp3-large{
    height:40px;
    line-height:40px;
    font-size:16px; }
    .bp3-input.bp3-large[type="search"], .bp3-input.bp3-large.bp3-round{
      padding:0 15px; }
  .bp3-input.bp3-small{
    height:24px;
    padding-right:8px;
    padding-left:8px;
    line-height:24px;
    font-size:12px; }
    .bp3-input.bp3-small[type="search"], .bp3-input.bp3-small.bp3-round{
      padding:0 12px; }
  .bp3-input.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-dark .bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark .bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-input:disabled, .bp3-dark .bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
  .bp3-input.bp3-intent-primary{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-primary[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #137cbd;
              box-shadow:inset 0 0 0 1px #137cbd; }
    .bp3-input.bp3-intent-primary:disabled, .bp3-input.bp3-intent-primary.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px #137cbd, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary:focus{
        -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-primary[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #137cbd;
                box-shadow:inset 0 0 0 1px #137cbd; }
      .bp3-dark .bp3-input.bp3-intent-primary:disabled, .bp3-dark .bp3-input.bp3-intent-primary.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-success{
    -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success:focus{
      -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-success[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #0f9960;
              box-shadow:inset 0 0 0 1px #0f9960; }
    .bp3-input.bp3-intent-success:disabled, .bp3-input.bp3-intent-success.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-success{
      -webkit-box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), 0 0 0 0 rgba(15, 153, 96, 0), inset 0 0 0 1px #0f9960, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success:focus{
        -webkit-box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #0f9960, 0 0 0 1px #0f9960, 0 0 0 3px rgba(15, 153, 96, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-success[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #0f9960;
                box-shadow:inset 0 0 0 1px #0f9960; }
      .bp3-dark .bp3-input.bp3-intent-success:disabled, .bp3-dark .bp3-input.bp3-intent-success.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-warning{
    -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning:focus{
      -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-warning[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #d9822b;
              box-shadow:inset 0 0 0 1px #d9822b; }
    .bp3-input.bp3-intent-warning:disabled, .bp3-input.bp3-intent-warning.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), 0 0 0 0 rgba(217, 130, 43, 0), inset 0 0 0 1px #d9822b, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning:focus{
        -webkit-box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #d9822b, 0 0 0 1px #d9822b, 0 0 0 3px rgba(217, 130, 43, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-warning[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #d9822b;
                box-shadow:inset 0 0 0 1px #d9822b; }
      .bp3-dark .bp3-input.bp3-intent-warning:disabled, .bp3-dark .bp3-input.bp3-intent-warning.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input.bp3-intent-danger{
    -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger:focus{
      -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-input.bp3-intent-danger[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px #db3737;
              box-shadow:inset 0 0 0 1px #db3737; }
    .bp3-input.bp3-intent-danger:disabled, .bp3-input.bp3-intent-danger.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none; }
    .bp3-dark .bp3-input.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), 0 0 0 0 rgba(219, 55, 55, 0), inset 0 0 0 1px #db3737, inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger:focus{
        -webkit-box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px #db3737, 0 0 0 1px #db3737, 0 0 0 3px rgba(219, 55, 55, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-input.bp3-intent-danger[readonly]{
        -webkit-box-shadow:inset 0 0 0 1px #db3737;
                box-shadow:inset 0 0 0 1px #db3737; }
      .bp3-dark .bp3-input.bp3-intent-danger:disabled, .bp3-dark .bp3-input.bp3-intent-danger.bp3-disabled{
        -webkit-box-shadow:none;
                box-shadow:none; }
  .bp3-input::-ms-clear{
    display:none; }
textarea.bp3-input{
  max-width:100%;
  padding:10px; }
  textarea.bp3-input, textarea.bp3-input.bp3-large, textarea.bp3-input.bp3-small{
    height:auto;
    line-height:inherit; }
  textarea.bp3-input.bp3-small{
    padding:8px; }
  .bp3-dark textarea.bp3-input{
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background:rgba(16, 22, 26, 0.3);
    color:#f5f8fa; }
    .bp3-dark textarea.bp3-input::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input::placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark textarea.bp3-input:focus{
      -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input[readonly]{
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark textarea.bp3-input:disabled, .bp3-dark textarea.bp3-input.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:rgba(57, 75, 89, 0.5);
      color:rgba(167, 182, 194, 0.6); }
label.bp3-label{
  display:block;
  margin-top:0;
  margin-bottom:15px; }
  label.bp3-label .bp3-html-select,
  label.bp3-label .bp3-input,
  label.bp3-label .bp3-select,
  label.bp3-label .bp3-slider,
  label.bp3-label .bp3-popover-wrapper{
    display:block;
    margin-top:5px;
    text-transform:none; }
  label.bp3-label .bp3-button-group{
    margin-top:5px; }
  label.bp3-label .bp3-select select,
  label.bp3-label .bp3-html-select select{
    width:100%;
    vertical-align:top;
    font-weight:400; }
  label.bp3-label.bp3-disabled,
  label.bp3-label.bp3-disabled .bp3-text-muted{
    color:rgba(92, 112, 128, 0.6); }
  label.bp3-label.bp3-inline{
    line-height:30px; }
    label.bp3-label.bp3-inline .bp3-html-select,
    label.bp3-label.bp3-inline .bp3-input,
    label.bp3-label.bp3-inline .bp3-input-group,
    label.bp3-label.bp3-inline .bp3-select,
    label.bp3-label.bp3-inline .bp3-popover-wrapper{
      display:inline-block;
      margin:0 0 0 5px;
      vertical-align:top; }
    label.bp3-label.bp3-inline .bp3-button-group{
      margin:0 0 0 5px; }
    label.bp3-label.bp3-inline .bp3-input-group .bp3-input{
      margin-left:0; }
    label.bp3-label.bp3-inline.bp3-large{
      line-height:40px; }
  label.bp3-label:not(.bp3-inline) .bp3-popover-target{
    display:block; }
  .bp3-dark label.bp3-label{
    color:#f5f8fa; }
    .bp3-dark label.bp3-label.bp3-disabled,
    .bp3-dark label.bp3-label.bp3-disabled .bp3-text-muted{
      color:rgba(167, 182, 194, 0.6); }
.bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button{
  -webkit-box-flex:1;
      -ms-flex:1 1 14px;
          flex:1 1 14px;
  width:30px;
  min-height:0;
  padding:0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:first-child{
    border-radius:0 3px 0 0; }
  .bp3-numeric-input .bp3-button-group.bp3-vertical > .bp3-button:last-child{
    border-radius:0 0 3px 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:first-child{
  border-radius:3px 0 0 0; }

.bp3-numeric-input .bp3-button-group.bp3-vertical:first-child > .bp3-button:last-child{
  border-radius:0 0 0 3px; }

.bp3-numeric-input.bp3-large .bp3-button-group.bp3-vertical > .bp3-button{
  width:40px; }

form{
  display:block; }
.bp3-html-select select,
.bp3-select select{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  border:none;
  border-radius:3px;
  cursor:pointer;
  padding:5px 10px;
  vertical-align:middle;
  text-align:left;
  font-size:14px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  border-radius:3px;
  width:100%;
  height:30px;
  padding:0 25px 0 10px;
  -moz-appearance:none;
  -webkit-appearance:none; }
  .bp3-html-select select > *, .bp3-select select > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-html-select select > .bp3-fill, .bp3-select select > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-html-select select::before,
  .bp3-select select::before, .bp3-html-select select > *, .bp3-select select > *{
    margin-right:7px; }
  .bp3-html-select select:empty::before,
  .bp3-select select:empty::before,
  .bp3-html-select select > :last-child,
  .bp3-select select > :last-child{
    margin-right:0; }
  .bp3-html-select select:hover,
  .bp3-select select:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-html-select select:active,
  .bp3-select select:active, .bp3-html-select select.bp3-active,
  .bp3-select select.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-html-select select:disabled,
  .bp3-select select:disabled, .bp3-html-select select.bp3-disabled,
  .bp3-select select.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select select:disabled.bp3-active,
    .bp3-select select:disabled.bp3-active, .bp3-html-select select:disabled.bp3-active:hover,
    .bp3-select select:disabled.bp3-active:hover, .bp3-html-select select.bp3-disabled.bp3-active,
    .bp3-select select.bp3-disabled.bp3-active, .bp3-html-select select.bp3-disabled.bp3-active:hover,
    .bp3-select select.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }

.bp3-html-select.bp3-minimal select,
.bp3-select.bp3-minimal select{
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none; }
  .bp3-html-select.bp3-minimal select:hover,
  .bp3-select.bp3-minimal select:hover{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(167, 182, 194, 0.3);
    text-decoration:none;
    color:#182026; }
  .bp3-html-select.bp3-minimal select:active,
  .bp3-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal select.bp3-active,
  .bp3-select.bp3-minimal select.bp3-active{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:rgba(115, 134, 148, 0.3);
    color:#182026; }
  .bp3-html-select.bp3-minimal select:disabled,
  .bp3-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal select:disabled:hover,
  .bp3-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal select.bp3-disabled,
  .bp3-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal select.bp3-disabled:hover,
  .bp3-select.bp3-minimal select.bp3-disabled:hover{
    background:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-html-select.bp3-minimal select:disabled.bp3-active,
    .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active{
      background:rgba(115, 134, 148, 0.3); }
  .bp3-dark .bp3-html-select.bp3-minimal select, .bp3-html-select.bp3-minimal .bp3-dark select,
  .bp3-dark .bp3-select.bp3-minimal select, .bp3-select.bp3-minimal .bp3-dark select{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:none;
    color:inherit; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover, .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover{
      background:rgba(138, 155, 168, 0.15); }
    .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:rgba(138, 155, 168, 0.3);
      color:#f5f8fa; }
    .bp3-dark .bp3-html-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal .bp3-dark select:disabled,
    .bp3-dark .bp3-select.bp3-minimal select:disabled, .bp3-select.bp3-minimal .bp3-dark select:disabled, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select:disabled:hover, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover{
      background:none;
      cursor:not-allowed;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-html-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select:disabled:hover.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-disabled:hover.bp3-active{
        background:rgba(138, 155, 168, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-primary,
  .bp3-select.bp3-minimal select.bp3-intent-primary{
    color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover,
    .bp3-select.bp3-minimal select.bp3-intent-primary:hover{
      background:rgba(19, 124, 189, 0.15);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:active,
    .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active{
      background:rgba(19, 124, 189, 0.3);
      color:#106ba3; }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled{
      background:none;
      color:rgba(16, 107, 163, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active{
        background:rgba(19, 124, 189, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
      stroke:#106ba3; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary{
      color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.2);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#48aff0; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(72, 175, 240, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-primary.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-success,
  .bp3-select.bp3-minimal select.bp3-intent-success{
    color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:hover,
    .bp3-select.bp3-minimal select.bp3-intent-success:hover{
      background:rgba(15, 153, 96, 0.15);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:active,
    .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active{
      background:rgba(15, 153, 96, 0.3);
      color:#0d8050; }
    .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled{
      background:none;
      color:rgba(13, 128, 80, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active{
        background:rgba(15, 153, 96, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
      stroke:#0d8050; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success{
      color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.2);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#3dcc91; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(61, 204, 145, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-success.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-warning,
  .bp3-select.bp3-minimal select.bp3-intent-warning{
    color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover,
    .bp3-select.bp3-minimal select.bp3-intent-warning:hover{
      background:rgba(217, 130, 43, 0.15);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:active,
    .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active{
      background:rgba(217, 130, 43, 0.3);
      color:#bf7326; }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled{
      background:none;
      color:rgba(191, 115, 38, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active{
        background:rgba(217, 130, 43, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
      stroke:#bf7326; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning{
      color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.2);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#ffb366; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(255, 179, 102, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-warning.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
  .bp3-html-select.bp3-minimal select.bp3-intent-danger,
  .bp3-select.bp3-minimal select.bp3-intent-danger{
    color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      -webkit-box-shadow:none;
              box-shadow:none;
      background:none;
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover,
    .bp3-select.bp3-minimal select.bp3-intent-danger:hover{
      background:rgba(219, 55, 55, 0.15);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:active,
    .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active{
      background:rgba(219, 55, 55, 0.3);
      color:#c23030; }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled,
    .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled{
      background:none;
      color:rgba(194, 48, 48, 0.5); }
      .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active,
      .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active{
        background:rgba(219, 55, 55, 0.3); }
    .bp3-html-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head, .bp3-select.bp3-minimal select.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
      stroke:#c23030; }
    .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger{
      color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:hover, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.2);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#ff7373; }
      .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled,
      .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(255, 115, 115, 0.5); }
        .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger:disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active,
        .bp3-dark .bp3-select.bp3-minimal select.bp3-intent-danger.bp3-disabled.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }

.bp3-html-select.bp3-large select,
.bp3-select.bp3-large select{
  height:40px;
  padding-right:35px;
  font-size:16px; }

.bp3-dark .bp3-html-select select, .bp3-dark .bp3-select select{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
  background-color:#394b59;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
  color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover, .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }
  .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#202b33;
    background-image:none; }
  .bp3-dark .bp3-html-select select:disabled, .bp3-dark .bp3-select select:disabled, .bp3-dark .bp3-html-select select.bp3-disabled, .bp3-dark .bp3-select select.bp3-disabled{
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(57, 75, 89, 0.5);
    background-image:none;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-html-select select:disabled.bp3-active, .bp3-dark .bp3-select select:disabled.bp3-active, .bp3-dark .bp3-html-select select.bp3-disabled.bp3-active, .bp3-dark .bp3-select select.bp3-disabled.bp3-active{
      background:rgba(57, 75, 89, 0.7); }
  .bp3-dark .bp3-html-select select .bp3-button-spinner .bp3-spinner-head, .bp3-dark .bp3-select select .bp3-button-spinner .bp3-spinner-head{
    background:rgba(16, 22, 26, 0.5);
    stroke:#8a9ba8; }

.bp3-html-select select:disabled,
.bp3-select select:disabled{
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:rgba(206, 217, 224, 0.5);
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-html-select .bp3-icon,
.bp3-select .bp3-icon, .bp3-select::after{
  position:absolute;
  top:7px;
  right:7px;
  color:#5c7080;
  pointer-events:none; }
  .bp3-html-select .bp3-disabled.bp3-icon,
  .bp3-select .bp3-disabled.bp3-icon, .bp3-disabled.bp3-select::after{
    color:rgba(92, 112, 128, 0.6); }
.bp3-html-select,
.bp3-select{
  display:inline-block;
  position:relative;
  vertical-align:middle;
  letter-spacing:normal; }
  .bp3-html-select select::-ms-expand,
  .bp3-select select::-ms-expand{
    display:none; }
  .bp3-html-select .bp3-icon,
  .bp3-select .bp3-icon{
    color:#5c7080; }
    .bp3-html-select .bp3-icon:hover,
    .bp3-select .bp3-icon:hover{
      color:#182026; }
    .bp3-dark .bp3-html-select .bp3-icon, .bp3-dark
    .bp3-select .bp3-icon{
      color:#a7b6c2; }
      .bp3-dark .bp3-html-select .bp3-icon:hover, .bp3-dark
      .bp3-select .bp3-icon:hover{
        color:#f5f8fa; }
  .bp3-html-select.bp3-large::after,
  .bp3-html-select.bp3-large .bp3-icon,
  .bp3-select.bp3-large::after,
  .bp3-select.bp3-large .bp3-icon{
    top:12px;
    right:12px; }
  .bp3-html-select.bp3-fill,
  .bp3-html-select.bp3-fill select,
  .bp3-select.bp3-fill,
  .bp3-select.bp3-fill select{
    width:100%; }
  .bp3-dark .bp3-html-select option, .bp3-dark
  .bp3-select option{
    background-color:#30404d;
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select::after, .bp3-dark
  .bp3-select::after{
    color:#a7b6c2; }

.bp3-select::after{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  content:""; }
.bp3-running-text table, table.bp3-html-table{
  border-spacing:0;
  font-size:14px; }
  .bp3-running-text table th, table.bp3-html-table th,
  .bp3-running-text table td,
  table.bp3-html-table td{
    padding:11px;
    vertical-align:top;
    text-align:left; }
  .bp3-running-text table th, table.bp3-html-table th{
    color:#182026;
    font-weight:600; }
  
  .bp3-running-text table td,
  table.bp3-html-table td{
    color:#182026; }
  .bp3-running-text table tbody tr:first-child th, table.bp3-html-table tbody tr:first-child th,
  .bp3-running-text table tbody tr:first-child td,
  table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-running-text table th, .bp3-running-text .bp3-dark table th, .bp3-dark table.bp3-html-table th{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table td, .bp3-running-text .bp3-dark table td, .bp3-dark table.bp3-html-table td{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table tbody tr:first-child th, .bp3-running-text .bp3-dark table tbody tr:first-child th, .bp3-dark table.bp3-html-table tbody tr:first-child th,
  .bp3-dark .bp3-running-text table tbody tr:first-child td,
  .bp3-running-text .bp3-dark table tbody tr:first-child td,
  .bp3-dark table.bp3-html-table tbody tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }

table.bp3-html-table.bp3-html-table-condensed th,
table.bp3-html-table.bp3-html-table-condensed td, table.bp3-html-table.bp3-small th,
table.bp3-html-table.bp3-small td{
  padding-top:6px;
  padding-bottom:6px; }

table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(191, 204, 214, 0.15); }

table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:none;
          box-shadow:none; }
  table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(191, 204, 214, 0.3);
  cursor:pointer; }

table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(191, 204, 214, 0.4); }

.bp3-dark table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(92, 112, 128, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child){
    -webkit-box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 1px 0 0 rgba(255, 255, 255, 0.15); }

.bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td{
  -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered.bp3-html-table-striped tbody tr:not(:first-child) td:first-child{
    -webkit-box-shadow:none;
            box-shadow:none; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:hover td{
  background-color:rgba(92, 112, 128, 0.3);
  cursor:pointer; }

.bp3-dark table.bp3-html-table.bp3-interactive tbody tr:active td{
  background-color:rgba(92, 112, 128, 0.4); }

.bp3-key-combo{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center; }
  .bp3-key-combo > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-key-combo > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-key-combo::before,
  .bp3-key-combo > *{
    margin-right:5px; }
  .bp3-key-combo:empty::before,
  .bp3-key-combo > :last-child{
    margin-right:0; }

.bp3-hotkey-dialog{
  top:40px;
  padding-bottom:0; }
  .bp3-hotkey-dialog .bp3-dialog-body{
    margin:0;
    padding:0; }
  .bp3-hotkey-dialog .bp3-hotkey-label{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1; }

.bp3-hotkey-column{
  margin:auto;
  max-height:80vh;
  overflow-y:auto;
  padding:30px; }
  .bp3-hotkey-column .bp3-heading{
    margin-bottom:20px; }
    .bp3-hotkey-column .bp3-heading:not(:first-child){
      margin-top:40px; }

.bp3-hotkey{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:justify;
      -ms-flex-pack:justify;
          justify-content:space-between;
  margin-right:0;
  margin-left:0; }
  .bp3-hotkey:not(:last-child){
    margin-bottom:10px; }
.bp3-icon{
  display:inline-block;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  vertical-align:text-bottom; }
  .bp3-icon:not(:empty)::before{
    content:"" !important;
    content:unset !important; }
  .bp3-icon > svg{
    display:block; }
    .bp3-icon > svg:not([fill]){
      fill:currentColor; }

.bp3-icon.bp3-intent-primary, .bp3-icon-standard.bp3-intent-primary, .bp3-icon-large.bp3-intent-primary{
  color:#106ba3; }
  .bp3-dark .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-icon-large.bp3-intent-primary{
    color:#48aff0; }

.bp3-icon.bp3-intent-success, .bp3-icon-standard.bp3-intent-success, .bp3-icon-large.bp3-intent-success{
  color:#0d8050; }
  .bp3-dark .bp3-icon.bp3-intent-success, .bp3-dark .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-icon-large.bp3-intent-success{
    color:#3dcc91; }

.bp3-icon.bp3-intent-warning, .bp3-icon-standard.bp3-intent-warning, .bp3-icon-large.bp3-intent-warning{
  color:#bf7326; }
  .bp3-dark .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-icon-large.bp3-intent-warning{
    color:#ffb366; }

.bp3-icon.bp3-intent-danger, .bp3-icon-standard.bp3-intent-danger, .bp3-icon-large.bp3-intent-danger{
  color:#c23030; }
  .bp3-dark .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-icon-large.bp3-intent-danger{
    color:#ff7373; }

span.bp3-icon-standard{
  line-height:1;
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon-large{
  line-height:1;
  font-family:"Icons20", sans-serif;
  font-size:20px;
  font-weight:400;
  font-style:normal;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon:empty{
  line-height:1;
  font-family:"Icons20";
  font-size:inherit;
  font-weight:400;
  font-style:normal; }
  span.bp3-icon:empty::before{
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased; }

.bp3-icon-add::before{
  content:""; }

.bp3-icon-add-column-left::before{
  content:""; }

.bp3-icon-add-column-right::before{
  content:""; }

.bp3-icon-add-row-bottom::before{
  content:""; }

.bp3-icon-add-row-top::before{
  content:""; }

.bp3-icon-add-to-artifact::before{
  content:""; }

.bp3-icon-add-to-folder::before{
  content:""; }

.bp3-icon-airplane::before{
  content:""; }

.bp3-icon-align-center::before{
  content:""; }

.bp3-icon-align-justify::before{
  content:""; }

.bp3-icon-align-left::before{
  content:""; }

.bp3-icon-align-right::before{
  content:""; }

.bp3-icon-alignment-bottom::before{
  content:""; }

.bp3-icon-alignment-horizontal-center::before{
  content:""; }

.bp3-icon-alignment-left::before{
  content:""; }

.bp3-icon-alignment-right::before{
  content:""; }

.bp3-icon-alignment-top::before{
  content:""; }

.bp3-icon-alignment-vertical-center::before{
  content:""; }

.bp3-icon-annotation::before{
  content:""; }

.bp3-icon-application::before{
  content:""; }

.bp3-icon-applications::before{
  content:""; }

.bp3-icon-archive::before{
  content:""; }

.bp3-icon-arrow-bottom-left::before{
  content:"↙"; }

.bp3-icon-arrow-bottom-right::before{
  content:"↘"; }

.bp3-icon-arrow-down::before{
  content:"↓"; }

.bp3-icon-arrow-left::before{
  content:"←"; }

.bp3-icon-arrow-right::before{
  content:"→"; }

.bp3-icon-arrow-top-left::before{
  content:"↖"; }

.bp3-icon-arrow-top-right::before{
  content:"↗"; }

.bp3-icon-arrow-up::before{
  content:"↑"; }

.bp3-icon-arrows-horizontal::before{
  content:"↔"; }

.bp3-icon-arrows-vertical::before{
  content:"↕"; }

.bp3-icon-asterisk::before{
  content:"*"; }

.bp3-icon-automatic-updates::before{
  content:""; }

.bp3-icon-badge::before{
  content:""; }

.bp3-icon-ban-circle::before{
  content:""; }

.bp3-icon-bank-account::before{
  content:""; }

.bp3-icon-barcode::before{
  content:""; }

.bp3-icon-blank::before{
  content:""; }

.bp3-icon-blocked-person::before{
  content:""; }

.bp3-icon-bold::before{
  content:""; }

.bp3-icon-book::before{
  content:""; }

.bp3-icon-bookmark::before{
  content:""; }

.bp3-icon-box::before{
  content:""; }

.bp3-icon-briefcase::before{
  content:""; }

.bp3-icon-bring-data::before{
  content:""; }

.bp3-icon-build::before{
  content:""; }

.bp3-icon-calculator::before{
  content:""; }

.bp3-icon-calendar::before{
  content:""; }

.bp3-icon-camera::before{
  content:""; }

.bp3-icon-caret-down::before{
  content:"⌄"; }

.bp3-icon-caret-left::before{
  content:"〈"; }

.bp3-icon-caret-right::before{
  content:"〉"; }

.bp3-icon-caret-up::before{
  content:"⌃"; }

.bp3-icon-cell-tower::before{
  content:""; }

.bp3-icon-changes::before{
  content:""; }

.bp3-icon-chart::before{
  content:""; }

.bp3-icon-chat::before{
  content:""; }

.bp3-icon-chevron-backward::before{
  content:""; }

.bp3-icon-chevron-down::before{
  content:""; }

.bp3-icon-chevron-forward::before{
  content:""; }

.bp3-icon-chevron-left::before{
  content:""; }

.bp3-icon-chevron-right::before{
  content:""; }

.bp3-icon-chevron-up::before{
  content:""; }

.bp3-icon-circle::before{
  content:""; }

.bp3-icon-circle-arrow-down::before{
  content:""; }

.bp3-icon-circle-arrow-left::before{
  content:""; }

.bp3-icon-circle-arrow-right::before{
  content:""; }

.bp3-icon-circle-arrow-up::before{
  content:""; }

.bp3-icon-citation::before{
  content:""; }

.bp3-icon-clean::before{
  content:""; }

.bp3-icon-clipboard::before{
  content:""; }

.bp3-icon-cloud::before{
  content:"☁"; }

.bp3-icon-cloud-download::before{
  content:""; }

.bp3-icon-cloud-upload::before{
  content:""; }

.bp3-icon-code::before{
  content:""; }

.bp3-icon-code-block::before{
  content:""; }

.bp3-icon-cog::before{
  content:""; }

.bp3-icon-collapse-all::before{
  content:""; }

.bp3-icon-column-layout::before{
  content:""; }

.bp3-icon-comment::before{
  content:""; }

.bp3-icon-comparison::before{
  content:""; }

.bp3-icon-compass::before{
  content:""; }

.bp3-icon-compressed::before{
  content:""; }

.bp3-icon-confirm::before{
  content:""; }

.bp3-icon-console::before{
  content:""; }

.bp3-icon-contrast::before{
  content:""; }

.bp3-icon-control::before{
  content:""; }

.bp3-icon-credit-card::before{
  content:""; }

.bp3-icon-cross::before{
  content:"✗"; }

.bp3-icon-crown::before{
  content:""; }

.bp3-icon-cube::before{
  content:""; }

.bp3-icon-cube-add::before{
  content:""; }

.bp3-icon-cube-remove::before{
  content:""; }

.bp3-icon-curved-range-chart::before{
  content:""; }

.bp3-icon-cut::before{
  content:""; }

.bp3-icon-dashboard::before{
  content:""; }

.bp3-icon-data-lineage::before{
  content:""; }

.bp3-icon-database::before{
  content:""; }

.bp3-icon-delete::before{
  content:""; }

.bp3-icon-delta::before{
  content:"Δ"; }

.bp3-icon-derive-column::before{
  content:""; }

.bp3-icon-desktop::before{
  content:""; }

.bp3-icon-diagram-tree::before{
  content:""; }

.bp3-icon-direction-left::before{
  content:""; }

.bp3-icon-direction-right::before{
  content:""; }

.bp3-icon-disable::before{
  content:""; }

.bp3-icon-document::before{
  content:""; }

.bp3-icon-document-open::before{
  content:""; }

.bp3-icon-document-share::before{
  content:""; }

.bp3-icon-dollar::before{
  content:"$"; }

.bp3-icon-dot::before{
  content:"•"; }

.bp3-icon-double-caret-horizontal::before{
  content:""; }

.bp3-icon-double-caret-vertical::before{
  content:""; }

.bp3-icon-double-chevron-down::before{
  content:""; }

.bp3-icon-double-chevron-left::before{
  content:""; }

.bp3-icon-double-chevron-right::before{
  content:""; }

.bp3-icon-double-chevron-up::before{
  content:""; }

.bp3-icon-doughnut-chart::before{
  content:""; }

.bp3-icon-download::before{
  content:""; }

.bp3-icon-drag-handle-horizontal::before{
  content:""; }

.bp3-icon-drag-handle-vertical::before{
  content:""; }

.bp3-icon-draw::before{
  content:""; }

.bp3-icon-drive-time::before{
  content:""; }

.bp3-icon-duplicate::before{
  content:""; }

.bp3-icon-edit::before{
  content:"✎"; }

.bp3-icon-eject::before{
  content:"⏏"; }

.bp3-icon-endorsed::before{
  content:""; }

.bp3-icon-envelope::before{
  content:"✉"; }

.bp3-icon-equals::before{
  content:""; }

.bp3-icon-eraser::before{
  content:""; }

.bp3-icon-error::before{
  content:""; }

.bp3-icon-euro::before{
  content:"€"; }

.bp3-icon-exchange::before{
  content:""; }

.bp3-icon-exclude-row::before{
  content:""; }

.bp3-icon-expand-all::before{
  content:""; }

.bp3-icon-export::before{
  content:""; }

.bp3-icon-eye-off::before{
  content:""; }

.bp3-icon-eye-on::before{
  content:""; }

.bp3-icon-eye-open::before{
  content:""; }

.bp3-icon-fast-backward::before{
  content:""; }

.bp3-icon-fast-forward::before{
  content:""; }

.bp3-icon-feed::before{
  content:""; }

.bp3-icon-feed-subscribed::before{
  content:""; }

.bp3-icon-film::before{
  content:""; }

.bp3-icon-filter::before{
  content:""; }

.bp3-icon-filter-keep::before{
  content:""; }

.bp3-icon-filter-list::before{
  content:""; }

.bp3-icon-filter-open::before{
  content:""; }

.bp3-icon-filter-remove::before{
  content:""; }

.bp3-icon-flag::before{
  content:"⚑"; }

.bp3-icon-flame::before{
  content:""; }

.bp3-icon-flash::before{
  content:""; }

.bp3-icon-floppy-disk::before{
  content:""; }

.bp3-icon-flow-branch::before{
  content:""; }

.bp3-icon-flow-end::before{
  content:""; }

.bp3-icon-flow-linear::before{
  content:""; }

.bp3-icon-flow-review::before{
  content:""; }

.bp3-icon-flow-review-branch::before{
  content:""; }

.bp3-icon-flows::before{
  content:""; }

.bp3-icon-folder-close::before{
  content:""; }

.bp3-icon-folder-new::before{
  content:""; }

.bp3-icon-folder-open::before{
  content:""; }

.bp3-icon-folder-shared::before{
  content:""; }

.bp3-icon-folder-shared-open::before{
  content:""; }

.bp3-icon-follower::before{
  content:""; }

.bp3-icon-following::before{
  content:""; }

.bp3-icon-font::before{
  content:""; }

.bp3-icon-fork::before{
  content:""; }

.bp3-icon-form::before{
  content:""; }

.bp3-icon-full-circle::before{
  content:""; }

.bp3-icon-full-stacked-chart::before{
  content:""; }

.bp3-icon-fullscreen::before{
  content:""; }

.bp3-icon-function::before{
  content:""; }

.bp3-icon-gantt-chart::before{
  content:""; }

.bp3-icon-geolocation::before{
  content:""; }

.bp3-icon-geosearch::before{
  content:""; }

.bp3-icon-git-branch::before{
  content:""; }

.bp3-icon-git-commit::before{
  content:""; }

.bp3-icon-git-merge::before{
  content:""; }

.bp3-icon-git-new-branch::before{
  content:""; }

.bp3-icon-git-pull::before{
  content:""; }

.bp3-icon-git-push::before{
  content:""; }

.bp3-icon-git-repo::before{
  content:""; }

.bp3-icon-glass::before{
  content:""; }

.bp3-icon-globe::before{
  content:""; }

.bp3-icon-globe-network::before{
  content:""; }

.bp3-icon-graph::before{
  content:""; }

.bp3-icon-graph-remove::before{
  content:""; }

.bp3-icon-greater-than::before{
  content:""; }

.bp3-icon-greater-than-or-equal-to::before{
  content:""; }

.bp3-icon-grid::before{
  content:""; }

.bp3-icon-grid-view::before{
  content:""; }

.bp3-icon-group-objects::before{
  content:""; }

.bp3-icon-grouped-bar-chart::before{
  content:""; }

.bp3-icon-hand::before{
  content:""; }

.bp3-icon-hand-down::before{
  content:""; }

.bp3-icon-hand-left::before{
  content:""; }

.bp3-icon-hand-right::before{
  content:""; }

.bp3-icon-hand-up::before{
  content:""; }

.bp3-icon-header::before{
  content:""; }

.bp3-icon-header-one::before{
  content:""; }

.bp3-icon-header-two::before{
  content:""; }

.bp3-icon-headset::before{
  content:""; }

.bp3-icon-heart::before{
  content:"♥"; }

.bp3-icon-heart-broken::before{
  content:""; }

.bp3-icon-heat-grid::before{
  content:""; }

.bp3-icon-heatmap::before{
  content:""; }

.bp3-icon-help::before{
  content:"?"; }

.bp3-icon-helper-management::before{
  content:""; }

.bp3-icon-highlight::before{
  content:""; }

.bp3-icon-history::before{
  content:""; }

.bp3-icon-home::before{
  content:"⌂"; }

.bp3-icon-horizontal-bar-chart::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-asc::before{
  content:""; }

.bp3-icon-horizontal-bar-chart-desc::before{
  content:""; }

.bp3-icon-horizontal-distribution::before{
  content:""; }

.bp3-icon-id-number::before{
  content:""; }

.bp3-icon-image-rotate-left::before{
  content:""; }

.bp3-icon-image-rotate-right::before{
  content:""; }

.bp3-icon-import::before{
  content:""; }

.bp3-icon-inbox::before{
  content:""; }

.bp3-icon-inbox-filtered::before{
  content:""; }

.bp3-icon-inbox-geo::before{
  content:""; }

.bp3-icon-inbox-search::before{
  content:""; }

.bp3-icon-inbox-update::before{
  content:""; }

.bp3-icon-info-sign::before{
  content:"ℹ"; }

.bp3-icon-inheritance::before{
  content:""; }

.bp3-icon-inner-join::before{
  content:""; }

.bp3-icon-insert::before{
  content:""; }

.bp3-icon-intersection::before{
  content:""; }

.bp3-icon-ip-address::before{
  content:""; }

.bp3-icon-issue::before{
  content:""; }

.bp3-icon-issue-closed::before{
  content:""; }

.bp3-icon-issue-new::before{
  content:""; }

.bp3-icon-italic::before{
  content:""; }

.bp3-icon-join-table::before{
  content:""; }

.bp3-icon-key::before{
  content:""; }

.bp3-icon-key-backspace::before{
  content:""; }

.bp3-icon-key-command::before{
  content:""; }

.bp3-icon-key-control::before{
  content:""; }

.bp3-icon-key-delete::before{
  content:""; }

.bp3-icon-key-enter::before{
  content:""; }

.bp3-icon-key-escape::before{
  content:""; }

.bp3-icon-key-option::before{
  content:""; }

.bp3-icon-key-shift::before{
  content:""; }

.bp3-icon-key-tab::before{
  content:""; }

.bp3-icon-known-vehicle::before{
  content:""; }

.bp3-icon-label::before{
  content:""; }

.bp3-icon-layer::before{
  content:""; }

.bp3-icon-layers::before{
  content:""; }

.bp3-icon-layout::before{
  content:""; }

.bp3-icon-layout-auto::before{
  content:""; }

.bp3-icon-layout-balloon::before{
  content:""; }

.bp3-icon-layout-circle::before{
  content:""; }

.bp3-icon-layout-grid::before{
  content:""; }

.bp3-icon-layout-group-by::before{
  content:""; }

.bp3-icon-layout-hierarchy::before{
  content:""; }

.bp3-icon-layout-linear::before{
  content:""; }

.bp3-icon-layout-skew-grid::before{
  content:""; }

.bp3-icon-layout-sorted-clusters::before{
  content:""; }

.bp3-icon-learning::before{
  content:""; }

.bp3-icon-left-join::before{
  content:""; }

.bp3-icon-less-than::before{
  content:""; }

.bp3-icon-less-than-or-equal-to::before{
  content:""; }

.bp3-icon-lifesaver::before{
  content:""; }

.bp3-icon-lightbulb::before{
  content:""; }

.bp3-icon-link::before{
  content:""; }

.bp3-icon-list::before{
  content:"☰"; }

.bp3-icon-list-columns::before{
  content:""; }

.bp3-icon-list-detail-view::before{
  content:""; }

.bp3-icon-locate::before{
  content:""; }

.bp3-icon-lock::before{
  content:""; }

.bp3-icon-log-in::before{
  content:""; }

.bp3-icon-log-out::before{
  content:""; }

.bp3-icon-manual::before{
  content:""; }

.bp3-icon-manually-entered-data::before{
  content:""; }

.bp3-icon-map::before{
  content:""; }

.bp3-icon-map-create::before{
  content:""; }

.bp3-icon-map-marker::before{
  content:""; }

.bp3-icon-maximize::before{
  content:""; }

.bp3-icon-media::before{
  content:""; }

.bp3-icon-menu::before{
  content:""; }

.bp3-icon-menu-closed::before{
  content:""; }

.bp3-icon-menu-open::before{
  content:""; }

.bp3-icon-merge-columns::before{
  content:""; }

.bp3-icon-merge-links::before{
  content:""; }

.bp3-icon-minimize::before{
  content:""; }

.bp3-icon-minus::before{
  content:"−"; }

.bp3-icon-mobile-phone::before{
  content:""; }

.bp3-icon-mobile-video::before{
  content:""; }

.bp3-icon-moon::before{
  content:""; }

.bp3-icon-more::before{
  content:""; }

.bp3-icon-mountain::before{
  content:""; }

.bp3-icon-move::before{
  content:""; }

.bp3-icon-mugshot::before{
  content:""; }

.bp3-icon-multi-select::before{
  content:""; }

.bp3-icon-music::before{
  content:""; }

.bp3-icon-new-drawing::before{
  content:""; }

.bp3-icon-new-grid-item::before{
  content:""; }

.bp3-icon-new-layer::before{
  content:""; }

.bp3-icon-new-layers::before{
  content:""; }

.bp3-icon-new-link::before{
  content:""; }

.bp3-icon-new-object::before{
  content:""; }

.bp3-icon-new-person::before{
  content:""; }

.bp3-icon-new-prescription::before{
  content:""; }

.bp3-icon-new-text-box::before{
  content:""; }

.bp3-icon-ninja::before{
  content:""; }

.bp3-icon-not-equal-to::before{
  content:""; }

.bp3-icon-notifications::before{
  content:""; }

.bp3-icon-notifications-updated::before{
  content:""; }

.bp3-icon-numbered-list::before{
  content:""; }

.bp3-icon-numerical::before{
  content:""; }

.bp3-icon-office::before{
  content:""; }

.bp3-icon-offline::before{
  content:""; }

.bp3-icon-oil-field::before{
  content:""; }

.bp3-icon-one-column::before{
  content:""; }

.bp3-icon-outdated::before{
  content:""; }

.bp3-icon-page-layout::before{
  content:""; }

.bp3-icon-panel-stats::before{
  content:""; }

.bp3-icon-panel-table::before{
  content:""; }

.bp3-icon-paperclip::before{
  content:""; }

.bp3-icon-paragraph::before{
  content:""; }

.bp3-icon-path::before{
  content:""; }

.bp3-icon-path-search::before{
  content:""; }

.bp3-icon-pause::before{
  content:""; }

.bp3-icon-people::before{
  content:""; }

.bp3-icon-percentage::before{
  content:""; }

.bp3-icon-person::before{
  content:""; }

.bp3-icon-phone::before{
  content:"☎"; }

.bp3-icon-pie-chart::before{
  content:""; }

.bp3-icon-pin::before{
  content:""; }

.bp3-icon-pivot::before{
  content:""; }

.bp3-icon-pivot-table::before{
  content:""; }

.bp3-icon-play::before{
  content:""; }

.bp3-icon-plus::before{
  content:"+"; }

.bp3-icon-polygon-filter::before{
  content:""; }

.bp3-icon-power::before{
  content:""; }

.bp3-icon-predictive-analysis::before{
  content:""; }

.bp3-icon-prescription::before{
  content:""; }

.bp3-icon-presentation::before{
  content:""; }

.bp3-icon-print::before{
  content:"⎙"; }

.bp3-icon-projects::before{
  content:""; }

.bp3-icon-properties::before{
  content:""; }

.bp3-icon-property::before{
  content:""; }

.bp3-icon-publish-function::before{
  content:""; }

.bp3-icon-pulse::before{
  content:""; }

.bp3-icon-random::before{
  content:""; }

.bp3-icon-record::before{
  content:""; }

.bp3-icon-redo::before{
  content:""; }

.bp3-icon-refresh::before{
  content:""; }

.bp3-icon-regression-chart::before{
  content:""; }

.bp3-icon-remove::before{
  content:""; }

.bp3-icon-remove-column::before{
  content:""; }

.bp3-icon-remove-column-left::before{
  content:""; }

.bp3-icon-remove-column-right::before{
  content:""; }

.bp3-icon-remove-row-bottom::before{
  content:""; }

.bp3-icon-remove-row-top::before{
  content:""; }

.bp3-icon-repeat::before{
  content:""; }

.bp3-icon-reset::before{
  content:""; }

.bp3-icon-resolve::before{
  content:""; }

.bp3-icon-rig::before{
  content:""; }

.bp3-icon-right-join::before{
  content:""; }

.bp3-icon-ring::before{
  content:""; }

.bp3-icon-rotate-document::before{
  content:""; }

.bp3-icon-rotate-page::before{
  content:""; }

.bp3-icon-satellite::before{
  content:""; }

.bp3-icon-saved::before{
  content:""; }

.bp3-icon-scatter-plot::before{
  content:""; }

.bp3-icon-search::before{
  content:""; }

.bp3-icon-search-around::before{
  content:""; }

.bp3-icon-search-template::before{
  content:""; }

.bp3-icon-search-text::before{
  content:""; }

.bp3-icon-segmented-control::before{
  content:""; }

.bp3-icon-select::before{
  content:""; }

.bp3-icon-selection::before{
  content:"⦿"; }

.bp3-icon-send-to::before{
  content:""; }

.bp3-icon-send-to-graph::before{
  content:""; }

.bp3-icon-send-to-map::before{
  content:""; }

.bp3-icon-series-add::before{
  content:""; }

.bp3-icon-series-configuration::before{
  content:""; }

.bp3-icon-series-derived::before{
  content:""; }

.bp3-icon-series-filtered::before{
  content:""; }

.bp3-icon-series-search::before{
  content:""; }

.bp3-icon-settings::before{
  content:""; }

.bp3-icon-share::before{
  content:""; }

.bp3-icon-shield::before{
  content:""; }

.bp3-icon-shop::before{
  content:""; }

.bp3-icon-shopping-cart::before{
  content:""; }

.bp3-icon-signal-search::before{
  content:""; }

.bp3-icon-sim-card::before{
  content:""; }

.bp3-icon-slash::before{
  content:""; }

.bp3-icon-small-cross::before{
  content:""; }

.bp3-icon-small-minus::before{
  content:""; }

.bp3-icon-small-plus::before{
  content:""; }

.bp3-icon-small-tick::before{
  content:""; }

.bp3-icon-snowflake::before{
  content:""; }

.bp3-icon-social-media::before{
  content:""; }

.bp3-icon-sort::before{
  content:""; }

.bp3-icon-sort-alphabetical::before{
  content:""; }

.bp3-icon-sort-alphabetical-desc::before{
  content:""; }

.bp3-icon-sort-asc::before{
  content:""; }

.bp3-icon-sort-desc::before{
  content:""; }

.bp3-icon-sort-numerical::before{
  content:""; }

.bp3-icon-sort-numerical-desc::before{
  content:""; }

.bp3-icon-split-columns::before{
  content:""; }

.bp3-icon-square::before{
  content:""; }

.bp3-icon-stacked-chart::before{
  content:""; }

.bp3-icon-star::before{
  content:"★"; }

.bp3-icon-star-empty::before{
  content:"☆"; }

.bp3-icon-step-backward::before{
  content:""; }

.bp3-icon-step-chart::before{
  content:""; }

.bp3-icon-step-forward::before{
  content:""; }

.bp3-icon-stop::before{
  content:""; }

.bp3-icon-stopwatch::before{
  content:""; }

.bp3-icon-strikethrough::before{
  content:""; }

.bp3-icon-style::before{
  content:""; }

.bp3-icon-swap-horizontal::before{
  content:""; }

.bp3-icon-swap-vertical::before{
  content:""; }

.bp3-icon-symbol-circle::before{
  content:""; }

.bp3-icon-symbol-cross::before{
  content:""; }

.bp3-icon-symbol-diamond::before{
  content:""; }

.bp3-icon-symbol-square::before{
  content:""; }

.bp3-icon-symbol-triangle-down::before{
  content:""; }

.bp3-icon-symbol-triangle-up::before{
  content:""; }

.bp3-icon-tag::before{
  content:""; }

.bp3-icon-take-action::before{
  content:""; }

.bp3-icon-taxi::before{
  content:""; }

.bp3-icon-text-highlight::before{
  content:""; }

.bp3-icon-th::before{
  content:""; }

.bp3-icon-th-derived::before{
  content:""; }

.bp3-icon-th-disconnect::before{
  content:""; }

.bp3-icon-th-filtered::before{
  content:""; }

.bp3-icon-th-list::before{
  content:""; }

.bp3-icon-thumbs-down::before{
  content:""; }

.bp3-icon-thumbs-up::before{
  content:""; }

.bp3-icon-tick::before{
  content:"✓"; }

.bp3-icon-tick-circle::before{
  content:""; }

.bp3-icon-time::before{
  content:"⏲"; }

.bp3-icon-timeline-area-chart::before{
  content:""; }

.bp3-icon-timeline-bar-chart::before{
  content:""; }

.bp3-icon-timeline-events::before{
  content:""; }

.bp3-icon-timeline-line-chart::before{
  content:""; }

.bp3-icon-tint::before{
  content:""; }

.bp3-icon-torch::before{
  content:""; }

.bp3-icon-tractor::before{
  content:""; }

.bp3-icon-train::before{
  content:""; }

.bp3-icon-translate::before{
  content:""; }

.bp3-icon-trash::before{
  content:""; }

.bp3-icon-tree::before{
  content:""; }

.bp3-icon-trending-down::before{
  content:""; }

.bp3-icon-trending-up::before{
  content:""; }

.bp3-icon-truck::before{
  content:""; }

.bp3-icon-two-columns::before{
  content:""; }

.bp3-icon-unarchive::before{
  content:""; }

.bp3-icon-underline::before{
  content:"⎁"; }

.bp3-icon-undo::before{
  content:"⎌"; }

.bp3-icon-ungroup-objects::before{
  content:""; }

.bp3-icon-unknown-vehicle::before{
  content:""; }

.bp3-icon-unlock::before{
  content:""; }

.bp3-icon-unpin::before{
  content:""; }

.bp3-icon-unresolve::before{
  content:""; }

.bp3-icon-updated::before{
  content:""; }

.bp3-icon-upload::before{
  content:""; }

.bp3-icon-user::before{
  content:""; }

.bp3-icon-variable::before{
  content:""; }

.bp3-icon-vertical-bar-chart-asc::before{
  content:""; }

.bp3-icon-vertical-bar-chart-desc::before{
  content:""; }

.bp3-icon-vertical-distribution::before{
  content:""; }

.bp3-icon-video::before{
  content:""; }

.bp3-icon-volume-down::before{
  content:""; }

.bp3-icon-volume-off::before{
  content:""; }

.bp3-icon-volume-up::before{
  content:""; }

.bp3-icon-walk::before{
  content:""; }

.bp3-icon-warning-sign::before{
  content:""; }

.bp3-icon-waterfall-chart::before{
  content:""; }

.bp3-icon-widget::before{
  content:""; }

.bp3-icon-widget-button::before{
  content:""; }

.bp3-icon-widget-footer::before{
  content:""; }

.bp3-icon-widget-header::before{
  content:""; }

.bp3-icon-wrench::before{
  content:""; }

.bp3-icon-zoom-in::before{
  content:""; }

.bp3-icon-zoom-out::before{
  content:""; }

.bp3-icon-zoom-to-fit::before{
  content:""; }
.bp3-submenu > .bp3-popover-wrapper{
  display:block; }

.bp3-submenu .bp3-popover-target{
  display:block; }

.bp3-submenu.bp3-popover{
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0 5px; }
  .bp3-submenu.bp3-popover > .bp3-popover-content{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-submenu.bp3-popover, .bp3-submenu.bp3-popover.bp3-dark{
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-dark .bp3-submenu.bp3-popover > .bp3-popover-content, .bp3-submenu.bp3-popover.bp3-dark > .bp3-popover-content{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
.bp3-menu{
  margin:0;
  border-radius:3px;
  background:#ffffff;
  min-width:180px;
  padding:5px;
  list-style:none;
  text-align:left;
  color:#182026; }

.bp3-menu-divider{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-menu-divider{
    border-top-color:rgba(255, 255, 255, 0.15); }

.bp3-menu-item{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  border-radius:2px;
  padding:5px 7px;
  text-decoration:none;
  line-height:20px;
  color:inherit;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-menu-item > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-menu-item > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-menu-item::before,
  .bp3-menu-item > *{
    margin-right:7px; }
  .bp3-menu-item:empty::before,
  .bp3-menu-item > :last-child{
    margin-right:0; }
  .bp3-menu-item > .bp3-fill{
    word-break:break-word; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    background-color:rgba(167, 182, 194, 0.3);
    cursor:pointer;
    text-decoration:none; }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-dark .bp3-menu-item{
    color:inherit; }
    .bp3-dark .bp3-menu-item:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
      background-color:rgba(138, 155, 168, 0.15);
      color:inherit; }
    .bp3-dark .bp3-menu-item.bp3-disabled{
      background-color:inherit;
      color:rgba(167, 182, 194, 0.6); }
  .bp3-menu-item.bp3-intent-primary{
    color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-primary::before, .bp3-menu-item.bp3-intent-primary::after,
    .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
      color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary.bp3-active{
      background-color:#137cbd; }
    .bp3-menu-item.bp3-intent-primary:active{
      background-color:#106ba3; }
    .bp3-menu-item.bp3-intent-primary:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary:active, .bp3-menu-item.bp3-intent-primary:active::before, .bp3-menu-item.bp3-intent-primary:active::after,
    .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-menu-item.bp3-intent-primary.bp3-active::after,
    .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-success{
    color:#0d8050; }
    .bp3-menu-item.bp3-intent-success .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-success::before, .bp3-menu-item.bp3-intent-success::after,
    .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
      color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success.bp3-active{
      background-color:#0f9960; }
    .bp3-menu-item.bp3-intent-success:active{
      background-color:#0d8050; }
    .bp3-menu-item.bp3-intent-success:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-menu-item.bp3-intent-success:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-menu-item.bp3-intent-success:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success:active, .bp3-menu-item.bp3-intent-success:active::before, .bp3-menu-item.bp3-intent-success:active::after,
    .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-menu-item.bp3-intent-success.bp3-active::after,
    .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-warning{
    color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-warning::before, .bp3-menu-item.bp3-intent-warning::after,
    .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
      color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning.bp3-active{
      background-color:#d9822b; }
    .bp3-menu-item.bp3-intent-warning:active{
      background-color:#bf7326; }
    .bp3-menu-item.bp3-intent-warning:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning:active, .bp3-menu-item.bp3-intent-warning:active::before, .bp3-menu-item.bp3-intent-warning:active::after,
    .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-menu-item.bp3-intent-warning.bp3-active::after,
    .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item.bp3-intent-danger{
    color:#c23030; }
    .bp3-menu-item.bp3-intent-danger .bp3-icon{
      color:inherit; }
    .bp3-menu-item.bp3-intent-danger::before, .bp3-menu-item.bp3-intent-danger::after,
    .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
      color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger.bp3-active{
      background-color:#db3737; }
    .bp3-menu-item.bp3-intent-danger:active{
      background-color:#c23030; }
    .bp3-menu-item.bp3-intent-danger:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
    .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
    .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger:active, .bp3-menu-item.bp3-intent-danger:active::before, .bp3-menu-item.bp3-intent-danger:active::after,
    .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-menu-item.bp3-intent-danger.bp3-active::after,
    .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
      color:#ffffff; }
  .bp3-menu-item::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    margin-right:7px; }
  .bp3-menu-item::before,
  .bp3-menu-item > .bp3-icon{
    margin-top:2px;
    color:#5c7080; }
  .bp3-menu-item .bp3-menu-item-label{
    color:#5c7080; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    color:inherit; }
  .bp3-menu-item.bp3-active, .bp3-menu-item:active{
    background-color:rgba(115, 134, 148, 0.3); }
  .bp3-menu-item.bp3-disabled{
    outline:none !important;
    background-color:inherit !important;
    cursor:not-allowed !important;
    color:rgba(92, 112, 128, 0.6) !important; }
    .bp3-menu-item.bp3-disabled::before,
    .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-large .bp3-menu-item{
    padding:9px 7px;
    line-height:22px;
    font-size:16px; }
    .bp3-large .bp3-menu-item .bp3-icon{
      margin-top:3px; }
    .bp3-large .bp3-menu-item::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      margin-top:1px;
      margin-right:10px; }

button.bp3-menu-item{
  border:none;
  background:none;
  width:100%;
  text-align:left; }
.bp3-menu-header{
  display:block;
  margin:5px;
  border-top:1px solid rgba(16, 22, 26, 0.15);
  cursor:default;
  padding-left:2px; }
  .bp3-dark .bp3-menu-header{
    border-top-color:rgba(255, 255, 255, 0.15); }
  .bp3-menu-header:first-of-type{
    border-top:none; }
  .bp3-menu-header > h6{
    color:#182026;
    font-weight:600;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    margin:0;
    padding:10px 7px 0 1px;
    line-height:17px; }
    .bp3-dark .bp3-menu-header > h6{
      color:#f5f8fa; }
  .bp3-menu-header:first-of-type > h6{
    padding-top:0; }
  .bp3-large .bp3-menu-header > h6{
    padding-top:15px;
    padding-bottom:5px;
    font-size:18px; }
  .bp3-large .bp3-menu-header:first-of-type > h6{
    padding-top:0; }

.bp3-dark .bp3-menu{
  background:#30404d;
  color:#f5f8fa; }

.bp3-dark .bp3-menu-item.bp3-intent-primary{
  color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary::before, .bp3-dark .bp3-menu-item.bp3-intent-primary::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary .bp3-menu-item-label{
    color:#48aff0; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active{
    background-color:#137cbd; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active{
    background-color:#106ba3; }
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-primary.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary:active, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-primary.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-success{
  color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-success::before, .bp3-dark .bp3-menu-item.bp3-intent-success::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success .bp3-menu-item-label{
    color:#3dcc91; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active{
    background-color:#0f9960; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:active{
    background-color:#0d8050; }
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-success:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-success.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success:active, .bp3-dark .bp3-menu-item.bp3-intent-success:active::before, .bp3-dark .bp3-menu-item.bp3-intent-success:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-success.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-warning{
  color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning::before, .bp3-dark .bp3-menu-item.bp3-intent-warning::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning .bp3-menu-item-label{
    color:#ffb366; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active{
    background-color:#d9822b; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active{
    background-color:#bf7326; }
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-warning.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning:active, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-warning.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item.bp3-intent-danger{
  color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-icon{
    color:inherit; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger::before, .bp3-dark .bp3-menu-item.bp3-intent-danger::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger .bp3-menu-item-label{
    color:#ff7373; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active{
    background-color:#db3737; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active{
    background-color:#c23030; }
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::before, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:hover::after, .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after, .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:hover .bp3-menu-item-label,
  .bp3-dark .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label,
  .bp3-submenu .bp3-dark .bp3-popover-target.bp3-popover-open > .bp3-intent-danger.bp3-menu-item .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger:active, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger:active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger:active .bp3-menu-item-label, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::before, .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active::after,
  .bp3-dark .bp3-menu-item.bp3-intent-danger.bp3-active .bp3-menu-item-label{
    color:#ffffff; }

.bp3-dark .bp3-menu-item::before,
.bp3-dark .bp3-menu-item > .bp3-icon{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item .bp3-menu-item-label{
  color:#a7b6c2; }

.bp3-dark .bp3-menu-item.bp3-active, .bp3-dark .bp3-menu-item:active{
  background-color:rgba(138, 155, 168, 0.3); }

.bp3-dark .bp3-menu-item.bp3-disabled{
  color:rgba(167, 182, 194, 0.6) !important; }
  .bp3-dark .bp3-menu-item.bp3-disabled::before,
  .bp3-dark .bp3-menu-item.bp3-disabled > .bp3-icon,
  .bp3-dark .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
    color:rgba(167, 182, 194, 0.6) !important; }

.bp3-dark .bp3-menu-divider,
.bp3-dark .bp3-menu-header{
  border-color:rgba(255, 255, 255, 0.15); }

.bp3-dark .bp3-menu-header > h6{
  color:#f5f8fa; }

.bp3-label .bp3-menu{
  margin-top:5px; }
.bp3-navbar{
  position:relative;
  z-index:10;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:100%;
  height:50px;
  padding:0 15px; }
  .bp3-navbar.bp3-dark,
  .bp3-dark .bp3-navbar{
    background-color:#394b59; }
  .bp3-navbar.bp3-dark{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-navbar{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4); }
  .bp3-navbar.bp3-fixed-top{
    position:fixed;
    top:0;
    right:0;
    left:0; }

.bp3-navbar-heading{
  margin-right:15px;
  font-size:16px; }

.bp3-navbar-group{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  height:50px; }
  .bp3-navbar-group.bp3-align-left{
    float:left; }
  .bp3-navbar-group.bp3-align-right{
    float:right; }

.bp3-navbar-divider{
  margin:0 10px;
  border-left:1px solid rgba(16, 22, 26, 0.15);
  height:20px; }
  .bp3-dark .bp3-navbar-divider{
    border-left-color:rgba(255, 255, 255, 0.15); }
.bp3-non-ideal-state{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:100%;
  height:100%;
  text-align:center; }
  .bp3-non-ideal-state > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-non-ideal-state > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-non-ideal-state::before,
  .bp3-non-ideal-state > *{
    margin-bottom:20px; }
  .bp3-non-ideal-state:empty::before,
  .bp3-non-ideal-state > :last-child{
    margin-bottom:0; }
  .bp3-non-ideal-state > *{
    max-width:400px; }

.bp3-non-ideal-state-visual{
  color:rgba(92, 112, 128, 0.6);
  font-size:60px; }
  .bp3-dark .bp3-non-ideal-state-visual{
    color:rgba(167, 182, 194, 0.6); }

.bp3-overflow-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:nowrap;
      flex-wrap:nowrap;
  min-width:0; }

.bp3-overflow-list-spacer{
  -ms-flex-negative:1;
      flex-shrink:1;
  width:1px; }

body.bp3-overlay-open{
  overflow:hidden; }

.bp3-overlay{
  position:static;
  top:0;
  right:0;
  bottom:0;
  left:0;
  z-index:20; }
  .bp3-overlay:not(.bp3-overlay-open){
    pointer-events:none; }
  .bp3-overlay.bp3-overlay-container{
    position:fixed;
    overflow:hidden; }
    .bp3-overlay.bp3-overlay-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-scroll-container{
    position:fixed;
    overflow:auto; }
    .bp3-overlay.bp3-overlay-scroll-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-inline{
    display:inline;
    overflow:visible; }

.bp3-overlay-content{
  position:fixed;
  z-index:20; }
  .bp3-overlay-inline .bp3-overlay-content,
  .bp3-overlay-scroll-container .bp3-overlay-content{
    position:absolute; }

.bp3-overlay-backdrop{
  position:fixed;
  top:0;
  right:0;
  bottom:0;
  left:0;
  opacity:1;
  z-index:20;
  background-color:rgba(16, 22, 26, 0.7);
  overflow:auto;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-overlay-backdrop.bp3-overlay-enter, .bp3-overlay-backdrop.bp3-overlay-appear{
    opacity:0; }
  .bp3-overlay-backdrop.bp3-overlay-enter-active, .bp3-overlay-backdrop.bp3-overlay-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop.bp3-overlay-exit{
    opacity:1; }
  .bp3-overlay-backdrop.bp3-overlay-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-overlay-backdrop:focus{
    outline:none; }
  .bp3-overlay-inline .bp3-overlay-backdrop{
    position:absolute; }
.bp3-panel-stack{
  position:relative;
  overflow:hidden; }

.bp3-panel-stack-header{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  z-index:1;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  height:30px; }
  .bp3-dark .bp3-panel-stack-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack-header > span{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1;
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch; }
  .bp3-panel-stack-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack-view{
  position:absolute;
  top:0;
  right:0;
  bottom:0;
  left:0;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  background-color:#ffffff;
  overflow-y:auto; }
  .bp3-dark .bp3-panel-stack-view{
    background-color:#30404d; }

.bp3-panel-stack-push .bp3-panel-stack-enter, .bp3-panel-stack-push .bp3-panel-stack-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack-push .bp3-panel-stack-enter-active, .bp3-panel-stack-push .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-push .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-push .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter, .bp3-panel-stack-pop .bp3-panel-stack-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter-active, .bp3-panel-stack-pop .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }

.bp3-panel-stack-pop .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-pop .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease;
  -webkit-transition-delay:0;
          transition-delay:0; }
.bp3-popover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1);
  display:inline-block;
  z-index:20;
  border-radius:3px; }
  .bp3-popover .bp3-popover-arrow{
    position:absolute;
    width:30px;
    height:30px; }
    .bp3-popover .bp3-popover-arrow::before{
      margin:5px;
      width:20px;
      height:20px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover{
    margin-top:-17px;
    margin-bottom:17px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
      bottom:-11px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover{
    margin-left:17px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
      left:-11px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover{
    margin-top:17px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
      top:-11px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover{
    margin-right:17px;
    margin-left:-17px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
      right:-11px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-popover > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-popover > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-popover > .bp3-popover-arrow{
    top:-0.3934px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-popover > .bp3-popover-arrow{
    right:-0.3934px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-popover > .bp3-popover-arrow{
    left:-0.3934px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-popover > .bp3-popover-arrow{
    bottom:-0.3934px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-popover{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-popover{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-popover{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-popover .bp3-popover-content{
    background:#ffffff;
    color:inherit; }
  .bp3-popover .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-popover .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-popover .bp3-popover-arrow-fill{
    fill:#ffffff; }
  .bp3-popover-enter > .bp3-popover, .bp3-popover-appear > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3); }
  .bp3-popover-enter-active > .bp3-popover, .bp3-popover-appear-active > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover .bp3-popover-content{
    position:relative;
    border-radius:3px; }
  .bp3-popover.bp3-popover-content-sizing .bp3-popover-content{
    max-width:350px;
    padding:20px; }
  .bp3-popover-target + .bp3-overlay .bp3-popover.bp3-popover-content-sizing{
    width:350px; }
  .bp3-popover.bp3-minimal{
    margin:0 !important; }
    .bp3-popover.bp3-minimal .bp3-popover-arrow{
      display:none; }
    .bp3-popover.bp3-minimal.bp3-popover{
      -webkit-transform:scale(1);
              transform:scale(1); }
      .bp3-popover-enter > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-enter-active > .bp3-popover.bp3-minimal.bp3-popover, .bp3-popover-appear-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
      .bp3-popover-exit > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-exit-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
        -webkit-transition-delay:0;
                transition-delay:0; }
  .bp3-popover.bp3-dark,
  .bp3-dark .bp3-popover{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-popover .bp3-popover-content{
      background:#30404d;
      color:inherit; }
    .bp3-popover.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-popover .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-popover.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-popover .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-popover.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-popover .bp3-popover-arrow-fill{
      fill:#30404d; }

.bp3-popover-arrow::before{
  display:block;
  position:absolute;
  -webkit-transform:rotate(45deg);
          transform:rotate(45deg);
  border-radius:2px;
  content:""; }

.bp3-tether-pinned .bp3-popover-arrow{
  display:none; }

.bp3-popover-backdrop{
  background:rgba(255, 255, 255, 0); }

.bp3-transition-container{
  opacity:1;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  z-index:20; }
  .bp3-transition-container.bp3-popover-enter, .bp3-transition-container.bp3-popover-appear{
    opacity:0; }
  .bp3-transition-container.bp3-popover-enter-active, .bp3-transition-container.bp3-popover-appear-active{
    opacity:1;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container.bp3-popover-exit{
    opacity:1; }
  .bp3-transition-container.bp3-popover-exit-active{
    opacity:0;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-transition-container:focus{
    outline:none; }
  .bp3-transition-container.bp3-popover-leave .bp3-popover-content{
    pointer-events:none; }
  .bp3-transition-container[data-x-out-of-boundaries]{
    display:none; }

span.bp3-popover-target{
  display:inline-block; }

.bp3-popover-wrapper.bp3-fill{
  width:100%; }

.bp3-portal{
  position:absolute;
  top:0;
  right:0;
  left:0; }
@-webkit-keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }
@keyframes linear-progress-bar-stripes{
  from{
    background-position:0 0; }
  to{
    background-position:30px 0; } }

.bp3-progress-bar{
  display:block;
  position:relative;
  border-radius:40px;
  background:rgba(92, 112, 128, 0.2);
  width:100%;
  height:8px;
  overflow:hidden; }
  .bp3-progress-bar .bp3-progress-meter{
    position:absolute;
    border-radius:40px;
    background:linear-gradient(-45deg, rgba(255, 255, 255, 0.2) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.2) 50%, rgba(255, 255, 255, 0.2) 75%, transparent 75%);
    background-color:rgba(92, 112, 128, 0.8);
    background-size:30px 30px;
    width:100%;
    height:100%;
    -webkit-transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-progress-bar:not(.bp3-no-animation):not(.bp3-no-stripes) .bp3-progress-meter{
    animation:linear-progress-bar-stripes 300ms linear infinite reverse; }
  .bp3-progress-bar.bp3-no-stripes .bp3-progress-meter{
    background-image:none; }

.bp3-dark .bp3-progress-bar{
  background:rgba(16, 22, 26, 0.5); }
  .bp3-dark .bp3-progress-bar .bp3-progress-meter{
    background-color:#8a9ba8; }

.bp3-progress-bar.bp3-intent-primary .bp3-progress-meter{
  background-color:#137cbd; }

.bp3-progress-bar.bp3-intent-success .bp3-progress-meter{
  background-color:#0f9960; }

.bp3-progress-bar.bp3-intent-warning .bp3-progress-meter{
  background-color:#d9822b; }

.bp3-progress-bar.bp3-intent-danger .bp3-progress-meter{
  background-color:#db3737; }
@-webkit-keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
@keyframes skeleton-glow{
  from{
    border-color:rgba(206, 217, 224, 0.2);
    background:rgba(206, 217, 224, 0.2); }
  to{
    border-color:rgba(92, 112, 128, 0.2);
    background:rgba(92, 112, 128, 0.2); } }
.bp3-skeleton{
  border-color:rgba(206, 217, 224, 0.2) !important;
  border-radius:2px;
  -webkit-box-shadow:none !important;
          box-shadow:none !important;
  background:rgba(206, 217, 224, 0.2);
  background-clip:padding-box !important;
  cursor:default;
  color:transparent !important;
  -webkit-animation:1000ms linear infinite alternate skeleton-glow;
          animation:1000ms linear infinite alternate skeleton-glow;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-skeleton::before, .bp3-skeleton::after,
  .bp3-skeleton *{
    visibility:hidden !important; }
.bp3-slider{
  width:100%;
  min-width:150px;
  height:40px;
  position:relative;
  outline:none;
  cursor:default;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-slider:hover{
    cursor:pointer; }
  .bp3-slider:active{
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-slider.bp3-disabled{
    opacity:0.5;
    cursor:not-allowed; }
  .bp3-slider.bp3-slider-unlabeled{
    height:16px; }

.bp3-slider-track,
.bp3-slider-progress{
  top:5px;
  right:0;
  left:0;
  height:6px;
  position:absolute; }

.bp3-slider-track{
  border-radius:3px;
  overflow:hidden; }

.bp3-slider-progress{
  background:rgba(92, 112, 128, 0.2); }
  .bp3-dark .bp3-slider-progress{
    background:rgba(16, 22, 26, 0.5); }
  .bp3-slider-progress.bp3-intent-primary{
    background-color:#137cbd; }
  .bp3-slider-progress.bp3-intent-success{
    background-color:#0f9960; }
  .bp3-slider-progress.bp3-intent-warning{
    background-color:#d9822b; }
  .bp3-slider-progress.bp3-intent-danger{
    background-color:#db3737; }

.bp3-slider-handle{
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  color:#182026;
  position:absolute;
  top:0;
  left:0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
  cursor:pointer;
  width:16px;
  height:16px; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5; }
  .bp3-slider-handle:active, .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none; }
  .bp3-slider-handle:disabled, .bp3-slider-handle.bp3-disabled{
    outline:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
    .bp3-slider-handle:disabled.bp3-active, .bp3-slider-handle:disabled.bp3-active:hover, .bp3-slider-handle.bp3-disabled.bp3-active, .bp3-slider-handle.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }
  .bp3-slider-handle:focus{
    z-index:1; }
  .bp3-slider-handle:hover{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    background-clip:padding-box;
    background-color:#ebf1f5;
    z-index:2;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
    cursor:-webkit-grab;
    cursor:grab; }
  .bp3-slider-handle.bp3-active{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-disabled .bp3-slider-handle{
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#bfccd6;
    pointer-events:none; }
  .bp3-dark .bp3-slider-handle{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover, .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      background-color:#30404d; }
    .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
      background-color:#202b33;
      background-image:none; }
    .bp3-dark .bp3-slider-handle:disabled, .bp3-dark .bp3-slider-handle.bp3-disabled{
      -webkit-box-shadow:none;
              box-shadow:none;
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      color:rgba(167, 182, 194, 0.6); }
      .bp3-dark .bp3-slider-handle:disabled.bp3-active, .bp3-dark .bp3-slider-handle.bp3-disabled.bp3-active{
        background:rgba(57, 75, 89, 0.7); }
    .bp3-dark .bp3-slider-handle .bp3-button-spinner .bp3-spinner-head{
      background:rgba(16, 22, 26, 0.5);
      stroke:#8a9ba8; }
    .bp3-dark .bp3-slider-handle, .bp3-dark .bp3-slider-handle:hover{
      background-color:#394b59; }
    .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#293742; }
  .bp3-dark .bp3-disabled .bp3-slider-handle{
    border-color:#5c7080;
    -webkit-box-shadow:none;
            box-shadow:none;
    background:#5c7080; }
  .bp3-slider-handle .bp3-slider-label{
    margin-left:8px;
    border-radius:3px;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
    background:#394b59;
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
      background:#e1e8ed;
      color:#394b59; }
    .bp3-disabled .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-slider-handle.bp3-start, .bp3-slider-handle.bp3-end{
    width:8px; }
  .bp3-slider-handle.bp3-start{
    border-top-right-radius:0;
    border-bottom-right-radius:0; }
  .bp3-slider-handle.bp3-end{
    margin-left:8px;
    border-top-left-radius:0;
    border-bottom-left-radius:0; }
    .bp3-slider-handle.bp3-end .bp3-slider-label{
      margin-left:0; }

.bp3-slider-label{
  -webkit-transform:translate(-50%, 20px);
          transform:translate(-50%, 20px);
  display:inline-block;
  position:absolute;
  padding:2px 5px;
  vertical-align:top;
  line-height:1;
  font-size:12px; }

.bp3-slider.bp3-vertical{
  width:40px;
  min-width:40px;
  height:150px; }
  .bp3-slider.bp3-vertical .bp3-slider-track,
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:0;
    bottom:0;
    left:5px;
    width:6px;
    height:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-label{
    -webkit-transform:translate(20px, 50%);
            transform:translate(20px, 50%); }
  .bp3-slider.bp3-vertical .bp3-slider-handle{
    top:auto; }
    .bp3-slider.bp3-vertical .bp3-slider-handle .bp3-slider-label{
      margin-top:-8px;
      margin-left:0; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end, .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      margin-left:0;
      width:16px;
      height:8px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      border-top-left-radius:0;
      border-bottom-right-radius:3px; }
      .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start .bp3-slider-label{
        -webkit-transform:translate(20px);
                transform:translate(20px); }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end{
      margin-bottom:8px;
      border-top-left-radius:3px;
      border-bottom-left-radius:0;
      border-bottom-right-radius:0; }

@-webkit-keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

@keyframes pt-spinner-animation{
  from{
    -webkit-transform:rotate(0deg);
            transform:rotate(0deg); }
  to{
    -webkit-transform:rotate(360deg);
            transform:rotate(360deg); } }

.bp3-spinner{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  overflow:visible;
  vertical-align:middle; }
  .bp3-spinner svg{
    display:block; }
  .bp3-spinner path{
    fill-opacity:0; }
  .bp3-spinner .bp3-spinner-head{
    -webkit-transform-origin:center;
            transform-origin:center;
    -webkit-transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    stroke:rgba(92, 112, 128, 0.8);
    stroke-linecap:round; }
  .bp3-spinner .bp3-spinner-track{
    stroke:rgba(92, 112, 128, 0.2); }

.bp3-spinner-animation{
  -webkit-animation:pt-spinner-animation 500ms linear infinite;
          animation:pt-spinner-animation 500ms linear infinite; }
  .bp3-no-spin > .bp3-spinner-animation{
    -webkit-animation:none;
            animation:none; }

.bp3-dark .bp3-spinner .bp3-spinner-head{
  stroke:#8a9ba8; }

.bp3-dark .bp3-spinner .bp3-spinner-track{
  stroke:rgba(16, 22, 26, 0.5); }

.bp3-spinner.bp3-intent-primary .bp3-spinner-head{
  stroke:#137cbd; }

.bp3-spinner.bp3-intent-success .bp3-spinner-head{
  stroke:#0f9960; }

.bp3-spinner.bp3-intent-warning .bp3-spinner-head{
  stroke:#d9822b; }

.bp3-spinner.bp3-intent-danger .bp3-spinner-head{
  stroke:#db3737; }
.bp3-tabs.bp3-vertical{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }
  .bp3-tabs.bp3-vertical > .bp3-tab-list{
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab{
      border-radius:3px;
      width:100%;
      padding:0 10px; }
      .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab[aria-selected="true"]{
        -webkit-box-shadow:none;
                box-shadow:none;
        background-color:rgba(19, 124, 189, 0.2); }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab-indicator-wrapper .bp3-tab-indicator{
      top:0;
      right:0;
      bottom:0;
      left:0;
      border-radius:3px;
      background-color:rgba(19, 124, 189, 0.2);
      height:auto; }
  .bp3-tabs.bp3-vertical > .bp3-tab-panel{
    margin-top:0;
    padding-left:20px; }

.bp3-tab-list{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  -webkit-box-align:end;
      -ms-flex-align:end;
          align-items:flex-end;
  position:relative;
  margin:0;
  border:none;
  padding:0;
  list-style:none; }
  .bp3-tab-list > *:not(:last-child){
    margin-right:20px; }

.bp3-tab{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  position:relative;
  cursor:pointer;
  max-width:100%;
  vertical-align:top;
  line-height:30px;
  color:#182026;
  font-size:14px; }
  .bp3-tab a{
    display:block;
    text-decoration:none;
    color:inherit; }
  .bp3-tab-indicator-wrapper ~ .bp3-tab{
    -webkit-box-shadow:none !important;
            box-shadow:none !important;
    background-color:transparent !important; }
  .bp3-tab[aria-disabled="true"]{
    cursor:not-allowed;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-tab[aria-selected="true"]{
    border-radius:0;
    -webkit-box-shadow:inset 0 -3px 0 #106ba3;
            box-shadow:inset 0 -3px 0 #106ba3; }
  .bp3-tab[aria-selected="true"], .bp3-tab:not([aria-disabled="true"]):hover{
    color:#106ba3; }
  .bp3-tab:focus{
    -moz-outline-radius:0; }
  .bp3-large > .bp3-tab{
    line-height:40px;
    font-size:16px; }

.bp3-tab-panel{
  margin-top:20px; }
  .bp3-tab-panel[aria-hidden="true"]{
    display:none; }

.bp3-tab-indicator-wrapper{
  position:absolute;
  top:0;
  left:0;
  -webkit-transform:translateX(0), translateY(0);
          transform:translateX(0), translateY(0);
  -webkit-transition:height, width, -webkit-transform;
  transition:height, width, -webkit-transform;
  transition:height, transform, width;
  transition:height, transform, width, -webkit-transform;
  -webkit-transition-duration:200ms;
          transition-duration:200ms;
  -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
          transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
  pointer-events:none; }
  .bp3-tab-indicator-wrapper .bp3-tab-indicator{
    position:absolute;
    right:0;
    bottom:0;
    left:0;
    background-color:#106ba3;
    height:3px; }
  .bp3-tab-indicator-wrapper.bp3-no-animation{
    -webkit-transition:none;
    transition:none; }

.bp3-dark .bp3-tab{
  color:#f5f8fa; }
  .bp3-dark .bp3-tab[aria-disabled="true"]{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tab[aria-selected="true"]{
    -webkit-box-shadow:inset 0 -3px 0 #48aff0;
            box-shadow:inset 0 -3px 0 #48aff0; }
  .bp3-dark .bp3-tab[aria-selected="true"], .bp3-dark .bp3-tab:not([aria-disabled="true"]):hover{
    color:#48aff0; }

.bp3-dark .bp3-tab-indicator{
  background-color:#48aff0; }

.bp3-flex-expander{
  -webkit-box-flex:1;
      -ms-flex:1 1;
          flex:1 1; }
.bp3-tag{
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:relative;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:none;
          box-shadow:none;
  background-color:#5c7080;
  min-width:20px;
  max-width:100%;
  min-height:20px;
  padding:2px 6px;
  line-height:16px;
  color:#f5f8fa;
  font-size:12px; }
  .bp3-tag.bp3-interactive{
    cursor:pointer; }
    .bp3-tag.bp3-interactive:hover{
      background-color:rgba(92, 112, 128, 0.85); }
    .bp3-tag.bp3-interactive.bp3-active, .bp3-tag.bp3-interactive:active{
      background-color:rgba(92, 112, 128, 0.7); }
  .bp3-tag > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag > .bp3-fill{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag::before,
  .bp3-tag > *{
    margin-right:4px; }
  .bp3-tag:empty::before,
  .bp3-tag > :last-child{
    margin-right:0; }
  .bp3-tag:focus{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:0;
    -moz-outline-radius:6px; }
  .bp3-tag.bp3-round{
    border-radius:30px;
    padding-right:8px;
    padding-left:8px; }
  .bp3-dark .bp3-tag{
    background-color:#bfccd6;
    color:#182026; }
    .bp3-dark .bp3-tag.bp3-interactive{
      cursor:pointer; }
      .bp3-dark .bp3-tag.bp3-interactive:hover{
        background-color:rgba(191, 204, 214, 0.85); }
      .bp3-dark .bp3-tag.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-interactive:active{
        background-color:rgba(191, 204, 214, 0.7); }
    .bp3-dark .bp3-tag > .bp3-icon, .bp3-dark .bp3-tag .bp3-icon-standard, .bp3-dark .bp3-tag .bp3-icon-large{
      fill:currentColor; }
  .bp3-tag > .bp3-icon, .bp3-tag .bp3-icon-standard, .bp3-tag .bp3-icon-large{
    fill:#ffffff; }
  .bp3-tag.bp3-large,
  .bp3-large .bp3-tag{
    min-width:30px;
    min-height:30px;
    padding:0 10px;
    line-height:20px;
    font-size:14px; }
    .bp3-tag.bp3-large::before,
    .bp3-tag.bp3-large > *,
    .bp3-large .bp3-tag::before,
    .bp3-large .bp3-tag > *{
      margin-right:7px; }
    .bp3-tag.bp3-large:empty::before,
    .bp3-tag.bp3-large > :last-child,
    .bp3-large .bp3-tag:empty::before,
    .bp3-large .bp3-tag > :last-child{
      margin-right:0; }
    .bp3-tag.bp3-large.bp3-round,
    .bp3-large .bp3-tag.bp3-round{
      padding-right:12px;
      padding-left:12px; }
  .bp3-tag.bp3-intent-primary{
    background:#137cbd;
    color:#ffffff; }
    .bp3-tag.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.85); }
      .bp3-tag.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.7); }
  .bp3-tag.bp3-intent-success{
    background:#0f9960;
    color:#ffffff; }
    .bp3-tag.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.85); }
      .bp3-tag.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.7); }
  .bp3-tag.bp3-intent-warning{
    background:#d9822b;
    color:#ffffff; }
    .bp3-tag.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.85); }
      .bp3-tag.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.7); }
  .bp3-tag.bp3-intent-danger{
    background:#db3737;
    color:#ffffff; }
    .bp3-tag.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.85); }
      .bp3-tag.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.7); }
  .bp3-tag.bp3-fill{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    width:100%; }
  .bp3-tag.bp3-minimal > .bp3-icon, .bp3-tag.bp3-minimal .bp3-icon-standard, .bp3-tag.bp3-minimal .bp3-icon-large{
    fill:#5c7080; }
  .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
    background-color:rgba(138, 155, 168, 0.2);
    color:#182026; }
    .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
        background-color:rgba(92, 112, 128, 0.3); }
      .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
        background-color:rgba(92, 112, 128, 0.4); }
    .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]){
      color:#f5f8fa; }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:hover{
          background-color:rgba(191, 204, 214, 0.3); }
        .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]).bp3-interactive:active{
          background-color:rgba(191, 204, 214, 0.4); }
      .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) > .bp3-icon, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-standard, .bp3-dark .bp3-tag.bp3-minimal:not([class*="bp3-intent-"]) .bp3-icon-large{
        fill:#a7b6c2; }
  .bp3-tag.bp3-minimal.bp3-intent-primary{
    background-color:rgba(19, 124, 189, 0.15);
    color:#106ba3; }
    .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
        background-color:rgba(19, 124, 189, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
        background-color:rgba(19, 124, 189, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-primary > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-primary .bp3-icon-large{
      fill:#137cbd; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary{
      background-color:rgba(19, 124, 189, 0.25);
      color:#48aff0; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:hover{
          background-color:rgba(19, 124, 189, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-primary.bp3-interactive:active{
          background-color:rgba(19, 124, 189, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-success{
    background-color:rgba(15, 153, 96, 0.15);
    color:#0d8050; }
    .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
        background-color:rgba(15, 153, 96, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
        background-color:rgba(15, 153, 96, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-success > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-success .bp3-icon-large{
      fill:#0f9960; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success{
      background-color:rgba(15, 153, 96, 0.25);
      color:#3dcc91; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:hover{
          background-color:rgba(15, 153, 96, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-success.bp3-interactive:active{
          background-color:rgba(15, 153, 96, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-warning{
    background-color:rgba(217, 130, 43, 0.15);
    color:#bf7326; }
    .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
        background-color:rgba(217, 130, 43, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
        background-color:rgba(217, 130, 43, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-warning > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-warning .bp3-icon-large{
      fill:#d9822b; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning{
      background-color:rgba(217, 130, 43, 0.25);
      color:#ffb366; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:hover{
          background-color:rgba(217, 130, 43, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-warning.bp3-interactive:active{
          background-color:rgba(217, 130, 43, 0.45); }
  .bp3-tag.bp3-minimal.bp3-intent-danger{
    background-color:rgba(219, 55, 55, 0.15);
    color:#c23030; }
    .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
      cursor:pointer; }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
        background-color:rgba(219, 55, 55, 0.25); }
      .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
        background-color:rgba(219, 55, 55, 0.35); }
    .bp3-tag.bp3-minimal.bp3-intent-danger > .bp3-icon, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-standard, .bp3-tag.bp3-minimal.bp3-intent-danger .bp3-icon-large{
      fill:#db3737; }
    .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger{
      background-color:rgba(219, 55, 55, 0.25);
      color:#ff7373; }
      .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive{
        cursor:pointer; }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:hover{
          background-color:rgba(219, 55, 55, 0.35); }
        .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive.bp3-active, .bp3-dark .bp3-tag.bp3-minimal.bp3-intent-danger.bp3-interactive:active{
          background-color:rgba(219, 55, 55, 0.45); }

.bp3-tag-remove{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  opacity:0.5;
  margin-top:-2px;
  margin-right:-6px !important;
  margin-bottom:-2px;
  border:none;
  background:none;
  cursor:pointer;
  padding:2px;
  padding-left:0;
  color:inherit; }
  .bp3-tag-remove:hover{
    opacity:0.8;
    background:none;
    text-decoration:none; }
  .bp3-tag-remove:active{
    opacity:1; }
  .bp3-tag-remove:empty::before{
    line-height:1;
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-weight:400;
    font-style:normal;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    content:""; }
  .bp3-large .bp3-tag-remove{
    margin-right:-10px !important;
    padding:5px;
    padding-left:0; }
    .bp3-large .bp3-tag-remove:empty::before{
      line-height:1;
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-weight:400;
      font-style:normal; }
.bp3-tag-input{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:horizontal;
  -webkit-box-direction:normal;
      -ms-flex-direction:row;
          flex-direction:row;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  cursor:text;
  height:auto;
  min-height:30px;
  padding-right:0;
  padding-left:5px;
  line-height:inherit; }
  .bp3-tag-input > *{
    -webkit-box-flex:0;
        -ms-flex-positive:0;
            flex-grow:0;
    -ms-flex-negative:0;
        flex-shrink:0; }
  .bp3-tag-input > .bp3-tag-input-values{
    -webkit-box-flex:1;
        -ms-flex-positive:1;
            flex-grow:1;
    -ms-flex-negative:1;
        flex-shrink:1; }
  .bp3-tag-input .bp3-tag-input-icon{
    margin-top:7px;
    margin-right:7px;
    margin-left:2px;
    color:#5c7080; }
  .bp3-tag-input .bp3-tag-input-values{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -ms-flex-wrap:wrap;
        flex-wrap:wrap;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    -ms-flex-item-align:stretch;
        align-self:stretch;
    margin-top:5px;
    margin-right:7px;
    min-width:0; }
    .bp3-tag-input .bp3-tag-input-values > *{
      -webkit-box-flex:0;
          -ms-flex-positive:0;
              flex-grow:0;
      -ms-flex-negative:0;
          flex-shrink:0; }
    .bp3-tag-input .bp3-tag-input-values > .bp3-fill{
      -webkit-box-flex:1;
          -ms-flex-positive:1;
              flex-grow:1;
      -ms-flex-negative:1;
          flex-shrink:1; }
    .bp3-tag-input .bp3-tag-input-values::before,
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-right:5px; }
    .bp3-tag-input .bp3-tag-input-values:empty::before,
    .bp3-tag-input .bp3-tag-input-values > :last-child{
      margin-right:0; }
    .bp3-tag-input .bp3-tag-input-values:first-child .bp3-input-ghost:first-child{
      padding-left:5px; }
    .bp3-tag-input .bp3-tag-input-values > *{
      margin-bottom:5px; }
  .bp3-tag-input .bp3-tag{
    overflow-wrap:break-word; }
    .bp3-tag-input .bp3-tag.bp3-active{
      outline:rgba(19, 124, 189, 0.6) auto 2px;
      outline-offset:0;
      -moz-outline-radius:6px; }
  .bp3-tag-input .bp3-input-ghost{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:80px;
    line-height:20px; }
    .bp3-tag-input .bp3-input-ghost:disabled, .bp3-tag-input .bp3-input-ghost.bp3-disabled{
      cursor:not-allowed; }
  .bp3-tag-input .bp3-button,
  .bp3-tag-input .bp3-spinner{
    margin:3px;
    margin-left:0; }
  .bp3-tag-input .bp3-button{
    min-width:24px;
    min-height:24px;
    padding:0 7px; }
  .bp3-tag-input.bp3-large{
    height:auto;
    min-height:40px; }
    .bp3-tag-input.bp3-large::before,
    .bp3-tag-input.bp3-large > *{
      margin-right:10px; }
    .bp3-tag-input.bp3-large:empty::before,
    .bp3-tag-input.bp3-large > :last-child{
      margin-right:0; }
    .bp3-tag-input.bp3-large .bp3-tag-input-icon{
      margin-top:10px;
      margin-left:5px; }
    .bp3-tag-input.bp3-large .bp3-input-ghost{
      line-height:30px; }
    .bp3-tag-input.bp3-large .bp3-button{
      min-width:30px;
      min-height:30px;
      padding:5px 10px;
      margin:5px;
      margin-left:0; }
    .bp3-tag-input.bp3-large .bp3-spinner{
      margin:8px;
      margin-left:0; }
  .bp3-tag-input.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
    background-color:#ffffff; }
    .bp3-tag-input.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
    .bp3-tag-input.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-tag-input .bp3-tag-input-icon, .bp3-tag-input.bp3-dark .bp3-tag-input-icon{
    color:#a7b6c2; }
  .bp3-dark .bp3-tag-input .bp3-input-ghost, .bp3-tag-input.bp3-dark .bp3-input-ghost{
    color:#f5f8fa; }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-webkit-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-webkit-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-moz-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-moz-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost:-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost:-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::-ms-input-placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::-ms-input-placeholder{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-tag-input .bp3-input-ghost::placeholder, .bp3-tag-input.bp3-dark .bp3-input-ghost::placeholder{
      color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-tag-input.bp3-active, .bp3-tag-input.bp3-dark.bp3-active{
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
    background-color:rgba(16, 22, 26, 0.3); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-primary, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-primary{
      -webkit-box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #106ba3, 0 0 0 3px rgba(16, 107, 163, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-success, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-success{
      -webkit-box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #0d8050, 0 0 0 3px rgba(13, 128, 80, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-warning, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-warning{
      -webkit-box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #bf7326, 0 0 0 3px rgba(191, 115, 38, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-tag-input.bp3-active.bp3-intent-danger, .bp3-tag-input.bp3-dark.bp3-active.bp3-intent-danger{
      -webkit-box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px #c23030, 0 0 0 3px rgba(194, 48, 48, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }

.bp3-input-ghost{
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  background:none;
  padding:0; }
  .bp3-input-ghost::-webkit-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-moz-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::-ms-input-placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost::placeholder{
    opacity:1;
    color:rgba(92, 112, 128, 0.6); }
  .bp3-input-ghost:focus{
    outline:none !important; }
.bp3-toast{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  position:relative !important;
  margin:20px 0 0;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  min-width:300px;
  max-width:500px;
  pointer-events:all; }
  .bp3-toast.bp3-toast-enter, .bp3-toast.bp3-toast-appear{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active, .bp3-toast.bp3-toast-appear-active{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-enter ~ .bp3-toast, .bp3-toast.bp3-toast-appear ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active ~ .bp3-toast, .bp3-toast.bp3-toast-appear-active ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit{
    opacity:1;
    -webkit-filter:blur(0);
            filter:blur(0); }
  .bp3-toast.bp3-toast-exit-active{
    opacity:0;
    -webkit-filter:blur(10px);
            filter:blur(10px);
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:opacity, filter;
    transition-property:opacity, filter, -webkit-filter;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-toast.bp3-toast-exit ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0); }
  .bp3-toast.bp3-toast-exit-active ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:50ms;
            transition-delay:50ms; }
  .bp3-toast .bp3-button-group{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    padding:5px;
    padding-left:0; }
  .bp3-toast > .bp3-icon{
    margin:12px;
    margin-right:0;
    color:#5c7080; }
  .bp3-toast.bp3-dark,
  .bp3-dark .bp3-toast{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
    background-color:#394b59; }
    .bp3-toast.bp3-dark > .bp3-icon,
    .bp3-dark .bp3-toast > .bp3-icon{
      color:#a7b6c2; }
  .bp3-toast[class*="bp3-intent-"] a{
    color:rgba(255, 255, 255, 0.7); }
    .bp3-toast[class*="bp3-intent-"] a:hover{
      color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] > .bp3-icon{
    color:#ffffff; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button, .bp3-toast[class*="bp3-intent-"] .bp3-button::before,
  .bp3-toast[class*="bp3-intent-"] .bp3-button .bp3-icon, .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    color:rgba(255, 255, 255, 0.7) !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:focus{
    outline-color:rgba(255, 255, 255, 0.5); }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:hover{
    background-color:rgba(255, 255, 255, 0.15) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button:active{
    background-color:rgba(255, 255, 255, 0.3) !important;
    color:#ffffff !important; }
  .bp3-toast[class*="bp3-intent-"] .bp3-button::after{
    background:rgba(255, 255, 255, 0.3) !important; }
  .bp3-toast.bp3-intent-primary{
    background-color:#137cbd;
    color:#ffffff; }
  .bp3-toast.bp3-intent-success{
    background-color:#0f9960;
    color:#ffffff; }
  .bp3-toast.bp3-intent-warning{
    background-color:#d9822b;
    color:#ffffff; }
  .bp3-toast.bp3-intent-danger{
    background-color:#db3737;
    color:#ffffff; }

.bp3-toast-message{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  padding:11px;
  word-break:break-word; }

.bp3-toast-container{
  display:-webkit-box !important;
  display:-ms-flexbox !important;
  display:flex !important;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  position:fixed;
  right:0;
  left:0;
  z-index:40;
  overflow:hidden;
  padding:0 20px 20px;
  pointer-events:none; }
  .bp3-toast-container.bp3-toast-container-top{
    top:0;
    bottom:auto; }
  .bp3-toast-container.bp3-toast-container-bottom{
    -webkit-box-orient:vertical;
    -webkit-box-direction:reverse;
        -ms-flex-direction:column-reverse;
            flex-direction:column-reverse;
    top:auto;
    bottom:0; }
  .bp3-toast-container.bp3-toast-container-left{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start; }
  .bp3-toast-container.bp3-toast-container-right{
    -webkit-box-align:end;
        -ms-flex-align:end;
            align-items:flex-end; }

.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-enter:not(.bp3-toast-enter-active) ~ .bp3-toast, .bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active),
.bp3-toast-container-bottom .bp3-toast.bp3-toast-appear:not(.bp3-toast-appear-active) ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-leave-active ~ .bp3-toast{
  -webkit-transform:translateY(60px);
          transform:translateY(60px); }
.bp3-tooltip{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1); }
  .bp3-tooltip .bp3-popover-arrow{
    position:absolute;
    width:22px;
    height:22px; }
    .bp3-tooltip .bp3-popover-arrow::before{
      margin:4px;
      width:14px;
      height:14px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip{
    margin-top:-11px;
    margin-bottom:11px; }
    .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
      bottom:-8px; }
      .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(-90deg);
                transform:rotate(-90deg); }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip{
    margin-left:11px; }
    .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
      left:-8px; }
      .bp3-tether-element-attached-left.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(0);
                transform:rotate(0); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip{
    margin-top:11px; }
    .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
      top:-8px; }
      .bp3-tether-element-attached-top.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(90deg);
                transform:rotate(90deg); }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip{
    margin-right:11px;
    margin-left:-11px; }
    .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
      right:-8px; }
      .bp3-tether-element-attached-right.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow svg{
        -webkit-transform:rotate(180deg);
                transform:rotate(180deg); }
  .bp3-tether-element-attached-middle > .bp3-tooltip > .bp3-popover-arrow{
    top:50%;
    -webkit-transform:translateY(-50%);
            transform:translateY(-50%); }
  .bp3-tether-element-attached-center > .bp3-tooltip > .bp3-popover-arrow{
    right:50%;
    -webkit-transform:translateX(50%);
            transform:translateX(50%); }
  .bp3-tether-element-attached-top.bp3-tether-target-attached-top > .bp3-tooltip > .bp3-popover-arrow{
    top:-0.22183px; }
  .bp3-tether-element-attached-right.bp3-tether-target-attached-right > .bp3-tooltip > .bp3-popover-arrow{
    right:-0.22183px; }
  .bp3-tether-element-attached-left.bp3-tether-target-attached-left > .bp3-tooltip > .bp3-popover-arrow{
    left:-0.22183px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-bottom > .bp3-tooltip > .bp3-popover-arrow{
    bottom:-0.22183px; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:top left;
            transform-origin:top left; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:top center;
            transform-origin:top center; }
  .bp3-tether-element-attached-top.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:top right;
            transform-origin:top right; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:center left;
            transform-origin:center left; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:center center;
            transform-origin:center center; }
  .bp3-tether-element-attached-middle.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:center right;
            transform-origin:center right; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-left > .bp3-tooltip{
    -webkit-transform-origin:bottom left;
            transform-origin:bottom left; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-center > .bp3-tooltip{
    -webkit-transform-origin:bottom center;
            transform-origin:bottom center; }
  .bp3-tether-element-attached-bottom.bp3-tether-element-attached-right > .bp3-tooltip{
    -webkit-transform-origin:bottom right;
            transform-origin:bottom right; }
  .bp3-tooltip .bp3-popover-content{
    background:#394b59;
    color:#f5f8fa; }
  .bp3-tooltip .bp3-popover-arrow::before{
    -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2);
            box-shadow:1px 1px 6px rgba(16, 22, 26, 0.2); }
  .bp3-tooltip .bp3-popover-arrow-border{
    fill:#10161a;
    fill-opacity:0.1; }
  .bp3-tooltip .bp3-popover-arrow-fill{
    fill:#394b59; }
  .bp3-popover-enter > .bp3-tooltip, .bp3-popover-appear > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8); }
  .bp3-popover-enter-active > .bp3-tooltip, .bp3-popover-appear-active > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-popover-exit > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8);
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-tooltip .bp3-popover-content{
    padding:10px 12px; }
  .bp3-tooltip.bp3-dark,
  .bp3-dark .bp3-tooltip{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-content,
    .bp3-dark .bp3-tooltip .bp3-popover-content{
      background:#e1e8ed;
      color:#394b59; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow::before,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow::before{
      -webkit-box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4);
              box-shadow:1px 1px 6px rgba(16, 22, 26, 0.4); }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-border,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-border{
      fill:#10161a;
      fill-opacity:0.2; }
    .bp3-tooltip.bp3-dark .bp3-popover-arrow-fill,
    .bp3-dark .bp3-tooltip .bp3-popover-arrow-fill{
      fill:#e1e8ed; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-content{
    background:#137cbd;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-primary .bp3-popover-arrow-fill{
    fill:#137cbd; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-content{
    background:#0f9960;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-success .bp3-popover-arrow-fill{
    fill:#0f9960; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-content{
    background:#d9822b;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-warning .bp3-popover-arrow-fill{
    fill:#d9822b; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-content{
    background:#db3737;
    color:#ffffff; }
  .bp3-tooltip.bp3-intent-danger .bp3-popover-arrow-fill{
    fill:#db3737; }

.bp3-tooltip-indicator{
  border-bottom:dotted 1px;
  cursor:help; }
.bp3-tree .bp3-icon, .bp3-tree .bp3-icon-standard, .bp3-tree .bp3-icon-large{
  color:#5c7080; }
  .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-tree .bp3-icon.bp3-intent-success, .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-tree-node-list{
  margin:0;
  padding-left:0;
  list-style:none; }

.bp3-tree-root{
  position:relative;
  background-color:transparent;
  cursor:default;
  padding-left:0; }

.bp3-tree-node-content-0{
  padding-left:0px; }

.bp3-tree-node-content-1{
  padding-left:23px; }

.bp3-tree-node-content-2{
  padding-left:46px; }

.bp3-tree-node-content-3{
  padding-left:69px; }

.bp3-tree-node-content-4{
  padding-left:92px; }

.bp3-tree-node-content-5{
  padding-left:115px; }

.bp3-tree-node-content-6{
  padding-left:138px; }

.bp3-tree-node-content-7{
  padding-left:161px; }

.bp3-tree-node-content-8{
  padding-left:184px; }

.bp3-tree-node-content-9{
  padding-left:207px; }

.bp3-tree-node-content-10{
  padding-left:230px; }

.bp3-tree-node-content-11{
  padding-left:253px; }

.bp3-tree-node-content-12{
  padding-left:276px; }

.bp3-tree-node-content-13{
  padding-left:299px; }

.bp3-tree-node-content-14{
  padding-left:322px; }

.bp3-tree-node-content-15{
  padding-left:345px; }

.bp3-tree-node-content-16{
  padding-left:368px; }

.bp3-tree-node-content-17{
  padding-left:391px; }

.bp3-tree-node-content-18{
  padding-left:414px; }

.bp3-tree-node-content-19{
  padding-left:437px; }

.bp3-tree-node-content-20{
  padding-left:460px; }

.bp3-tree-node-content{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  width:100%;
  height:30px;
  padding-right:5px; }
  .bp3-tree-node-content:hover{
    background-color:rgba(191, 204, 214, 0.4); }

.bp3-tree-node-caret,
.bp3-tree-node-caret-none{
  min-width:30px; }

.bp3-tree-node-caret{
  color:#5c7080;
  -webkit-transform:rotate(0deg);
          transform:rotate(0deg);
  cursor:pointer;
  padding:7px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tree-node-caret:hover{
    color:#182026; }
  .bp3-dark .bp3-tree-node-caret{
    color:#a7b6c2; }
    .bp3-dark .bp3-tree-node-caret:hover{
      color:#f5f8fa; }
  .bp3-tree-node-caret.bp3-tree-node-caret-open{
    -webkit-transform:rotate(90deg);
            transform:rotate(90deg); }
  .bp3-tree-node-caret.bp3-icon-standard::before{
    content:""; }

.bp3-tree-node-icon{
  position:relative;
  margin-right:7px; }

.bp3-tree-node-label{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  position:relative;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-label span{
    display:inline; }

.bp3-tree-node-secondary-label{
  padding:0 5px;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-tree-node-secondary-label .bp3-popover-wrapper,
  .bp3-tree-node-secondary-label .bp3-popover-target{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-content{
  background-color:inherit;
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-disabled .bp3-tree-node-caret,
.bp3-tree-node.bp3-disabled .bp3-tree-node-icon{
  cursor:not-allowed;
  color:rgba(92, 112, 128, 0.6); }

.bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content,
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-standard, .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-icon-large{
    color:#ffffff; }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret::before{
    color:rgba(255, 255, 255, 0.7); }
  .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content .bp3-tree-node-caret:hover::before{
    color:#ffffff; }

.bp3-dark .bp3-tree-node-content:hover{
  background-color:rgba(92, 112, 128, 0.3); }

.bp3-dark .bp3-tree .bp3-icon, .bp3-dark .bp3-tree .bp3-icon-standard, .bp3-dark .bp3-tree .bp3-icon-large{
  color:#a7b6c2; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-primary, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-primary{
    color:#137cbd; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-success, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-success{
    color:#0f9960; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-warning, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-warning{
    color:#d9822b; }
  .bp3-dark .bp3-tree .bp3-icon.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-standard.bp3-intent-danger, .bp3-dark .bp3-tree .bp3-icon-large.bp3-intent-danger{
    color:#db3737; }

.bp3-dark .bp3-tree-node.bp3-tree-node-selected > .bp3-tree-node-content{
  background-color:#137cbd; }
/*!

Copyright 2017-present Palantir Technologies, Inc. All rights reserved.
Licensed under the Apache License, Version 2.0.

*/
.bp3-omnibar{
  -webkit-filter:blur(0);
          filter:blur(0);
  opacity:1;
  top:20vh;
  left:calc(50% - 250px);
  z-index:21;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  background-color:#ffffff;
  width:500px; }
  .bp3-omnibar.bp3-overlay-enter, .bp3-omnibar.bp3-overlay-appear{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2; }
  .bp3-omnibar.bp3-overlay-enter-active, .bp3-omnibar.bp3-overlay-appear-active{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar.bp3-overlay-exit{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1; }
  .bp3-omnibar.bp3-overlay-exit-active{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
    -webkit-transition-delay:0;
            transition-delay:0; }
  .bp3-omnibar .bp3-input{
    border-radius:0;
    background-color:transparent; }
    .bp3-omnibar .bp3-input, .bp3-omnibar .bp3-input:focus{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-omnibar .bp3-menu{
    border-radius:0;
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
    background-color:transparent;
    max-height:calc(60vh - 40px);
    overflow:auto; }
    .bp3-omnibar .bp3-menu:empty{
      display:none; }
  .bp3-dark .bp3-omnibar, .bp3-omnibar.bp3-dark{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    background-color:#30404d; }

.bp3-omnibar-overlay .bp3-overlay-backdrop{
  background-color:rgba(16, 22, 26, 0.2); }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }

.bp3-multi-select{
  min-width:150px; }

.bp3-multi-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto; }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-width:400px;
  max-height:300px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensureUiComponents() in @jupyterlab/buildutils */

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

/* Icons urls */

:root {
  --jp-icon-add: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDEzaC02djZoLTJ2LTZINXYtMmg2VjVoMnY2aDZ2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDhoLTIuODFjLS40NS0uNzgtMS4wNy0xLjQ1LTEuODItMS45NkwxNyA0LjQxIDE1LjU5IDNsLTIuMTcgMi4xN0MxMi45NiA1LjA2IDEyLjQ5IDUgMTIgNWMtLjQ5IDAtLjk2LjA2LTEuNDEuMTdMOC40MSAzIDcgNC40MWwxLjYyIDEuNjNDNy44OCA2LjU1IDcuMjYgNy4yMiA2LjgxIDhINHYyaDIuMDljLS4wNS4zMy0uMDkuNjYtLjA5IDF2MUg0djJoMnYxYzAgLjM0LjA0LjY3LjA5IDFINHYyaDIuODFjMS4wNCAxLjc5IDIuOTcgMyA1LjE5IDNzNC4xNS0xLjIxIDUuMTktM0gyMHYtMmgtMi4wOWMuMDUtLjMzLjA5LS42Ni4wOS0xdi0xaDJ2LTJoLTJ2LTFjMC0uMzQtLjA0LS42Ny0uMDktMUgyMFY4em0tNiA4aC00di0yaDR2MnptMC00aC00di0yaDR2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTYuMTdMNC44MyAxMmwtMS40MiAxLjQxTDkgMTkgMjEgN2wtMS40MS0xLjQxeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1pY29uLWJyYW5kMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNmZmYiPgogICAgPHBhdGggZD0iTTEwNSAxMjcuM2g0MHYxMi44aC00MHpNNTEuMSA3N0w3NCA5OS45bC0yMy4zIDIzLjMgMTAuNSAxMC41IDIzLjMtMjMuM0w5NSA5OS45IDg0LjUgODkuNCA2MS42IDY2LjV6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-cut: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkuNjQgNy42NGMuMjMtLjUuMzYtMS4wNS4zNi0xLjY0IDAtMi4yMS0xLjc5LTQtNC00UzIgMy43OSAyIDZzMS43OSA0IDQgNGMuNTkgMCAxLjE0LS4xMyAxLjY0LS4zNkwxMCAxMmwtMi4zNiAyLjM2QzcuMTQgMTQuMTMgNi41OSAxNCA2IDE0Yy0yLjIxIDAtNCAxLjc5LTQgNHMxLjc5IDQgNCA0IDQtMS43OSA0LTRjMC0uNTktLjEzLTEuMTQtLjM2LTEuNjRMMTIgMTRsNyA3aDN2LTFMOS42NCA3LjY0ek02IDhjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTAgMTJjLTEuMSAwLTItLjg5LTItMnMuOS0yIDItMiAyIC44OSAyIDItLjkgMi0yIDJ6bTYtNy41Yy0uMjggMC0uNS0uMjItLjUtLjVzLjIyLS41LjUtLjUuNS4yMi41LjUtLjIyLjUtLjUuNXpNMTkgM2wtNiA2IDIgMiA3LTdWM3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-download: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE5IDloLTRWM0g5djZINWw3IDcgNy03ek01IDE4djJoMTR2LTJINXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-edit: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMgMTcuMjVWMjFoMy43NUwxNy44MSA5Ljk0bC0zLjc1LTMuNzVMMyAxNy4yNXpNMjAuNzEgNy4wNGMuMzktLjM5LjM5LTEuMDIgMC0xLjQxbC0yLjM0LTIuMzRjLS4zOS0uMzktMS4wMi0uMzktMS40MSAwbC0xLjgzIDEuODMgMy43NSAzLjc1IDEuODMtMS44M3oiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-ellipses: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iNSIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIyIi8+CiAgICA8Y2lyY2xlIGN4PSIxOSIgY3k9IjEyIiByPSIyIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-extension: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwLjUgMTFIMTlWN2MwLTEuMS0uOS0yLTItMmgtNFYzLjVDMTMgMi4xMiAxMS44OCAxIDEwLjUgMVM4IDIuMTIgOCAzLjVWNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAydjMuOEgzLjVjMS40OSAwIDIuNyAxLjIxIDIuNyAyLjdzLTEuMjEgMi43LTIuNyAyLjdIMlYyMGMwIDEuMS45IDIgMiAyaDMuOHYtMS41YzAtMS40OSAxLjIxLTIuNyAyLjctMi43IDEuNDkgMCAyLjcgMS4yMSAyLjcgMi43VjIySDE3YzEuMSAwIDItLjkgMi0ydi00aDEuNWMxLjM4IDAgMi41LTEuMTIgMi41LTIuNVMyMS44OCAxMSAyMC41IDExeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-fast-forward: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTQgMThsOC41LTZMNCA2djEyem05LTEydjEybDguNS02TDEzIDZ6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-file-upload: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTkgMTZoNnYtNmg0bC03LTctNyA3aDR6bS00IDJoMTR2Mkg1eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-file: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuMyA4LjJsLTUuNS01LjVjLS4zLS4zLS43LS41LTEuMi0uNUgzLjljLS44LjEtMS42LjktMS42IDEuOHYxNC4xYzAgLjkuNyAxLjYgMS42IDEuNmgxNC4yYy45IDAgMS42LS43IDEuNi0xLjZWOS40Yy4xLS41LS4xLS45LS40LTEuMnptLTUuOC0zLjNsMy40IDMuNmgtMy40VjQuOXptMy45IDEyLjdINC43Yy0uMSAwLS4yIDAtLjItLjJWNC43YzAtLjIuMS0uMy4yLS4zaDcuMnY0LjRzMCAuOC4zIDEuMWMuMy4zIDEuMS4zIDEuMS4zaDQuM3Y3LjJzLS4xLjItLjIuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-filter-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEwIDE4aDR2LTJoLTR2MnpNMyA2djJoMThWNkgzem0zIDdoMTJ2LTJINnYyeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY4YzAtMS4xLS45LTItMi0yaC04bC0yLTJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-html5: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMDAiIGQ9Ik0xMDguNCAwaDIzdjIyLjhoMjEuMlYwaDIzdjY5aC0yM1Y0NmgtMjF2MjNoLTIzLjJNMjA2IDIzaC0yMC4zVjBoNjMuN3YyM0gyMjl2NDZoLTIzbTUzLjUtNjloMjQuMWwxNC44IDI0LjNMMzEzLjIgMGgyNC4xdjY5aC0yM1YzNC44bC0xNi4xIDI0LjgtMTYuMS0yNC44VjY5aC0yMi42bTg5LjItNjloMjN2NDYuMmgzMi42VjY5aC01NS42Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI2U0NGQyNiIgZD0iTTEwNy42IDQ3MWwtMzMtMzcwLjRoMzYyLjhsLTMzIDM3MC4yTDI1NS43IDUxMiIvPgogIDxwYXRoIGNsYXNzPSJqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNmMTY1MjkiIGQ9Ik0yNTYgNDgwLjVWMTMxaDE0OC4zTDM3NiA0NDciLz4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNlYmViZWIiIGQ9Ik0xNDIgMTc2LjNoMTE0djQ1LjRoLTY0LjJsNC4yIDQ2LjVoNjB2NDUuM0gxNTQuNG0yIDIyLjhIMjAybDMuMiAzNi4zIDUwLjggMTMuNnY0Ny40bC05My4yLTI2Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIiBmaWxsPSIjZmZmIiBkPSJNMzY5LjYgMTc2LjNIMjU1Ljh2NDUuNGgxMDkuNm0tNC4xIDQ2LjVIMjU1Ljh2NDUuNGg1NmwtNS4zIDU5LTUwLjcgMTMuNnY0Ny4ybDkzLTI1LjgiLz4KPC9zdmc+Cg==);
  --jp-icon-image: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1icmFuZDQganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNGRkYiIGQ9Ik0yLjIgMi4yaDE3LjV2MTcuNUgyLjJ6Ii8+CiAgPHBhdGggY2xhc3M9ImpwLWljb24tYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzNGNTFCNSIgZD0iTTIuMiAyLjJ2MTcuNWgxNy41bC4xLTE3LjVIMi4yem0xMi4xIDIuMmMxLjIgMCAyLjIgMSAyLjIgMi4ycy0xIDIuMi0yLjIgMi4yLTIuMi0xLTIuMi0yLjIgMS0yLjIgMi4yLTIuMnpNNC40IDE3LjZsMy4zLTguOCAzLjMgNi42IDIuMi0zLjIgNC40IDUuNEg0LjR6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-inspector: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNEg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMThjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY2YzAtMS4xLS45LTItMi0yem0tNSAxNEg0di00aDExdjR6bTAtNUg0VjloMTF2NHptNSA1aC00VjloNHY5eiIvPgo8L3N2Zz4K);
  --jp-icon-json: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNGOUE4MjUiPgogICAgPHBhdGggZD0iTTIwLjIgMTEuOGMtMS42IDAtMS43LjUtMS43IDEgMCAuNC4xLjkuMSAxLjMuMS41LjEuOS4xIDEuMyAwIDEuNy0xLjQgMi4zLTMuNSAyLjNoLS45di0xLjloLjVjMS4xIDAgMS40IDAgMS40LS44IDAtLjMgMC0uNi0uMS0xIDAtLjQtLjEtLjgtLjEtMS4yIDAtMS4zIDAtMS44IDEuMy0yLTEuMy0uMi0xLjMtLjctMS4zLTIgMC0uNC4xLS44LjEtMS4yLjEtLjQuMS0uNy4xLTEgMC0uOC0uNC0uNy0xLjQtLjhoLS41VjQuMWguOWMyLjIgMCAzLjUuNyAzLjUgMi4zIDAgLjQtLjEuOS0uMSAxLjMtLjEuNS0uMS45LS4xIDEuMyAwIC41LjIgMSAxLjcgMXYxLjh6TTEuOCAxMC4xYzEuNiAwIDEuNy0uNSAxLjctMSAwLS40LS4xLS45LS4xLTEuMy0uMS0uNS0uMS0uOS0uMS0xLjMgMC0xLjYgMS40LTIuMyAzLjUtMi4zaC45djEuOWgtLjVjLTEgMC0xLjQgMC0xLjQuOCAwIC4zIDAgLjYuMSAxIDAgLjIuMS42LjEgMSAwIDEuMyAwIDEuOC0xLjMgMkM2IDExLjIgNiAxMS43IDYgMTNjMCAuNC0uMS44LS4xIDEuMi0uMS4zLS4xLjctLjEgMSAwIC44LjMuOCAxLjQuOGguNXYxLjloLS45Yy0yLjEgMC0zLjUtLjYtMy41LTIuMyAwLS40LjEtLjkuMS0xLjMuMS0uNS4xLS45LjEtMS4zIDAtLjUtLjItMS0xLjctMXYtMS45eiIvPgogICAgPGNpcmNsZSBjeD0iMTEiIGN5PSIxMy44IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY3g9IjExIiBjeT0iOC4yIiByPSIyLjEiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgPGcgY2xhc3M9ImpwLWljb24td2FybjAiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4=);
  --jp-icon-listings-info: url(data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iaXNvLTg4NTktMSI/Pg0KPHN2ZyB2ZXJzaW9uPSIxLjEiIGlkPSJDYXBhXzEiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiIHg9IjBweCIgeT0iMHB4Ig0KCSB2aWV3Qm94PSIwIDAgNTAuOTc4IDUwLjk3OCIgc3R5bGU9ImVuYWJsZS1iYWNrZ3JvdW5kOm5ldyAwIDAgNTAuOTc4IDUwLjk3ODsiIHhtbDpzcGFjZT0icHJlc2VydmUiPg0KPGc+DQoJPGc+DQoJCTxnPg0KCQkJPHBhdGggc3R5bGU9ImZpbGw6IzAxMDAwMjsiIGQ9Ik00My41Miw3LjQ1OEMzOC43MTEsMi42NDgsMzIuMzA3LDAsMjUuNDg5LDBDMTguNjcsMCwxMi4yNjYsMi42NDgsNy40NTgsNy40NTgNCgkJCQljLTkuOTQzLDkuOTQxLTkuOTQzLDI2LjExOSwwLDM2LjA2MmM0LjgwOSw0LjgwOSwxMS4yMTIsNy40NTYsMTguMDMxLDcuNDU4YzAsMCwwLjAwMSwwLDAuMDAyLDANCgkJCQljNi44MTYsMCwxMy4yMjEtMi42NDgsMTguMDI5LTcuNDU4YzQuODA5LTQuODA5LDcuNDU3LTExLjIxMiw3LjQ1Ny0xOC4wM0M1MC45NzcsMTguNjcsNDguMzI4LDEyLjI2Niw0My41Miw3LjQ1OHoNCgkJCQkgTTQyLjEwNiw0Mi4xMDVjLTQuNDMyLDQuNDMxLTEwLjMzMiw2Ljg3Mi0xNi42MTUsNi44NzJoLTAuMDAyYy02LjI4NS0wLjAwMS0xMi4xODctMi40NDEtMTYuNjE3LTYuODcyDQoJCQkJYy05LjE2Mi05LjE2My05LjE2Mi0yNC4wNzEsMC0zMy4yMzNDMTMuMzAzLDQuNDQsMTkuMjA0LDIsMjUuNDg5LDJjNi4yODQsMCwxMi4xODYsMi40NCwxNi42MTcsNi44NzINCgkJCQljNC40MzEsNC40MzEsNi44NzEsMTAuMzMyLDYuODcxLDE2LjYxN0M0OC45NzcsMzEuNzcyLDQ2LjUzNiwzNy42NzUsNDIuMTA2LDQyLjEwNXoiLz4NCgkJPC9nPg0KCQk8Zz4NCgkJCTxwYXRoIHN0eWxlPSJmaWxsOiMwMTAwMDI7IiBkPSJNMjMuNTc4LDMyLjIxOGMtMC4wMjMtMS43MzQsMC4xNDMtMy4wNTksMC40OTYtMy45NzJjMC4zNTMtMC45MTMsMS4xMS0xLjk5NywyLjI3Mi0zLjI1Mw0KCQkJCWMwLjQ2OC0wLjUzNiwwLjkyMy0xLjA2MiwxLjM2Ny0xLjU3NWMwLjYyNi0wLjc1MywxLjEwNC0xLjQ3OCwxLjQzNi0yLjE3NWMwLjMzMS0wLjcwNywwLjQ5NS0xLjU0MSwwLjQ5NS0yLjUNCgkJCQljMC0xLjA5Ni0wLjI2LTIuMDg4LTAuNzc5LTIuOTc5Yy0wLjU2NS0wLjg3OS0xLjUwMS0xLjMzNi0yLjgwNi0xLjM2OWMtMS44MDIsMC4wNTctMi45ODUsMC42NjctMy41NSwxLjgzMg0KCQkJCWMtMC4zMDEsMC41MzUtMC41MDMsMS4xNDEtMC42MDcsMS44MTRjLTAuMTM5LDAuNzA3LTAuMjA3LDEuNDMyLTAuMjA3LDIuMTc0aC0yLjkzN2MtMC4wOTEtMi4yMDgsMC40MDctNC4xMTQsMS40OTMtNS43MTkNCgkJCQljMS4wNjItMS42NCwyLjg1NS0yLjQ4MSw1LjM3OC0yLjUyN2MyLjE2LDAuMDIzLDMuODc0LDAuNjA4LDUuMTQxLDEuNzU4YzEuMjc4LDEuMTYsMS45MjksMi43NjQsMS45NSw0LjgxMQ0KCQkJCWMwLDEuMTQyLTAuMTM3LDIuMTExLTAuNDEsMi45MTFjLTAuMzA5LDAuODQ1LTAuNzMxLDEuNTkzLTEuMjY4LDIuMjQzYy0wLjQ5MiwwLjY1LTEuMDY4LDEuMzE4LTEuNzMsMi4wMDINCgkJCQljLTAuNjUsMC42OTctMS4zMTMsMS40NzktMS45ODcsMi4zNDZjLTAuMjM5LDAuMzc3LTAuNDI5LDAuNzc3LTAuNTY1LDEuMTk5Yy0wLjE2LDAuOTU5LTAuMjE3LDEuOTUxLTAuMTcxLDIuOTc5DQoJCQkJQzI2LjU4OSwzMi4yMTgsMjMuNTc4LDMyLjIxOCwyMy41NzgsMzIuMjE4eiBNMjMuNTc4LDM4LjIydi0zLjQ4NGgzLjA3NnYzLjQ4NEgyMy41Nzh6Ii8+DQoJCTwvZz4NCgk8L2c+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8Zz4NCjwvZz4NCjxnPg0KPC9nPg0KPGc+DQo8L2c+DQo8L3N2Zz4NCg==);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMEQ0N0ExIj4KICAgIDxwYXRoIGQ9Ik0xMS4xIDYuOVY1LjhINi45YzAtLjUgMC0xLjMuMi0xLjYuNC0uNy44LTEuMSAxLjctMS40IDEuNy0uMyAyLjUtLjMgMy45LS4xIDEgLjEgMS45LjkgMS45IDEuOXY0LjJjMCAuNS0uOSAxLjYtMiAxLjZIOC44Yy0xLjUgMC0yLjQgMS40LTIuNCAyLjh2Mi4ySDQuN0MzLjUgMTUuMSAzIDE0IDMgMTMuMVY5Yy0uMS0xIC42LTIgMS44LTIgMS41LS4xIDYuMy0uMSA2LjMtLjF6Ii8+CiAgICA8cGF0aCBkPSJNMTAuOSAxNS4xdjEuMWg0LjJjMCAuNSAwIDEuMy0uMiAxLjYtLjQuNy0uOCAxLjEtMS43IDEuNC0xLjcuMy0yLjUuMy0zLjkuMS0xLS4xLTEuOS0uOS0xLjktMS45di00LjJjMC0uNS45LTEuNiAyLTEuNmgzLjhjMS41IDAgMi40LTEuNCAyLjQtMi44VjYuNmgxLjdDMTguNSA2LjkgMTkgOCAxOSA4LjlWMTNjMCAxLS43IDIuMS0xLjkgMi4xaC02LjJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-refresh: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTkgMTMuNWMtMi40OSAwLTQuNS0yLjAxLTQuNS00LjVTNi41MSA0LjUgOSA0LjVjMS4yNCAwIDIuMzYuNTIgMy4xNyAxLjMzTDEwIDhoNVYzbC0xLjc2IDEuNzZDMTIuMTUgMy42OCAxMC42NiAzIDkgMyA1LjY5IDMgMy4wMSA1LjY5IDMuMDEgOVM1LjY5IDE1IDkgMTVjMi45NyAwIDUuNDMtMi4xNiA1LjktNWgtMS41MmMtLjQ2IDItMi4yNCAzLjUtNC4zOCAzLjV6Ii8+CiAgICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-regex: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi1hY2NlbnQyIiBmaWxsPSIjRkZGIj4KICAgIDxjaXJjbGUgY2xhc3M9InN0MiIgY3g9IjUuNSIgY3k9IjE0LjUiIHI9IjEuNSIvPgogICAgPHJlY3QgeD0iMTIiIHk9IjQiIGNsYXNzPSJzdDIiIHdpZHRoPSIxIiBoZWlnaHQ9IjgiLz4KICAgIDxyZWN0IHg9IjguNSIgeT0iNy41IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjg2NiAtMC41IDAuNSAwLjg2NiAtMi4zMjU1IDcuMzIxOSkiIGNsYXNzPSJzdDIiIHdpZHRoPSI4IiBoZWlnaHQ9IjEiLz4KICAgIDxyZWN0IHg9IjEyIiB5PSI0IiB0cmFuc2Zvcm09Im1hdHJpeCgwLjUgLTAuODY2IDAuODY2IDAuNSAtMC42Nzc5IDE0LjgyNTIpIiBjbGFzcz0ic3QyIiB3aWR0aD0iMSIgaGVpZ2h0PSI4Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-run: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTggNXYxNGwxMS03eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-running: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDUxMiA1MTIiPgogIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMjU2IDhDMTE5IDggOCAxMTkgOCAyNTZzMTExIDI0OCAyNDggMjQ4IDI0OC0xMTEgMjQ4LTI0OFMzOTMgOCAyNTYgOHptOTYgMzI4YzAgOC44LTcuMiAxNi0xNiAxNkgxNzZjLTguOCAwLTE2LTcuMi0xNi0xNlYxNzZjMC04LjggNy4yLTE2IDE2LTE2aDE2MGM4LjggMCAxNiA3LjIgMTYgMTZ2MTYweiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-save: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE3IDNINWMtMS4xMSAwLTIgLjktMiAydjE0YzAgMS4xLjg5IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjdsLTQtNHptLTUgMTZjLTEuNjYgMC0zLTEuMzQtMy0zczEuMzQtMyAzLTMgMyAxLjM0IDMgMy0xLjM0IDMtMyAzem0zLTEwSDVWNWgxMHY0eiIvPgogICAgPC9nPgo8L3N2Zz4K);
  --jp-icon-search: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-settings: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkuNDMgMTIuOThjLjA0LS4zMi4wNy0uNjQuMDctLjk4cy0uMDMtLjY2LS4wNy0uOThsMi4xMS0xLjY1Yy4xOS0uMTUuMjQtLjQyLjEyLS42NGwtMi0zLjQ2Yy0uMTItLjIyLS4zOS0uMy0uNjEtLjIybC0yLjQ5IDFjLS41Mi0uNC0xLjA4LS43My0xLjY5LS45OGwtLjM4LTIuNjVBLjQ4OC40ODggMCAwMDE0IDJoLTRjLS4yNSAwLS40Ni4xOC0uNDkuNDJsLS4zOCAyLjY1Yy0uNjEuMjUtMS4xNy41OS0xLjY5Ljk4bC0yLjQ5LTFjLS4yMy0uMDktLjQ5IDAtLjYxLjIybC0yIDMuNDZjLS4xMy4yMi0uMDcuNDkuMTIuNjRsMi4xMSAxLjY1Yy0uMDQuMzItLjA3LjY1LS4wNy45OHMuMDMuNjYuMDcuOThsLTIuMTEgMS42NWMtLjE5LjE1LS4yNC40Mi0uMTIuNjRsMiAzLjQ2Yy4xMi4yMi4zOS4zLjYxLjIybDIuNDktMWMuNTIuNCAxLjA4LjczIDEuNjkuOThsLjM4IDIuNjVjLjAzLjI0LjI0LjQyLjQ5LjQyaDRjLjI1IDAgLjQ2LS4xOC40OS0uNDJsLjM4LTIuNjVjLjYxLS4yNSAxLjE3LS41OSAxLjY5LS45OGwyLjQ5IDFjLjIzLjA5LjQ5IDAgLjYxLS4yMmwyLTMuNDZjLjEyLS4yMi4wNy0uNDktLjEyLS42NGwtMi4xMS0xLjY1ek0xMiAxNS41Yy0xLjkzIDAtMy41LTEuNTctMy41LTMuNXMxLjU3LTMuNSAzLjUtMy41IDMuNSAxLjU3IDMuNSAzLjUtMS41NyAzLjUtMy41IDMuNXoiLz4KPC9zdmc+Cg==);
  --jp-icon-spreadsheet: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNENBRjUwIiBkPSJNMi4yIDIuMnYxNy42aDE3LjZWMi4ySDIuMnptMTUuNCA3LjdoLTUuNVY0LjRoNS41djUuNXpNOS45IDQuNHY1LjVINC40VjQuNGg1LjV6bS01LjUgNy43aDUuNXY1LjVINC40di01LjV6bTcuNyA1LjV2LTUuNWg1LjV2NS41aC01LjV6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-stop: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik02IDZoMTJ2MTJINnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tab: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIxIDNIM2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxOGMxLjEgMCAyLS45IDItMlY1YzAtMS4xLS45LTItMi0yem0wIDE2SDNWNWgxMHY0aDh2MTB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMikiIGZpbGw9IiMzMzMzMzMiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uLWFjY2VudDIganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGQ9Ik01LjA1NjY0IDguNzYxNzJDNS4wNTY2NCA4LjU5NzY2IDUuMDMxMjUgOC40NTMxMiA0Ljk4MDQ3IDguMzI4MTJDNC45MzM1OSA4LjE5OTIyIDQuODU1NDcgOC4wODIwMyA0Ljc0NjA5IDcuOTc2NTZDNC42NDA2MiA3Ljg3MTA5IDQuNSA3Ljc3NTM5IDQuMzI0MjIgNy42ODk0NUM0LjE1MjM0IDcuNTk5NjEgMy45NDMzNiA3LjUxMTcyIDMuNjk3MjcgNy40MjU3OEMzLjMwMjczIDcuMjg1MTYgMi45NDMzNiA3LjEzNjcyIDIuNjE5MTQgNi45ODA0N0MyLjI5NDkyIDYuODI0MjIgMi4wMTc1OCA2LjY0MjU4IDEuNzg3MTEgNi40MzU1NUMxLjU2MDU1IDYuMjI4NTIgMS4zODQ3NyA1Ljk4ODI4IDEuMjU5NzcgNS43MTQ4NEMxLjEzNDc3IDUuNDM3NSAxLjA3MjI3IDUuMTA5MzggMS4wNzIyNyA0LjczMDQ3QzEuMDcyMjcgNC4zOTg0NCAxLjEyODkxIDQuMDk1NyAxLjI0MjE5IDMuODIyMjdDMS4zNTU0NyAzLjU0NDkyIDEuNTE1NjIgMy4zMDQ2OSAxLjcyMjY2IDMuMTAxNTZDMS45Mjk2OSAyLjg5ODQ0IDIuMTc5NjkgMi43MzQzNyAyLjQ3MjY2IDIuNjA5MzhDMi43NjU2MiAyLjQ4NDM4IDMuMDkxOCAyLjQwNDMgMy40NTExNyAyLjM2OTE0VjEuMTA5MzhINC4zODg2N1YyLjM4MDg2QzQuNzQwMjMgMi40Mjc3MyA1LjA1NjY0IDIuNTIzNDQgNS4zMzc4OSAyLjY2Nzk3QzUuNjE5MTQgMi44MTI1IDUuODU3NDIgMy4wMDE5NSA2LjA1MjczIDMuMjM2MzNDNi4yNTE5NSAzLjQ2NjggNi40MDQzIDMuNzQwMjMgNi41MDk3NyA0LjA1NjY0QzYuNjE5MTQgNC4zNjkxNCA2LjY3MzgzIDQuNzIwNyA2LjY3MzgzIDUuMTExMzNINS4wNDQ5MkM1LjA0NDkyIDQuNjM4NjcgNC45Mzc1IDQuMjgxMjUgNC43MjI2NiA0LjAzOTA2QzQuNTA3ODEgMy43OTI5NyA0LjIxNjggMy42Njk5MiAzLjg0OTYxIDMuNjY5OTJDMy42NTAzOSAzLjY2OTkyIDMuNDc2NTYgMy42OTcyNyAzLjMyODEyIDMuNzUxOTVDMy4xODM1OSAzLjgwMjczIDMuMDY0NDUgMy44NzY5NSAyLjk3MDcgMy45NzQ2MUMyLjg3Njk1IDQuMDY4MzYgMi44MDY2NCA0LjE3OTY5IDIuNzU5NzcgNC4zMDg1OUMyLjcxNjggNC40Mzc1IDIuNjk1MzEgNC41NzgxMiAyLjY5NTMxIDQuNzMwNDdDMi42OTUzMSA0Ljg4MjgxIDIuNzE2OCA1LjAxOTUzIDIuNzU5NzcgNS4xNDA2MkMyLjgwNjY0IDUuMjU3ODEgMi44ODI4MSA1LjM2NzE5IDIuOTg4MjggNS40Njg3NUMzLjA5NzY2IDUuNTcwMzEgMy4yNDAyMyA1LjY2Nzk3IDMuNDE2MDIgNS43NjE3MkMzLjU5MTggNS44NTE1NiAzLjgxMDU1IDUuOTQzMzYgNC4wNzIyNyA2LjAzNzExQzQuNDY2OCA2LjE4NTU1IDQuODI0MjIgNi4zMzk4NCA1LjE0NDUzIDYuNUM1LjQ2NDg0IDYuNjU2MjUgNS43MzgyOCA2LjgzOTg0IDUuOTY0ODQgNy4wNTA3OEM2LjE5NTMxIDcuMjU3ODEgNi4zNzEwOSA3LjUgNi40OTIxOSA3Ljc3NzM0QzYuNjE3MTkgOC4wNTA3OCA2LjY3OTY5IDguMzc1IDYuNjc5NjkgOC43NUM2LjY3OTY5IDkuMDkzNzUgNi42MjMwNSA5LjQwNDMgNi41MDk3NyA5LjY4MTY0QzYuMzk2NDggOS45NTUwOCA2LjIzNDM4IDEwLjE5MTQgNi4wMjM0NCAxMC4zOTA2QzUuODEyNSAxMC41ODk4IDUuNTU4NTkgMTAuNzUgNS4yNjE3MiAxMC44NzExQzQuOTY0ODQgMTAuOTg4MyA0LjYzMjgxIDExLjA2NDUgNC4yNjU2MiAxMS4wOTk2VjEyLjI0OEgzLjMzMzk4VjExLjA5OTZDMy4wMDE5NSAxMS4wNjg0IDIuNjc5NjkgMTAuOTk2MSAyLjM2NzE5IDEwLjg4MjhDMi4wNTQ2OSAxMC43NjU2IDEuNzc3MzQgMTAuNTk3NyAxLjUzNTE2IDEwLjM3ODlDMS4yOTY4OCAxMC4xNjAyIDEuMTA1NDcgOS44ODQ3NyAwLjk2MDkzOCA5LjU1MjczQzAuODE2NDA2IDkuMjE2OCAwLjc0NDE0MSA4LjgxNDQ1IDAuNzQ0MTQxIDguMzQ1N0gyLjM3ODkxQzIuMzc4OTEgOC42MjY5NSAyLjQxOTkyIDguODYzMjggMi41MDE5NSA5LjA1NDY5QzIuNTgzOTggOS4yNDIxOSAyLjY4OTQ1IDkuMzkyNTggMi44MTgzNiA5LjUwNTg2QzIuOTUxMTcgOS42MTUyMyAzLjEwMTU2IDkuNjkzMzYgMy4yNjk1MyA5Ljc0MDIzQzMuNDM3NSA5Ljc4NzExIDMuNjA5MzggOS44MTA1NSAzLjc4NTE2IDkuODEwNTVDNC4yMDMxMiA5LjgxMDU1IDQuNTE5NTMgOS43MTI4OSA0LjczNDM4IDkuNTE3NThDNC45NDkyMiA5LjMyMjI3IDUuMDU2NjQgOS4wNzAzMSA1LjA1NjY0IDguNzYxNzJaTTEzLjQxOCAxMi4yNzE1SDguMDc0MjJWMTFIMTMuNDE4VjEyLjI3MTVaIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzLjk1MjY0IDYpIiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTUgMTVIM3YyaDEydi0yem0wLThIM3YyaDEyVjd6TTMgMTNoMTh2LTJIM3Yyem0wIDhoMTh2LTJIM3Yyek0zIDN2MmgxOFYzSDN6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMiAxNy4xODQ0IDIuOTY5NjggMTQuMzAzMiAxLjg2MDk0IDExLjQ0MDlaIi8+CiAgICA8cGF0aCBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiMzMzMzMzMiIHN0cm9rZT0iIzMzMzMzMyIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOCA5Ljg2NzE5KSIgZD0iTTIuODYwMTUgNC44NjUzNUwwLjcyNjU0OSAyLjk5OTU5TDAgMy42MzA0NUwyLjg2MDE1IDYuMTMxNTdMOCAwLjYzMDg3Mkw3LjI3ODU3IDBMMi44NjAxNSA0Ljg2NTM1WiIvPgo8L3N2Zz4K);
  --jp-icon-undo: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjUgOGMtMi42NSAwLTUuMDUuOTktNi45IDIuNkwyIDd2OWg5bC0zLjYyLTMuNjJjMS4zOS0xLjE2IDMuMTYtMS44OCA1LjEyLTEuODggMy41NCAwIDYuNTUgMi4zMSA3LjYgNS41bDIuMzctLjc4QzIxLjA4IDExLjAzIDE3LjE1IDggMTIuNSA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-vega: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbjEganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjEyMTIxIj4KICAgIDxwYXRoIGQ9Ik0xMC42IDUuNGwyLjItMy4ySDIuMnY3LjNsNC02LjZ6Ii8+CiAgICA8cGF0aCBkPSJNMTUuOCAyLjJsLTQuNCA2LjZMNyA2LjNsLTQuOCA4djUuNWgxNy42VjIuMmgtNHptLTcgMTUuNEg1LjV2LTQuNGgzLjN2NC40em00LjQgMEg5LjhWOS44aDMuNHY3Ljh6bTQuNCAwaC0zLjRWNi41aDMuNHYxMS4xeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-yaml: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1jb250cmFzdDIganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjRDgxQjYwIj4KICAgIDxwYXRoIGQ9Ik03LjIgMTguNnYtNS40TDMgNS42aDMuM2wxLjQgMy4xYy4zLjkuNiAxLjYgMSAyLjUuMy0uOC42LTEuNiAxLTIuNWwxLjQtMy4xaDMuNGwtNC40IDcuNnY1LjVsLTIuOS0uMXoiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxNi41IiByPSIyLjEiLz4KICAgIDxjaXJjbGUgY2xhc3M9InN0MCIgY3g9IjE3LjYiIGN5PSIxMSIgcj0iMi4xIi8+CiAgPC9nPgo8L3N2Zz4K);
}

/* Icon CSS class declarations */

.jp-AddIcon {
  background-image: var(--jp-icon-add);
}
.jp-BugIcon {
  background-image: var(--jp-icon-bug);
}
.jp-BuildIcon {
  background-image: var(--jp-icon-build);
}
.jp-CaretDownEmptyIcon {
  background-image: var(--jp-icon-caret-down-empty);
}
.jp-CaretDownEmptyThinIcon {
  background-image: var(--jp-icon-caret-down-empty-thin);
}
.jp-CaretDownIcon {
  background-image: var(--jp-icon-caret-down);
}
.jp-CaretLeftIcon {
  background-image: var(--jp-icon-caret-left);
}
.jp-CaretRightIcon {
  background-image: var(--jp-icon-caret-right);
}
.jp-CaretUpEmptyThinIcon {
  background-image: var(--jp-icon-caret-up-empty-thin);
}
.jp-CaretUpIcon {
  background-image: var(--jp-icon-caret-up);
}
.jp-CaseSensitiveIcon {
  background-image: var(--jp-icon-case-sensitive);
}
.jp-CheckIcon {
  background-image: var(--jp-icon-check);
}
.jp-CircleEmptyIcon {
  background-image: var(--jp-icon-circle-empty);
}
.jp-CircleIcon {
  background-image: var(--jp-icon-circle);
}
.jp-ClearIcon {
  background-image: var(--jp-icon-clear);
}
.jp-CloseIcon {
  background-image: var(--jp-icon-close);
}
.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}
.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}
.jp-CutIcon {
  background-image: var(--jp-icon-cut);
}
.jp-DownloadIcon {
  background-image: var(--jp-icon-download);
}
.jp-EditIcon {
  background-image: var(--jp-icon-edit);
}
.jp-EllipsesIcon {
  background-image: var(--jp-icon-ellipses);
}
.jp-ExtensionIcon {
  background-image: var(--jp-icon-extension);
}
.jp-FastForwardIcon {
  background-image: var(--jp-icon-fast-forward);
}
.jp-FileIcon {
  background-image: var(--jp-icon-file);
}
.jp-FileUploadIcon {
  background-image: var(--jp-icon-file-upload);
}
.jp-FilterListIcon {
  background-image: var(--jp-icon-filter-list);
}
.jp-FolderIcon {
  background-image: var(--jp-icon-folder);
}
.jp-Html5Icon {
  background-image: var(--jp-icon-html5);
}
.jp-ImageIcon {
  background-image: var(--jp-icon-image);
}
.jp-InspectorIcon {
  background-image: var(--jp-icon-inspector);
}
.jp-JsonIcon {
  background-image: var(--jp-icon-json);
}
.jp-JupyterFaviconIcon {
  background-image: var(--jp-icon-jupyter-favicon);
}
.jp-JupyterIcon {
  background-image: var(--jp-icon-jupyter);
}
.jp-JupyterlabWordmarkIcon {
  background-image: var(--jp-icon-jupyterlab-wordmark);
}
.jp-KernelIcon {
  background-image: var(--jp-icon-kernel);
}
.jp-KeyboardIcon {
  background-image: var(--jp-icon-keyboard);
}
.jp-LauncherIcon {
  background-image: var(--jp-icon-launcher);
}
.jp-LineFormIcon {
  background-image: var(--jp-icon-line-form);
}
.jp-LinkIcon {
  background-image: var(--jp-icon-link);
}
.jp-ListIcon {
  background-image: var(--jp-icon-list);
}
.jp-ListingsInfoIcon {
  background-image: var(--jp-icon-listings-info);
}
.jp-MarkdownIcon {
  background-image: var(--jp-icon-markdown);
}
.jp-NewFolderIcon {
  background-image: var(--jp-icon-new-folder);
}
.jp-NotTrustedIcon {
  background-image: var(--jp-icon-not-trusted);
}
.jp-NotebookIcon {
  background-image: var(--jp-icon-notebook);
}
.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}
.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}
.jp-PythonIcon {
  background-image: var(--jp-icon-python);
}
.jp-RKernelIcon {
  background-image: var(--jp-icon-r-kernel);
}
.jp-ReactIcon {
  background-image: var(--jp-icon-react);
}
.jp-RefreshIcon {
  background-image: var(--jp-icon-refresh);
}
.jp-RegexIcon {
  background-image: var(--jp-icon-regex);
}
.jp-RunIcon {
  background-image: var(--jp-icon-run);
}
.jp-RunningIcon {
  background-image: var(--jp-icon-running);
}
.jp-SaveIcon {
  background-image: var(--jp-icon-save);
}
.jp-SearchIcon {
  background-image: var(--jp-icon-search);
}
.jp-SettingsIcon {
  background-image: var(--jp-icon-settings);
}
.jp-SpreadsheetIcon {
  background-image: var(--jp-icon-spreadsheet);
}
.jp-StopIcon {
  background-image: var(--jp-icon-stop);
}
.jp-TabIcon {
  background-image: var(--jp-icon-tab);
}
.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}
.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}
.jp-TrustedIcon {
  background-image: var(--jp-icon-trusted);
}
.jp-UndoIcon {
  background-image: var(--jp-icon-undo);
}
.jp-VegaIcon {
  background-image: var(--jp-icon-vega);
}
.jp-YamlIcon {
  background-image: var(--jp-icon-yaml);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * (DEPRECATED) Support for consuming icons as CSS background images
 */

:root {
  --jp-icon-search-white: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyLjEsMTAuOWgtMC43bC0wLjItMC4yYzAuOC0wLjksMS4zLTIuMiwxLjMtMy41YzAtMy0yLjQtNS40LTUuNC01LjRTMS44LDQuMiwxLjgsNy4xczIuNCw1LjQsNS40LDUuNCBjMS4zLDAsMi41LTAuNSwzLjUtMS4zbDAuMiwwLjJ2MC43bDQuMSw0LjFsMS4yLTEuMkwxMi4xLDEwLjl6IE03LjEsMTAuOWMtMi4xLDAtMy43LTEuNy0zLjctMy43czEuNy0zLjcsMy43LTMuN3MzLjcsMS43LDMuNywzLjcgUzkuMiwxMC45LDcuMSwxMC45eiIvPgogIDwvZz4KPC9zdmc+Cg==);
}

.jp-Icon,
.jp-MaterialIcon {
  background-position: center;
  background-repeat: no-repeat;
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-cover {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

/**
 * (DEPRECATED) Support for specific CSS icon sizes
 */

.jp-Icon-16 {
  background-size: 16px;
  min-width: 16px;
  min-height: 16px;
}

.jp-Icon-18 {
  background-size: 18px;
  min-width: 18px;
  min-height: 18px;
}

.jp-Icon-20 {
  background-size: 20px;
  min-width: 20px;
  min-height: 20px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for icons as inline SVG HTMLElements
 */

/* recolor the primary elements of an icon */
.jp-icon0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}
/* recolor the accent elements of an icon */
.jp-icon-accent0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-accent1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-accent2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-accent3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-accent4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-accent0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-accent1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-accent2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-accent3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-accent4[stroke] {
  stroke: var(--jp-layout-color4);
}
/* set the color of an icon to transparent */
.jp-icon-none[fill] {
  fill: none;
}

.jp-icon-none[stroke] {
  stroke: none;
}
/* brand icon colors. Same for light and dark */
.jp-icon-brand0[fill] {
  fill: var(--jp-brand-color0);
}
.jp-icon-brand1[fill] {
  fill: var(--jp-brand-color1);
}
.jp-icon-brand2[fill] {
  fill: var(--jp-brand-color2);
}
.jp-icon-brand3[fill] {
  fill: var(--jp-brand-color3);
}
.jp-icon-brand4[fill] {
  fill: var(--jp-brand-color4);
}

.jp-icon-brand0[stroke] {
  stroke: var(--jp-brand-color0);
}
.jp-icon-brand1[stroke] {
  stroke: var(--jp-brand-color1);
}
.jp-icon-brand2[stroke] {
  stroke: var(--jp-brand-color2);
}
.jp-icon-brand3[stroke] {
  stroke: var(--jp-brand-color3);
}
.jp-icon-brand4[stroke] {
  stroke: var(--jp-brand-color4);
}
/* warn icon colors. Same for light and dark */
.jp-icon-warn0[fill] {
  fill: var(--jp-warn-color0);
}
.jp-icon-warn1[fill] {
  fill: var(--jp-warn-color1);
}
.jp-icon-warn2[fill] {
  fill: var(--jp-warn-color2);
}
.jp-icon-warn3[fill] {
  fill: var(--jp-warn-color3);
}

.jp-icon-warn0[stroke] {
  stroke: var(--jp-warn-color0);
}
.jp-icon-warn1[stroke] {
  stroke: var(--jp-warn-color1);
}
.jp-icon-warn2[stroke] {
  stroke: var(--jp-warn-color2);
}
.jp-icon-warn3[stroke] {
  stroke: var(--jp-warn-color3);
}
/* icon colors that contrast well with each other and most backgrounds */
.jp-icon-contrast0[fill] {
  fill: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[fill] {
  fill: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[fill] {
  fill: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[fill] {
  fill: var(--jp-icon-contrast-color3);
}

.jp-icon-contrast0[stroke] {
  stroke: var(--jp-icon-contrast-color0);
}
.jp-icon-contrast1[stroke] {
  stroke: var(--jp-icon-contrast-color1);
}
.jp-icon-contrast2[stroke] {
  stroke: var(--jp-icon-contrast-color2);
}
.jp-icon-contrast3[stroke] {
  stroke: var(--jp-icon-contrast-color3);
}

/* CSS for icons in selected items in the settings editor */
#setting-editor .jp-PluginList .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
#setting-editor
  .jp-PluginList
  .jp-mod-selected
  .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected filebrowser listing items */
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}
.jp-DirListing-item.jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}

/* CSS for icons in selected tabs in the sidebar tab manager */
#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable[fill] {
  fill: #fff;
}

#tab-manager .lm-TabBar-tab.jp-mod-active .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable[fill] {
  fill: var(--jp-brand-color1);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-active
  .jp-icon-hover
  :hover
  .jp-icon-selectable-inverse[fill] {
  fill: #fff;
}

/**
 * TODO: come up with non css-hack solution for showing the busy icon on top
 *  of the close icon
 * CSS for complex behavior of close icon of tabs in the sidebar tab manager
 */
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
#tab-manager
  .lm-TabBar-tab.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

#tab-manager
  .lm-TabBar-tab.jp-mod-dirty.jp-mod-active
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: #fff;
}

/**
* TODO: come up with non css-hack solution for showing the busy icon on top
*  of the close icon
* CSS for complex behavior of close icon of tabs in the main area tabbar
*/
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon3[fill] {
  fill: none;
}
.lm-DockPanel-tabBar
  .lm-TabBar-tab.lm-mod-closable.jp-mod-dirty
  > .lm-TabBar-tabCloseIcon
  > :not(:hover)
  > .jp-icon-busy[fill] {
  fill: var(--jp-inverse-layout-color3);
}

/* CSS for icons in status bar */
#jp-main-statusbar .jp-mod-selected .jp-icon-selectable[fill] {
  fill: #fff;
}

#jp-main-statusbar .jp-mod-selected .jp-icon-selectable-inverse[fill] {
  fill: var(--jp-brand-color1);
}
/* special handling for splash icon CSS. While the theme CSS reloads during
   splash, the splash icon can loose theming. To prevent that, we set a
   default for its color variable */
:root {
  --jp-warn-color0: var(--md-orange-700);
}

/* not sure what to do with this one, used in filebrowser listing */
.jp-DragIcon {
  margin-right: 4px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/**
 * Support for alt colors for icons as inline SVG HTMLElements
 */

/* alt recolor the primary elements of an icon */
.jp-icon-alt .jp-icon0[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-alt .jp-icon0[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-alt .jp-icon1[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-alt .jp-icon2[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-alt .jp-icon3[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-alt .jp-icon4[stroke] {
  stroke: var(--jp-layout-color4);
}

/* alt recolor the accent elements of an icon */
.jp-icon-alt .jp-icon-accent0[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-alt .jp-icon-accent0[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-alt .jp-icon-accent1[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-alt .jp-icon-accent2[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-alt .jp-icon-accent3[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-alt .jp-icon-accent4[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-icon-hoverShow:not(:hover) svg {
  display: none !important;
}

/**
 * Support for hover colors for icons as inline SVG HTMLElements
 */

/**
 * regular colors
 */

/* recolor the primary elements of an icon */
.jp-icon-hover :hover .jp-icon0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/* recolor the accent elements of an icon */
.jp-icon-hover :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* set the color of an icon to transparent */
.jp-icon-hover :hover .jp-icon-none-hover[fill] {
  fill: none;
}

.jp-icon-hover :hover .jp-icon-none-hover[stroke] {
  stroke: none;
}

/**
 * inverse colors
 */

/* inverse recolor the primary elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[fill] {
  fill: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[fill] {
  fill: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[fill] {
  fill: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[fill] {
  fill: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[fill] {
  fill: var(--jp-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon0-hover[stroke] {
  stroke: var(--jp-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon1-hover[stroke] {
  stroke: var(--jp-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon2-hover[stroke] {
  stroke: var(--jp-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon3-hover[stroke] {
  stroke: var(--jp-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon4-hover[stroke] {
  stroke: var(--jp-layout-color4);
}

/* inverse recolor the accent elements of an icon */
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[fill] {
  fill: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[fill] {
  fill: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[fill] {
  fill: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[fill] {
  fill: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[fill] {
  fill: var(--jp-inverse-layout-color4);
}

.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent0-hover[stroke] {
  stroke: var(--jp-inverse-layout-color0);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent1-hover[stroke] {
  stroke: var(--jp-inverse-layout-color1);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent2-hover[stroke] {
  stroke: var(--jp-inverse-layout-color2);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent3-hover[stroke] {
  stroke: var(--jp-inverse-layout-color3);
}
.jp-icon-hover.jp-icon-alt :hover .jp-icon-accent4-hover[stroke] {
  stroke: var(--jp-inverse-layout-color4);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* Sibling imports */

/* Override Blueprint's _reset.scss styles */
html {
  box-sizing: unset;
}

*,
*::before,
*::after {
  box-sizing: unset;
}

body {
  color: unset;
  font-family: var(--jp-ui-font-family);
}

p {
  margin-top: unset;
  margin-bottom: unset;
}

small {
  font-size: unset;
}

strong {
  font-weight: unset;
}

/* Override Blueprint's _typography.scss styles */
a {
  text-decoration: unset;
  color: unset;
}
a:hover {
  text-decoration: unset;
  color: unset;
}

/* Override Blueprint's _accessibility.scss styles */
:focus {
  outline: unset;
  outline-offset: unset;
  -moz-outline-radius: unset;
}

/* Styles for ui-components */
.jp-Button {
  border-radius: var(--jp-border-radius);
  padding: 0px 12px;
  font-size: var(--jp-ui-font-size1);
}

/* Use our own theme for hover styles */
button.jp-Button.bp3-button.bp3-minimal:hover {
  background-color: var(--jp-layout-color2);
}
.jp-Button.minimal {
  color: unset !important;
}

.jp-Button.jp-ToolbarButtonComponent {
  text-transform: none;
}

.jp-InputGroup input {
  box-sizing: border-box;
  border-radius: 0;
  background-color: transparent;
  color: var(--jp-ui-font-color0);
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.jp-InputGroup input:focus {
  box-shadow: inset 0 0 0 var(--jp-border-width)
      var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.jp-InputGroup input::placeholder,
input::placeholder {
  color: var(--jp-ui-font-color3);
}

.jp-BPIcon {
  display: inline-block;
  vertical-align: middle;
  margin: auto;
}

/* Stop blueprint futzing with our icon fills */
.bp3-icon.jp-BPIcon > svg:not([fill]) {
  fill: var(--jp-inverse-layout-color3);
}

.jp-InputGroupAction {
  padding: 6px;
}

.jp-HTMLSelect.jp-DefaultStyle select {
  background-color: initial;
  border: none;
  border-radius: 0;
  box-shadow: none;
  color: var(--jp-ui-font-color0);
  display: block;
  font-size: var(--jp-ui-font-size1);
  height: 24px;
  line-height: 14px;
  padding: 0 25px 0 10px;
  text-align: left;
  -moz-appearance: none;
  -webkit-appearance: none;
}

/* Use our own theme for hover and option styles */
.jp-HTMLSelect.jp-DefaultStyle select:hover,
.jp-HTMLSelect.jp-DefaultStyle select > option {
  background-color: var(--jp-layout-color2);
  color: var(--jp-ui-font-color0);
}
select {
  box-sizing: border-box;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapse {
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-top: 1px solid var(--jp-border-color2);
  border-bottom: 1px solid var(--jp-border-color2);
}

.jp-Collapse-header {
  padding: 1px 12px;
  color: var(--jp-ui-font-color1);
  background-color: var(--jp-layout-color1);
  font-size: var(--jp-ui-font-size2);
}

.jp-Collapse-header:hover {
  background-color: var(--jp-layout-color2);
}

.jp-Collapse-contents {
  padding: 0px 12px 0px 12px;
  background-color: var(--jp-layout-color1);
  color: var(--jp-ui-font-color1);
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-commandpalette-search-height: 28px;
}

/*-----------------------------------------------------------------------------
| Overall styles
|----------------------------------------------------------------------------*/

.lm-CommandPalette {
  padding-bottom: 0px;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Search
|----------------------------------------------------------------------------*/

.lm-CommandPalette-search {
  padding: 4px;
  background-color: var(--jp-layout-color1);
  z-index: 2;
}

.lm-CommandPalette-wrapper {
  overflow: overlay;
  padding: 0px 9px;
  background-color: var(--jp-input-active-background);
  height: 30px;
  box-shadow: inset 0 0 0 var(--jp-border-width) var(--jp-input-border-color);
}

.lm-CommandPalette.lm-mod-focused .lm-CommandPalette-wrapper {
  box-shadow: inset 0 0 0 1px var(--jp-input-active-box-shadow-color),
    inset 0 0 0 3px var(--jp-input-active-box-shadow-color);
}

.lm-CommandPalette-wrapper::after {
  content: ' ';
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  height: 30px;
  width: 10px;
  padding: 0px 10px;
  background-image: var(--jp-icon-search-white);
  background-size: 20px;
  background-repeat: no-repeat;
  background-position: center;
}

.lm-CommandPalette-input {
  background: transparent;
  width: calc(100% - 18px);
  float: left;
  border: none;
  outline: none;
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  line-height: var(--jp-private-commandpalette-search-height);
}

.lm-CommandPalette-input::-webkit-input-placeholder,
.lm-CommandPalette-input::-moz-placeholder,
.lm-CommandPalette-input:-ms-input-placeholder {
  color: var(--jp-ui-font-color3);
  font-size: var(--jp-ui-font-size1);
}

/*-----------------------------------------------------------------------------
| Results
|----------------------------------------------------------------------------*/

.lm-CommandPalette-header:first-child {
  margin-top: 0px;
}

.lm-CommandPalette-header {
  border-bottom: solid var(--jp-border-width) var(--jp-border-color2);
  color: var(--jp-ui-font-color1);
  cursor: pointer;
  display: flex;
  font-size: var(--jp-ui-font-size0);
  font-weight: 600;
  letter-spacing: 1px;
  margin-top: 8px;
  padding: 8px 0 8px 12px;
  text-transform: uppercase;
}

.lm-CommandPalette-header.lm-mod-active {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-header > mark {
  background-color: transparent;
  font-weight: bold;
  color: var(--jp-ui-font-color1);
}

.lm-CommandPalette-item {
  padding: 4px 12px 4px 4px;
  color: var(--jp-ui-font-color1);
  font-size: var(--jp-ui-font-size1);
  font-weight: 400;
  display: flex;
}

.lm-CommandPalette-item.lm-mod-disabled {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item.lm-mod-active {
  background: var(--jp-layout-color3);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  background: var(--jp-layout-color4);
}

.lm-CommandPalette-item:hover:not(.lm-mod-active):not(.lm-mod-disabled) {
  background: var(--jp-layout-color2);
}

.lm-CommandPalette-itemContent {
  overflow: hidden;
}

.lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.lm-CommandPalette-item.lm-mod-disabled mark {
  color: var(--jp-ui-font-color3);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.4;
}

.lm-CommandPalette-item .lm-CommandPalette-itemShortcut {
  flex: 0 0 auto;
}

.lm-CommandPalette-itemCaption {
  display: none;
}

.lm-CommandPalette-content {
  background-color: var(--jp-layout-color1);
}

.lm-CommandPalette-content:empty:after {
  content: 'No results';
  margin: auto;
  margin-top: 20px;
  width: 100px;
  display: block;
  font-size: var(--jp-ui-font-size2);
  font-family: var(--jp-ui-font-family);
  font-weight: lighter;
}

.lm-CommandPalette-emptyMessage {
  text-align: center;
  margin-top: 24px;
  line-height: 1.32;
  padding: 0px 8px;
  color: var(--jp-content-font-color3);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Dialog {
  position: absolute;
  z-index: 10000;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  top: 0px;
  left: 0px;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-dialog-background);
}

.jp-Dialog-content {
  display: flex;
  flex-direction: column;
  margin-left: auto;
  margin-right: auto;
  background: var(--jp-layout-color1);
  padding: 24px;
  padding-bottom: 12px;
  min-width: 300px;
  min-height: 150px;
  max-width: 1000px;
  max-height: 500px;
  box-sizing: border-box;
  box-shadow: var(--jp-elevation-z20);
  word-wrap: break-word;
  border-radius: var(--jp-border-radius);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color1);
}

.jp-Dialog-button {
  overflow: visible;
}

button.jp-Dialog-button:focus {
  outline: 1px solid var(--jp-brand-color1);
  outline-offset: 4px;
  -moz-outline-radius: 0px;
}

button.jp-Dialog-button:focus::-moz-focus-inner {
  border: 0;
}

.jp-Dialog-header {
  flex: 0 0 auto;
  padding-bottom: 12px;
  font-size: var(--jp-ui-font-size3);
  font-weight: 400;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-body {
  display: flex;
  flex-direction: column;
  flex: 1 1 auto;
  font-size: var(--jp-ui-font-size1);
  background: var(--jp-layout-color1);
  overflow: auto;
}

.jp-Dialog-footer {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  flex: 0 0 auto;
  margin-left: -12px;
  margin-right: -12px;
  padding: 12px;
}

.jp-Dialog-title {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}

.jp-Dialog-body > .jp-select-wrapper {
  width: 100%;
}

.jp-Dialog-body > button {
  padding: 0px 16px;
}

.jp-Dialog-body > label {
  line-height: 1.4;
  color: var(--jp-ui-font-color0);
}

.jp-Dialog-button.jp-mod-styled:not(:last-child) {
  margin-right: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-HoverBox {
  position: fixed;
}

.jp-HoverBox.jp-mod-outofview {
  display: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-IFrame {
  width: 100%;
  height: 100%;
}

.jp-IFrame > iframe {
  border: none;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-IFrame {
  position: relative;
}

body.lm-mod-override-cursor .jp-IFrame:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MainAreaWidget > :focus {
  outline: none;
}

/**
 * google-material-color v1.2.6
 * https://github.com/danlevan/google-material-color
 */
:root {
  --md-red-50: #ffebee;
  --md-red-100: #ffcdd2;
  --md-red-200: #ef9a9a;
  --md-red-300: #e57373;
  --md-red-400: #ef5350;
  --md-red-500: #f44336;
  --md-red-600: #e53935;
  --md-red-700: #d32f2f;
  --md-red-800: #c62828;
  --md-red-900: #b71c1c;
  --md-red-A100: #ff8a80;
  --md-red-A200: #ff5252;
  --md-red-A400: #ff1744;
  --md-red-A700: #d50000;

  --md-pink-50: #fce4ec;
  --md-pink-100: #f8bbd0;
  --md-pink-200: #f48fb1;
  --md-pink-300: #f06292;
  --md-pink-400: #ec407a;
  --md-pink-500: #e91e63;
  --md-pink-600: #d81b60;
  --md-pink-700: #c2185b;
  --md-pink-800: #ad1457;
  --md-pink-900: #880e4f;
  --md-pink-A100: #ff80ab;
  --md-pink-A200: #ff4081;
  --md-pink-A400: #f50057;
  --md-pink-A700: #c51162;

  --md-purple-50: #f3e5f5;
  --md-purple-100: #e1bee7;
  --md-purple-200: #ce93d8;
  --md-purple-300: #ba68c8;
  --md-purple-400: #ab47bc;
  --md-purple-500: #9c27b0;
  --md-purple-600: #8e24aa;
  --md-purple-700: #7b1fa2;
  --md-purple-800: #6a1b9a;
  --md-purple-900: #4a148c;
  --md-purple-A100: #ea80fc;
  --md-purple-A200: #e040fb;
  --md-purple-A400: #d500f9;
  --md-purple-A700: #aa00ff;

  --md-deep-purple-50: #ede7f6;
  --md-deep-purple-100: #d1c4e9;
  --md-deep-purple-200: #b39ddb;
  --md-deep-purple-300: #9575cd;
  --md-deep-purple-400: #7e57c2;
  --md-deep-purple-500: #673ab7;
  --md-deep-purple-600: #5e35b1;
  --md-deep-purple-700: #512da8;
  --md-deep-purple-800: #4527a0;
  --md-deep-purple-900: #311b92;
  --md-deep-purple-A100: #b388ff;
  --md-deep-purple-A200: #7c4dff;
  --md-deep-purple-A400: #651fff;
  --md-deep-purple-A700: #6200ea;

  --md-indigo-50: #e8eaf6;
  --md-indigo-100: #c5cae9;
  --md-indigo-200: #9fa8da;
  --md-indigo-300: #7986cb;
  --md-indigo-400: #5c6bc0;
  --md-indigo-500: #3f51b5;
  --md-indigo-600: #3949ab;
  --md-indigo-700: #303f9f;
  --md-indigo-800: #283593;
  --md-indigo-900: #1a237e;
  --md-indigo-A100: #8c9eff;
  --md-indigo-A200: #536dfe;
  --md-indigo-A400: #3d5afe;
  --md-indigo-A700: #304ffe;

  --md-blue-50: #e3f2fd;
  --md-blue-100: #bbdefb;
  --md-blue-200: #90caf9;
  --md-blue-300: #64b5f6;
  --md-blue-400: #42a5f5;
  --md-blue-500: #2196f3;
  --md-blue-600: #1e88e5;
  --md-blue-700: #1976d2;
  --md-blue-800: #1565c0;
  --md-blue-900: #0d47a1;
  --md-blue-A100: #82b1ff;
  --md-blue-A200: #448aff;
  --md-blue-A400: #2979ff;
  --md-blue-A700: #2962ff;

  --md-light-blue-50: #e1f5fe;
  --md-light-blue-100: #b3e5fc;
  --md-light-blue-200: #81d4fa;
  --md-light-blue-300: #4fc3f7;
  --md-light-blue-400: #29b6f6;
  --md-light-blue-500: #03a9f4;
  --md-light-blue-600: #039be5;
  --md-light-blue-700: #0288d1;
  --md-light-blue-800: #0277bd;
  --md-light-blue-900: #01579b;
  --md-light-blue-A100: #80d8ff;
  --md-light-blue-A200: #40c4ff;
  --md-light-blue-A400: #00b0ff;
  --md-light-blue-A700: #0091ea;

  --md-cyan-50: #e0f7fa;
  --md-cyan-100: #b2ebf2;
  --md-cyan-200: #80deea;
  --md-cyan-300: #4dd0e1;
  --md-cyan-400: #26c6da;
  --md-cyan-500: #00bcd4;
  --md-cyan-600: #00acc1;
  --md-cyan-700: #0097a7;
  --md-cyan-800: #00838f;
  --md-cyan-900: #006064;
  --md-cyan-A100: #84ffff;
  --md-cyan-A200: #18ffff;
  --md-cyan-A400: #00e5ff;
  --md-cyan-A700: #00b8d4;

  --md-teal-50: #e0f2f1;
  --md-teal-100: #b2dfdb;
  --md-teal-200: #80cbc4;
  --md-teal-300: #4db6ac;
  --md-teal-400: #26a69a;
  --md-teal-500: #009688;
  --md-teal-600: #00897b;
  --md-teal-700: #00796b;
  --md-teal-800: #00695c;
  --md-teal-900: #004d40;
  --md-teal-A100: #a7ffeb;
  --md-teal-A200: #64ffda;
  --md-teal-A400: #1de9b6;
  --md-teal-A700: #00bfa5;

  --md-green-50: #e8f5e9;
  --md-green-100: #c8e6c9;
  --md-green-200: #a5d6a7;
  --md-green-300: #81c784;
  --md-green-400: #66bb6a;
  --md-green-500: #4caf50;
  --md-green-600: #43a047;
  --md-green-700: #388e3c;
  --md-green-800: #2e7d32;
  --md-green-900: #1b5e20;
  --md-green-A100: #b9f6ca;
  --md-green-A200: #69f0ae;
  --md-green-A400: #00e676;
  --md-green-A700: #00c853;

  --md-light-green-50: #f1f8e9;
  --md-light-green-100: #dcedc8;
  --md-light-green-200: #c5e1a5;
  --md-light-green-300: #aed581;
  --md-light-green-400: #9ccc65;
  --md-light-green-500: #8bc34a;
  --md-light-green-600: #7cb342;
  --md-light-green-700: #689f38;
  --md-light-green-800: #558b2f;
  --md-light-green-900: #33691e;
  --md-light-green-A100: #ccff90;
  --md-light-green-A200: #b2ff59;
  --md-light-green-A400: #76ff03;
  --md-light-green-A700: #64dd17;

  --md-lime-50: #f9fbe7;
  --md-lime-100: #f0f4c3;
  --md-lime-200: #e6ee9c;
  --md-lime-300: #dce775;
  --md-lime-400: #d4e157;
  --md-lime-500: #cddc39;
  --md-lime-600: #c0ca33;
  --md-lime-700: #afb42b;
  --md-lime-800: #9e9d24;
  --md-lime-900: #827717;
  --md-lime-A100: #f4ff81;
  --md-lime-A200: #eeff41;
  --md-lime-A400: #c6ff00;
  --md-lime-A700: #aeea00;

  --md-yellow-50: #fffde7;
  --md-yellow-100: #fff9c4;
  --md-yellow-200: #fff59d;
  --md-yellow-300: #fff176;
  --md-yellow-400: #ffee58;
  --md-yellow-500: #ffeb3b;
  --md-yellow-600: #fdd835;
  --md-yellow-700: #fbc02d;
  --md-yellow-800: #f9a825;
  --md-yellow-900: #f57f17;
  --md-yellow-A100: #ffff8d;
  --md-yellow-A200: #ffff00;
  --md-yellow-A400: #ffea00;
  --md-yellow-A700: #ffd600;

  --md-amber-50: #fff8e1;
  --md-amber-100: #ffecb3;
  --md-amber-200: #ffe082;
  --md-amber-300: #ffd54f;
  --md-amber-400: #ffca28;
  --md-amber-500: #ffc107;
  --md-amber-600: #ffb300;
  --md-amber-700: #ffa000;
  --md-amber-800: #ff8f00;
  --md-amber-900: #ff6f00;
  --md-amber-A100: #ffe57f;
  --md-amber-A200: #ffd740;
  --md-amber-A400: #ffc400;
  --md-amber-A700: #ffab00;

  --md-orange-50: #fff3e0;
  --md-orange-100: #ffe0b2;
  --md-orange-200: #ffcc80;
  --md-orange-300: #ffb74d;
  --md-orange-400: #ffa726;
  --md-orange-500: #ff9800;
  --md-orange-600: #fb8c00;
  --md-orange-700: #f57c00;
  --md-orange-800: #ef6c00;
  --md-orange-900: #e65100;
  --md-orange-A100: #ffd180;
  --md-orange-A200: #ffab40;
  --md-orange-A400: #ff9100;
  --md-orange-A700: #ff6d00;

  --md-deep-orange-50: #fbe9e7;
  --md-deep-orange-100: #ffccbc;
  --md-deep-orange-200: #ffab91;
  --md-deep-orange-300: #ff8a65;
  --md-deep-orange-400: #ff7043;
  --md-deep-orange-500: #ff5722;
  --md-deep-orange-600: #f4511e;
  --md-deep-orange-700: #e64a19;
  --md-deep-orange-800: #d84315;
  --md-deep-orange-900: #bf360c;
  --md-deep-orange-A100: #ff9e80;
  --md-deep-orange-A200: #ff6e40;
  --md-deep-orange-A400: #ff3d00;
  --md-deep-orange-A700: #dd2c00;

  --md-brown-50: #efebe9;
  --md-brown-100: #d7ccc8;
  --md-brown-200: #bcaaa4;
  --md-brown-300: #a1887f;
  --md-brown-400: #8d6e63;
  --md-brown-500: #795548;
  --md-brown-600: #6d4c41;
  --md-brown-700: #5d4037;
  --md-brown-800: #4e342e;
  --md-brown-900: #3e2723;

  --md-grey-50: #fafafa;
  --md-grey-100: #f5f5f5;
  --md-grey-200: #eeeeee;
  --md-grey-300: #e0e0e0;
  --md-grey-400: #bdbdbd;
  --md-grey-500: #9e9e9e;
  --md-grey-600: #757575;
  --md-grey-700: #616161;
  --md-grey-800: #424242;
  --md-grey-900: #212121;

  --md-blue-grey-50: #eceff1;
  --md-blue-grey-100: #cfd8dc;
  --md-blue-grey-200: #b0bec5;
  --md-blue-grey-300: #90a4ae;
  --md-blue-grey-400: #78909c;
  --md-blue-grey-500: #607d8b;
  --md-blue-grey-600: #546e7a;
  --md-blue-grey-700: #455a64;
  --md-blue-grey-800: #37474f;
  --md-blue-grey-900: #263238;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Spinner {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 10;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: var(--jp-layout-color0);
  outline: none;
}

.jp-SpinnerContent {
  font-size: 10px;
  margin: 50px auto;
  text-indent: -9999em;
  width: 3em;
  height: 3em;
  border-radius: 50%;
  background: var(--jp-brand-color3);
  background: linear-gradient(
    to right,
    #f37626 10%,
    rgba(255, 255, 255, 0) 42%
  );
  position: relative;
  animation: load3 1s infinite linear, fadeIn 1s;
}

.jp-SpinnerContent:before {
  width: 50%;
  height: 50%;
  background: #f37626;
  border-radius: 100% 0 0 0;
  position: absolute;
  top: 0;
  left: 0;
  content: '';
}

.jp-SpinnerContent:after {
  background: var(--jp-layout-color0);
  width: 75%;
  height: 75%;
  border-radius: 50%;
  content: '';
  margin: auto;
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes load3 {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

button.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: none;
  box-sizing: border-box;
  text-align: center;
  line-height: 32px;
  height: 32px;
  padding: 0px 12px;
  letter-spacing: 0.8px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled {
  background: var(--jp-input-background);
  height: 28px;
  box-sizing: border-box;
  border: var(--jp-border-width) solid var(--jp-border-color1);
  padding-left: 7px;
  padding-right: 7px;
  font-size: var(--jp-ui-font-size2);
  color: var(--jp-ui-font-color0);
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-select-wrapper {
  display: flex;
  position: relative;
  flex-direction: column;
  padding: 1px;
  background-color: var(--jp-layout-color1);
  height: 28px;
  box-sizing: border-box;
  margin-bottom: 12px;
}

.jp-select-wrapper.jp-mod-focused select.jp-mod-styled {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-input-active-background);
}

select.jp-mod-styled:hover {
  background-color: var(--jp-layout-color1);
  cursor: pointer;
  color: var(--jp-ui-font-color0);
  background-color: var(--jp-input-hover-background);
  box-shadow: inset 0 0px 1px rgba(0, 0, 0, 0.5);
}

select.jp-mod-styled {
  flex: 1 1 auto;
  height: 32px;
  width: 100%;
  font-size: var(--jp-ui-font-size2);
  background: var(--jp-input-background);
  color: var(--jp-ui-font-color0);
  padding: 0 25px 0 8px;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

:root {
  --jp-private-toolbar-height: calc(
    28px + var(--jp-border-width)
  ); /* leave 28px for content */
}

.jp-Toolbar {
  color: var(--jp-ui-font-color1);
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  border-bottom: var(--jp-border-width) solid var(--jp-toolbar-border-color);
  box-shadow: var(--jp-toolbar-box-shadow);
  background: var(--jp-toolbar-background);
  min-height: var(--jp-toolbar-micro-height);
  padding: 2px;
  z-index: 1;
}

/* Toolbar items */

.jp-Toolbar > .jp-Toolbar-item.jp-Toolbar-spacer {
  flex-grow: 1;
  flex-shrink: 1;
}

.jp-Toolbar-item.jp-Toolbar-kernelStatus {
  display: inline-block;
  width: 32px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px;
}

.jp-Toolbar > .jp-Toolbar-item {
  flex: 0 0 auto;
  display: flex;
  padding-left: 1px;
  padding-right: 1px;
  font-size: var(--jp-ui-font-size1);
  line-height: var(--jp-private-toolbar-height);
  height: 100%;
}

/* Toolbar buttons */

/* This is the div we use to wrap the react component into a Widget */
div.jp-ToolbarButton {
  color: transparent;
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px;
  margin: 0px;
}

button.jp-ToolbarButtonComponent {
  background: var(--jp-layout-color1);
  border: none;
  box-sizing: border-box;
  outline: none;
  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  padding: 0px 6px;
  margin: 0px;
  height: 24px;
  border-radius: var(--jp-border-radius);
  display: flex;
  align-items: center;
  text-align: center;
  font-size: 14px;
  min-width: unset;
  min-height: unset;
}

button.jp-ToolbarButtonComponent:disabled {
  opacity: 0.4;
}

button.jp-ToolbarButtonComponent span {
  padding: 0px;
  flex: 0 0 auto;
}

button.jp-ToolbarButtonComponent .jp-ToolbarButtonComponent-label {
  font-size: var(--jp-ui-font-size1);
  line-height: 100%;
  padding-left: 2px;
  color: var(--jp-ui-font-color1);
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Copyright (c) 2014-2017, PhosphorJS Contributors
|
| Distributed under the terms of the BSD 3-Clause License.
|
| The full license is in the file LICENSE, distributed with this software.
|----------------------------------------------------------------------------*/


/* <DEPRECATED> */ body.p-mod-override-cursor *, /* </DEPRECATED> */
body.lm-mod-override-cursor * {
  cursor: inherit !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2016, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-JSONEditor {
  display: flex;
  flex-direction: column;
  width: 100%;
}

.jp-JSONEditor-host {
  flex: 1 1 auto;
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  border-radius: 0px;
  background: var(--jp-layout-color0);
  min-height: 50px;
  padding: 1px;
}

.jp-JSONEditor.jp-mod-error .jp-JSONEditor-host {
  border-color: red;
  outline-color: red;
}

.jp-JSONEditor-header {
  display: flex;
  flex: 1 0 auto;
  padding: 0 0 0 12px;
}

.jp-JSONEditor-header label {
  flex: 0 0 auto;
}

.jp-JSONEditor-commitButton {
  height: 16px;
  width: 16px;
  background-size: 18px;
  background-repeat: no-repeat;
  background-position: center;
}

.jp-JSONEditor-host.jp-mod-focused {
  background-color: var(--jp-input-active-background);
  border: 1px solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

.jp-Editor.jp-mod-dropTarget {
  border: var(--jp-border-width) solid var(--jp-input-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* BASICS */

.CodeMirror {
  /* Set height, width, borders, and global font properties here */
  font-family: monospace;
  height: 300px;
  color: black;
  direction: ltr;
}

/* PADDING */

.CodeMirror-lines {
  padding: 4px 0; /* Vertical padding around content */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  padding: 0 4px; /* Horizontal padding of content */
}

.CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  background-color: white; /* The little square between H and V scrollbars */
}

/* GUTTER */

.CodeMirror-gutters {
  border-right: 1px solid #ddd;
  background-color: #f7f7f7;
  white-space: nowrap;
}
.CodeMirror-linenumbers {}
.CodeMirror-linenumber {
  padding: 0 3px 0 5px;
  min-width: 20px;
  text-align: right;
  color: #999;
  white-space: nowrap;
}

.CodeMirror-guttermarker { color: black; }
.CodeMirror-guttermarker-subtle { color: #999; }

/* CURSOR */

.CodeMirror-cursor {
  border-left: 1px solid black;
  border-right: none;
  width: 0;
}
/* Shown when moving in bi-directional text */
.CodeMirror div.CodeMirror-secondarycursor {
  border-left: 1px solid silver;
}
.cm-fat-cursor .CodeMirror-cursor {
  width: auto;
  border: 0 !important;
  background: #7e7;
}
.cm-fat-cursor div.CodeMirror-cursors {
  z-index: 1;
}
.cm-fat-cursor-mark {
  background-color: rgba(20, 255, 20, 0.5);
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
}
.cm-animate-fat-cursor {
  width: auto;
  border: 0;
  -webkit-animation: blink 1.06s steps(1) infinite;
  -moz-animation: blink 1.06s steps(1) infinite;
  animation: blink 1.06s steps(1) infinite;
  background-color: #7e7;
}
@-moz-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@-webkit-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}

/* Can style cursor different in overwrite (non-insert) mode */
.CodeMirror-overwrite .CodeMirror-cursor {}

.cm-tab { display: inline-block; text-decoration: inherit; }

.CodeMirror-rulers {
  position: absolute;
  left: 0; right: 0; top: -50px; bottom: 0;
  overflow: hidden;
}
.CodeMirror-ruler {
  border-left: 1px solid #ccc;
  top: 0; bottom: 0;
  position: absolute;
}

/* DEFAULT THEME */

.cm-s-default .cm-header {color: blue;}
.cm-s-default .cm-quote {color: #090;}
.cm-negative {color: #d44;}
.cm-positive {color: #292;}
.cm-header, .cm-strong {font-weight: bold;}
.cm-em {font-style: italic;}
.cm-link {text-decoration: underline;}
.cm-strikethrough {text-decoration: line-through;}

.cm-s-default .cm-keyword {color: #708;}
.cm-s-default .cm-atom {color: #219;}
.cm-s-default .cm-number {color: #164;}
.cm-s-default .cm-def {color: #00f;}
.cm-s-default .cm-variable,
.cm-s-default .cm-punctuation,
.cm-s-default .cm-property,
.cm-s-default .cm-operator {}
.cm-s-default .cm-variable-2 {color: #05a;}
.cm-s-default .cm-variable-3, .cm-s-default .cm-type {color: #085;}
.cm-s-default .cm-comment {color: #a50;}
.cm-s-default .cm-string {color: #a11;}
.cm-s-default .cm-string-2 {color: #f50;}
.cm-s-default .cm-meta {color: #555;}
.cm-s-default .cm-qualifier {color: #555;}
.cm-s-default .cm-builtin {color: #30a;}
.cm-s-default .cm-bracket {color: #997;}
.cm-s-default .cm-tag {color: #170;}
.cm-s-default .cm-attribute {color: #00c;}
.cm-s-default .cm-hr {color: #999;}
.cm-s-default .cm-link {color: #00c;}

.cm-s-default .cm-error {color: #f00;}
.cm-invalidchar {color: #f00;}

.CodeMirror-composing { border-bottom: 2px solid; }

/* Default styles for common addons */

div.CodeMirror span.CodeMirror-matchingbracket {color: #0b0;}
div.CodeMirror span.CodeMirror-nonmatchingbracket {color: #a22;}
.CodeMirror-matchingtag { background: rgba(255, 150, 0, .3); }
.CodeMirror-activeline-background {background: #e8f2ff;}

/* STOP */

/* The rest of this file contains styles related to the mechanics of
   the editor. You probably shouldn't touch them. */

.CodeMirror {
  position: relative;
  overflow: hidden;
  background: white;
}

.CodeMirror-scroll {
  overflow: scroll !important; /* Things will break if this is overridden */
  /* 30px is the magic margin used to hide the element's real scrollbars */
  /* See overflow: hidden in .CodeMirror */
  margin-bottom: -30px; margin-right: -30px;
  padding-bottom: 30px;
  height: 100%;
  outline: none; /* Prevent dragging from highlighting the element */
  position: relative;
}
.CodeMirror-sizer {
  position: relative;
  border-right: 30px solid transparent;
}

/* The fake, visible scrollbars. Used to force redraw during scrolling
   before actual scrolling happens, thus preventing shaking and
   flickering artifacts. */
.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  position: absolute;
  z-index: 6;
  display: none;
}
.CodeMirror-vscrollbar {
  right: 0; top: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}
.CodeMirror-hscrollbar {
  bottom: 0; left: 0;
  overflow-y: hidden;
  overflow-x: scroll;
}
.CodeMirror-scrollbar-filler {
  right: 0; bottom: 0;
}
.CodeMirror-gutter-filler {
  left: 0; bottom: 0;
}

.CodeMirror-gutters {
  position: absolute; left: 0; top: 0;
  min-height: 100%;
  z-index: 3;
}
.CodeMirror-gutter {
  white-space: normal;
  height: 100%;
  display: inline-block;
  vertical-align: top;
  margin-bottom: -30px;
}
.CodeMirror-gutter-wrapper {
  position: absolute;
  z-index: 4;
  background: none !important;
  border: none !important;
}
.CodeMirror-gutter-background {
  position: absolute;
  top: 0; bottom: 0;
  z-index: 4;
}
.CodeMirror-gutter-elt {
  position: absolute;
  cursor: default;
  z-index: 4;
}
.CodeMirror-gutter-wrapper ::selection { background-color: transparent }
.CodeMirror-gutter-wrapper ::-moz-selection { background-color: transparent }

.CodeMirror-lines {
  cursor: text;
  min-height: 1px; /* prevents collapsing before first draw */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  /* Reset some styles that the rest of the page might have set */
  -moz-border-radius: 0; -webkit-border-radius: 0; border-radius: 0;
  border-width: 0;
  background: transparent;
  font-family: inherit;
  font-size: inherit;
  margin: 0;
  white-space: pre;
  word-wrap: normal;
  line-height: inherit;
  color: inherit;
  z-index: 2;
  position: relative;
  overflow: visible;
  -webkit-tap-highlight-color: transparent;
  -webkit-font-variant-ligatures: contextual;
  font-variant-ligatures: contextual;
}
.CodeMirror-wrap pre.CodeMirror-line,
.CodeMirror-wrap pre.CodeMirror-line-like {
  word-wrap: break-word;
  white-space: pre-wrap;
  word-break: normal;
}

.CodeMirror-linebackground {
  position: absolute;
  left: 0; right: 0; top: 0; bottom: 0;
  z-index: 0;
}

.CodeMirror-linewidget {
  position: relative;
  z-index: 2;
  padding: 0.1px; /* Force widget margins to stay inside of the container */
}

.CodeMirror-widget {}

.CodeMirror-rtl pre { direction: rtl; }

.CodeMirror-code {
  outline: none;
}

/* Force content-box sizing for the elements where we expect it */
.CodeMirror-scroll,
.CodeMirror-sizer,
.CodeMirror-gutter,
.CodeMirror-gutters,
.CodeMirror-linenumber {
  -moz-box-sizing: content-box;
  box-sizing: content-box;
}

.CodeMirror-measure {
  position: absolute;
  width: 100%;
  height: 0;
  overflow: hidden;
  visibility: hidden;
}

.CodeMirror-cursor {
  position: absolute;
  pointer-events: none;
}
.CodeMirror-measure pre { position: static; }

div.CodeMirror-cursors {
  visibility: hidden;
  position: relative;
  z-index: 3;
}
div.CodeMirror-dragcursors {
  visibility: visible;
}

.CodeMirror-focused div.CodeMirror-cursors {
  visibility: visible;
}

.CodeMirror-selected { background: #d9d9d9; }
.CodeMirror-focused .CodeMirror-selected { background: #d7d4f0; }
.CodeMirror-crosshair { cursor: crosshair; }
.CodeMirror-line::selection, .CodeMirror-line > span::selection, .CodeMirror-line > span > span::selection { background: #d7d4f0; }
.CodeMirror-line::-moz-selection, .CodeMirror-line > span::-moz-selection, .CodeMirror-line > span > span::-moz-selection { background: #d7d4f0; }

.cm-searching {
  background-color: #ffa;
  background-color: rgba(255, 255, 0, .4);
}

/* Used to force a border model for a node */
.cm-force-border { padding-right: .1px; }

@media print {
  /* Hide the cursor when printing */
  .CodeMirror div.CodeMirror-cursors {
    visibility: hidden;
  }
}

/* See issue #2901 */
.cm-tab-wrap-hack:after { content: ''; }

/* Help users use markselection to safely style text background */
span.CodeMirror-selectedtext { background: none; }

.CodeMirror-dialog {
  position: absolute;
  left: 0; right: 0;
  background: inherit;
  z-index: 15;
  padding: .1em .8em;
  overflow: hidden;
  color: inherit;
}

.CodeMirror-dialog-top {
  border-bottom: 1px solid #eee;
  top: 0;
}

.CodeMirror-dialog-bottom {
  border-top: 1px solid #eee;
  bottom: 0;
}

.CodeMirror-dialog input {
  border: none;
  outline: none;
  background: transparent;
  width: 20em;
  color: inherit;
  font-family: monospace;
}

.CodeMirror-dialog button {
  font-size: 70%;
}

.CodeMirror-foldmarker {
  color: blue;
  text-shadow: #b9f 1px 1px 2px, #b9f -1px -1px 2px, #b9f 1px -1px 2px, #b9f -1px 1px 2px;
  font-family: arial;
  line-height: .3;
  cursor: pointer;
}
.CodeMirror-foldgutter {
  width: .7em;
}
.CodeMirror-foldgutter-open,
.CodeMirror-foldgutter-folded {
  cursor: pointer;
}
.CodeMirror-foldgutter-open:after {
  content: "\25BE";
}
.CodeMirror-foldgutter-folded:after {
  content: "\25B8";
}

/*
  Name:       material
  Author:     Mattia Astorino (http://github.com/equinusocio)
  Website:    https://material-theme.site/
*/

.cm-s-material.CodeMirror {
  background-color: #263238;
  color: #EEFFFF;
}

.cm-s-material .CodeMirror-gutters {
  background: #263238;
  color: #546E7A;
  border: none;
}

.cm-s-material .CodeMirror-guttermarker,
.cm-s-material .CodeMirror-guttermarker-subtle,
.cm-s-material .CodeMirror-linenumber {
  color: #546E7A;
}

.cm-s-material .CodeMirror-cursor {
  border-left: 1px solid #FFCC00;
}

.cm-s-material div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material.CodeMirror-focused div.CodeMirror-selected {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::selection,
.cm-s-material .CodeMirror-line>span::selection,
.cm-s-material .CodeMirror-line>span>span::selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-line::-moz-selection,
.cm-s-material .CodeMirror-line>span::-moz-selection,
.cm-s-material .CodeMirror-line>span>span::-moz-selection {
  background: rgba(128, 203, 196, 0.2);
}

.cm-s-material .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.5);
}

.cm-s-material .cm-keyword {
  color: #C792EA;
}

.cm-s-material .cm-operator {
  color: #89DDFF;
}

.cm-s-material .cm-variable-2 {
  color: #EEFFFF;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #f07178;
}

.cm-s-material .cm-builtin {
  color: #FFCB6B;
}

.cm-s-material .cm-atom {
  color: #F78C6C;
}

.cm-s-material .cm-number {
  color: #FF5370;
}

.cm-s-material .cm-def {
  color: #82AAFF;
}

.cm-s-material .cm-string {
  color: #C3E88D;
}

.cm-s-material .cm-string-2 {
  color: #f07178;
}

.cm-s-material .cm-comment {
  color: #546E7A;
}

.cm-s-material .cm-variable {
  color: #f07178;
}

.cm-s-material .cm-tag {
  color: #FF5370;
}

.cm-s-material .cm-meta {
  color: #FFCB6B;
}

.cm-s-material .cm-attribute {
  color: #C792EA;
}

.cm-s-material .cm-property {
  color: #C792EA;
}

.cm-s-material .cm-qualifier {
  color: #DECB6B;
}

.cm-s-material .cm-variable-3,
.cm-s-material .cm-type {
  color: #DECB6B;
}


.cm-s-material .cm-error {
  color: rgba(255, 255, 255, 1.0);
  background-color: #FF5370;
}

.cm-s-material .CodeMirror-matchingbracket {
  text-decoration: underline;
  color: white !important;
}
/**
 * "
 *  Using Zenburn color palette from the Emacs Zenburn Theme
 *  https://github.com/bbatsov/zenburn-emacs/blob/master/zenburn-theme.el
 *
 *  Also using parts of https://github.com/xavi/coderay-lighttable-theme
 * "
 * From: https://github.com/wisenomad/zenburn-lighttable-theme/blob/master/zenburn.css
 */

.cm-s-zenburn .CodeMirror-gutters { background: #3f3f3f !important; }
.cm-s-zenburn .CodeMirror-foldgutter-open, .CodeMirror-foldgutter-folded { color: #999; }
.cm-s-zenburn .CodeMirror-cursor { border-left: 1px solid white; }
.cm-s-zenburn { background-color: #3f3f3f; color: #dcdccc; }
.cm-s-zenburn span.cm-builtin { color: #dcdccc; font-weight: bold; }
.cm-s-zenburn span.cm-comment { color: #7f9f7f; }
.cm-s-zenburn span.cm-keyword { color: #f0dfaf; font-weight: bold; }
.cm-s-zenburn span.cm-atom { color: #bfebbf; }
.cm-s-zenburn span.cm-def { color: #dcdccc; }
.cm-s-zenburn span.cm-variable { color: #dfaf8f; }
.cm-s-zenburn span.cm-variable-2 { color: #dcdccc; }
.cm-s-zenburn span.cm-string { color: #cc9393; }
.cm-s-zenburn span.cm-string-2 { color: #cc9393; }
.cm-s-zenburn span.cm-number { color: #dcdccc; }
.cm-s-zenburn span.cm-tag { color: #93e0e3; }
.cm-s-zenburn span.cm-property { color: #dfaf8f; }
.cm-s-zenburn span.cm-attribute { color: #dfaf8f; }
.cm-s-zenburn span.cm-qualifier { color: #7cb8bb; }
.cm-s-zenburn span.cm-meta { color: #f0dfaf; }
.cm-s-zenburn span.cm-header { color: #f0efd0; }
.cm-s-zenburn span.cm-operator { color: #f0efd0; }
.cm-s-zenburn span.CodeMirror-matchingbracket { box-sizing: border-box; background: transparent; border-bottom: 1px solid; }
.cm-s-zenburn span.CodeMirror-nonmatchingbracket { border-bottom: 1px solid; background: none; }
.cm-s-zenburn .CodeMirror-activeline { background: #000000; }
.cm-s-zenburn .CodeMirror-activeline-background { background: #000000; }
.cm-s-zenburn div.CodeMirror-selected { background: #545454; }
.cm-s-zenburn .CodeMirror-focused div.CodeMirror-selected { background: #4f4f4f; }

.cm-s-abcdef.CodeMirror { background: #0f0f0f; color: #defdef; }
.cm-s-abcdef div.CodeMirror-selected { background: #515151; }
.cm-s-abcdef .CodeMirror-line::selection, .cm-s-abcdef .CodeMirror-line > span::selection, .cm-s-abcdef .CodeMirror-line > span > span::selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-line::-moz-selection, .cm-s-abcdef .CodeMirror-line > span::-moz-selection, .cm-s-abcdef .CodeMirror-line > span > span::-moz-selection { background: rgba(56, 56, 56, 0.99); }
.cm-s-abcdef .CodeMirror-gutters { background: #555; border-right: 2px solid #314151; }
.cm-s-abcdef .CodeMirror-guttermarker { color: #222; }
.cm-s-abcdef .CodeMirror-guttermarker-subtle { color: azure; }
.cm-s-abcdef .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-abcdef .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-abcdef span.cm-keyword { color: darkgoldenrod; font-weight: bold; }
.cm-s-abcdef span.cm-atom { color: #77F; }
.cm-s-abcdef span.cm-number { color: violet; }
.cm-s-abcdef span.cm-def { color: #fffabc; }
.cm-s-abcdef span.cm-variable { color: #abcdef; }
.cm-s-abcdef span.cm-variable-2 { color: #cacbcc; }
.cm-s-abcdef span.cm-variable-3, .cm-s-abcdef span.cm-type { color: #def; }
.cm-s-abcdef span.cm-property { color: #fedcba; }
.cm-s-abcdef span.cm-operator { color: #ff0; }
.cm-s-abcdef span.cm-comment { color: #7a7b7c; font-style: italic;}
.cm-s-abcdef span.cm-string { color: #2b4; }
.cm-s-abcdef span.cm-meta { color: #C9F; }
.cm-s-abcdef span.cm-qualifier { color: #FFF700; }
.cm-s-abcdef span.cm-builtin { color: #30aabc; }
.cm-s-abcdef span.cm-bracket { color: #8a8a8a; }
.cm-s-abcdef span.cm-tag { color: #FFDD44; }
.cm-s-abcdef span.cm-attribute { color: #DDFF00; }
.cm-s-abcdef span.cm-error { color: #FF0000; }
.cm-s-abcdef span.cm-header { color: aquamarine; font-weight: bold; }
.cm-s-abcdef span.cm-link { color: blueviolet; }

.cm-s-abcdef .CodeMirror-activeline-background { background: #314151; }

/*

    Name:       Base16 Default Light
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-light.CodeMirror { background: #f5f5f5; color: #202020; }
.cm-s-base16-light div.CodeMirror-selected { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::selection, .cm-s-base16-light .CodeMirror-line > span::selection, .cm-s-base16-light .CodeMirror-line > span > span::selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-line::-moz-selection, .cm-s-base16-light .CodeMirror-line > span::-moz-selection, .cm-s-base16-light .CodeMirror-line > span > span::-moz-selection { background: #e0e0e0; }
.cm-s-base16-light .CodeMirror-gutters { background: #f5f5f5; border-right: 0px; }
.cm-s-base16-light .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-light .CodeMirror-guttermarker-subtle { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-linenumber { color: #b0b0b0; }
.cm-s-base16-light .CodeMirror-cursor { border-left: 1px solid #505050; }

.cm-s-base16-light span.cm-comment { color: #8f5536; }
.cm-s-base16-light span.cm-atom { color: #aa759f; }
.cm-s-base16-light span.cm-number { color: #aa759f; }

.cm-s-base16-light span.cm-property, .cm-s-base16-light span.cm-attribute { color: #90a959; }
.cm-s-base16-light span.cm-keyword { color: #ac4142; }
.cm-s-base16-light span.cm-string { color: #f4bf75; }

.cm-s-base16-light span.cm-variable { color: #90a959; }
.cm-s-base16-light span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-light span.cm-def { color: #d28445; }
.cm-s-base16-light span.cm-bracket { color: #202020; }
.cm-s-base16-light span.cm-tag { color: #ac4142; }
.cm-s-base16-light span.cm-link { color: #aa759f; }
.cm-s-base16-light span.cm-error { background: #ac4142; color: #505050; }

.cm-s-base16-light .CodeMirror-activeline-background { background: #DDDCDC; }
.cm-s-base16-light .CodeMirror-matchingbracket { color: #f5f5f5 !important; background-color: #6A9FB5 !important}

/*

    Name:       Base16 Default Dark
    Author:     Chris Kempson (http://chriskempson.com)

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-base16-dark.CodeMirror { background: #151515; color: #e0e0e0; }
.cm-s-base16-dark div.CodeMirror-selected { background: #303030; }
.cm-s-base16-dark .CodeMirror-line::selection, .cm-s-base16-dark .CodeMirror-line > span::selection, .cm-s-base16-dark .CodeMirror-line > span > span::selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-line::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span::-moz-selection, .cm-s-base16-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(48, 48, 48, .99); }
.cm-s-base16-dark .CodeMirror-gutters { background: #151515; border-right: 0px; }
.cm-s-base16-dark .CodeMirror-guttermarker { color: #ac4142; }
.cm-s-base16-dark .CodeMirror-guttermarker-subtle { color: #505050; }
.cm-s-base16-dark .CodeMirror-linenumber { color: #505050; }
.cm-s-base16-dark .CodeMirror-cursor { border-left: 1px solid #b0b0b0; }

.cm-s-base16-dark span.cm-comment { color: #8f5536; }
.cm-s-base16-dark span.cm-atom { color: #aa759f; }
.cm-s-base16-dark span.cm-number { color: #aa759f; }

.cm-s-base16-dark span.cm-property, .cm-s-base16-dark span.cm-attribute { color: #90a959; }
.cm-s-base16-dark span.cm-keyword { color: #ac4142; }
.cm-s-base16-dark span.cm-string { color: #f4bf75; }

.cm-s-base16-dark span.cm-variable { color: #90a959; }
.cm-s-base16-dark span.cm-variable-2 { color: #6a9fb5; }
.cm-s-base16-dark span.cm-def { color: #d28445; }
.cm-s-base16-dark span.cm-bracket { color: #e0e0e0; }
.cm-s-base16-dark span.cm-tag { color: #ac4142; }
.cm-s-base16-dark span.cm-link { color: #aa759f; }
.cm-s-base16-dark span.cm-error { background: #ac4142; color: #b0b0b0; }

.cm-s-base16-dark .CodeMirror-activeline-background { background: #202020; }
.cm-s-base16-dark .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       dracula
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original dracula color scheme by Zeno Rocha (https://github.com/zenorocha/dracula-theme)

*/


.cm-s-dracula.CodeMirror, .cm-s-dracula .CodeMirror-gutters {
  background-color: #282a36 !important;
  color: #f8f8f2 !important;
  border: none;
}
.cm-s-dracula .CodeMirror-gutters { color: #282a36; }
.cm-s-dracula .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-dracula .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-dracula .CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::selection, .cm-s-dracula .CodeMirror-line > span::selection, .cm-s-dracula .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula .CodeMirror-line::-moz-selection, .cm-s-dracula .CodeMirror-line > span::-moz-selection, .cm-s-dracula .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-dracula span.cm-comment { color: #6272a4; }
.cm-s-dracula span.cm-string, .cm-s-dracula span.cm-string-2 { color: #f1fa8c; }
.cm-s-dracula span.cm-number { color: #bd93f9; }
.cm-s-dracula span.cm-variable { color: #50fa7b; }
.cm-s-dracula span.cm-variable-2 { color: white; }
.cm-s-dracula span.cm-def { color: #50fa7b; }
.cm-s-dracula span.cm-operator { color: #ff79c6; }
.cm-s-dracula span.cm-keyword { color: #ff79c6; }
.cm-s-dracula span.cm-atom { color: #bd93f9; }
.cm-s-dracula span.cm-meta { color: #f8f8f2; }
.cm-s-dracula span.cm-tag { color: #ff79c6; }
.cm-s-dracula span.cm-attribute { color: #50fa7b; }
.cm-s-dracula span.cm-qualifier { color: #50fa7b; }
.cm-s-dracula span.cm-property { color: #66d9ef; }
.cm-s-dracula span.cm-builtin { color: #50fa7b; }
.cm-s-dracula span.cm-variable-3, .cm-s-dracula span.cm-type { color: #ffb86c; }

.cm-s-dracula .CodeMirror-activeline-background { background: rgba(255,255,255,0.1); }
.cm-s-dracula .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*

    Name:       Hopscotch
    Author:     Jan T. Sott

    CodeMirror template by Jan T. Sott (https://github.com/idleberg/base16-codemirror)
    Original Base16 color scheme by Chris Kempson (https://github.com/chriskempson/base16)

*/

.cm-s-hopscotch.CodeMirror {background: #322931; color: #d5d3d5;}
.cm-s-hopscotch div.CodeMirror-selected {background: #433b42 !important;}
.cm-s-hopscotch .CodeMirror-gutters {background: #322931; border-right: 0px;}
.cm-s-hopscotch .CodeMirror-linenumber {color: #797379;}
.cm-s-hopscotch .CodeMirror-cursor {border-left: 1px solid #989498 !important;}

.cm-s-hopscotch span.cm-comment {color: #b33508;}
.cm-s-hopscotch span.cm-atom {color: #c85e7c;}
.cm-s-hopscotch span.cm-number {color: #c85e7c;}

.cm-s-hopscotch span.cm-property, .cm-s-hopscotch span.cm-attribute {color: #8fc13e;}
.cm-s-hopscotch span.cm-keyword {color: #dd464c;}
.cm-s-hopscotch span.cm-string {color: #fdcc59;}

.cm-s-hopscotch span.cm-variable {color: #8fc13e;}
.cm-s-hopscotch span.cm-variable-2 {color: #1290bf;}
.cm-s-hopscotch span.cm-def {color: #fd8b19;}
.cm-s-hopscotch span.cm-error {background: #dd464c; color: #989498;}
.cm-s-hopscotch span.cm-bracket {color: #d5d3d5;}
.cm-s-hopscotch span.cm-tag {color: #dd464c;}
.cm-s-hopscotch span.cm-link {color: #c85e7c;}

.cm-s-hopscotch .CodeMirror-matchingbracket { text-decoration: underline; color: white !important;}
.cm-s-hopscotch .CodeMirror-activeline-background { background: #302020; }

/****************************************************************/
/*   Based on mbonaci's Brackets mbo theme                      */
/*   https://github.com/mbonaci/global/blob/master/Mbo.tmTheme  */
/*   Create your own: http://tmtheme-editor.herokuapp.com       */
/****************************************************************/

.cm-s-mbo.CodeMirror { background: #2c2c2c; color: #ffffec; }
.cm-s-mbo div.CodeMirror-selected { background: #716C62; }
.cm-s-mbo .CodeMirror-line::selection, .cm-s-mbo .CodeMirror-line > span::selection, .cm-s-mbo .CodeMirror-line > span > span::selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-line::-moz-selection, .cm-s-mbo .CodeMirror-line > span::-moz-selection, .cm-s-mbo .CodeMirror-line > span > span::-moz-selection { background: rgba(113, 108, 98, .99); }
.cm-s-mbo .CodeMirror-gutters { background: #4e4e4e; border-right: 0px; }
.cm-s-mbo .CodeMirror-guttermarker { color: white; }
.cm-s-mbo .CodeMirror-guttermarker-subtle { color: grey; }
.cm-s-mbo .CodeMirror-linenumber { color: #dadada; }
.cm-s-mbo .CodeMirror-cursor { border-left: 1px solid #ffffec; }

.cm-s-mbo span.cm-comment { color: #95958a; }
.cm-s-mbo span.cm-atom { color: #00a8c6; }
.cm-s-mbo span.cm-number { color: #00a8c6; }

.cm-s-mbo span.cm-property, .cm-s-mbo span.cm-attribute { color: #9ddfe9; }
.cm-s-mbo span.cm-keyword { color: #ffb928; }
.cm-s-mbo span.cm-string { color: #ffcf6c; }
.cm-s-mbo span.cm-string.cm-property { color: #ffffec; }

.cm-s-mbo span.cm-variable { color: #ffffec; }
.cm-s-mbo span.cm-variable-2 { color: #00a8c6; }
.cm-s-mbo span.cm-def { color: #ffffec; }
.cm-s-mbo span.cm-bracket { color: #fffffc; font-weight: bold; }
.cm-s-mbo span.cm-tag { color: #9ddfe9; }
.cm-s-mbo span.cm-link { color: #f54b07; }
.cm-s-mbo span.cm-error { border-bottom: #636363; color: #ffffec; }
.cm-s-mbo span.cm-qualifier { color: #ffffec; }

.cm-s-mbo .CodeMirror-activeline-background { background: #494b41; }
.cm-s-mbo .CodeMirror-matchingbracket { color: #ffb928 !important; }
.cm-s-mbo .CodeMirror-matchingtag { background: rgba(255, 255, 255, .37); }

/*
  MDN-LIKE Theme - Mozilla
  Ported to CodeMirror by Peter Kroon <plakroon@gmail.com>
  Report bugs/issues here: https://github.com/codemirror/CodeMirror/issues
  GitHub: @peterkroon

  The mdn-like theme is inspired on the displayed code examples at: https://developer.mozilla.org/en-US/docs/Web/CSS/animation

*/
.cm-s-mdn-like.CodeMirror { color: #999; background-color: #fff; }
.cm-s-mdn-like div.CodeMirror-selected { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::selection, .cm-s-mdn-like .CodeMirror-line > span::selection, .cm-s-mdn-like .CodeMirror-line > span > span::selection { background: #cfc; }
.cm-s-mdn-like .CodeMirror-line::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span::-moz-selection, .cm-s-mdn-like .CodeMirror-line > span > span::-moz-selection { background: #cfc; }

.cm-s-mdn-like .CodeMirror-gutters { background: #f8f8f8; border-left: 6px solid rgba(0,83,159,0.65); color: #333; }
.cm-s-mdn-like .CodeMirror-linenumber { color: #aaa; padding-left: 8px; }
.cm-s-mdn-like .CodeMirror-cursor { border-left: 2px solid #222; }

.cm-s-mdn-like .cm-keyword { color: #6262FF; }
.cm-s-mdn-like .cm-atom { color: #F90; }
.cm-s-mdn-like .cm-number { color:  #ca7841; }
.cm-s-mdn-like .cm-def { color: #8DA6CE; }
.cm-s-mdn-like span.cm-variable-2, .cm-s-mdn-like span.cm-tag { color: #690; }
.cm-s-mdn-like span.cm-variable-3, .cm-s-mdn-like span.cm-def, .cm-s-mdn-like span.cm-type { color: #07a; }

.cm-s-mdn-like .cm-variable { color: #07a; }
.cm-s-mdn-like .cm-property { color: #905; }
.cm-s-mdn-like .cm-qualifier { color: #690; }

.cm-s-mdn-like .cm-operator { color: #cda869; }
.cm-s-mdn-like .cm-comment { color:#777; font-weight:normal; }
.cm-s-mdn-like .cm-string { color:#07a; font-style:italic; }
.cm-s-mdn-like .cm-string-2 { color:#bd6b18; } /*?*/
.cm-s-mdn-like .cm-meta { color: #000; } /*?*/
.cm-s-mdn-like .cm-builtin { color: #9B7536; } /*?*/
.cm-s-mdn-like .cm-tag { color: #997643; }
.cm-s-mdn-like .cm-attribute { color: #d6bb6d; } /*?*/
.cm-s-mdn-like .cm-header { color: #FF6400; }
.cm-s-mdn-like .cm-hr { color: #AEAEAE; }
.cm-s-mdn-like .cm-link { color:#ad9361; font-style:italic; text-decoration:none; }
.cm-s-mdn-like .cm-error { border-bottom: 1px solid red; }

div.cm-s-mdn-like .CodeMirror-activeline-background { background: #efefff; }
div.cm-s-mdn-like span.CodeMirror-matchingbracket { outline:1px solid grey; color: inherit; }

.cm-s-mdn-like.CodeMirror { background-image: url(data:image/png;base64,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); }

/*

    Name:       seti
    Author:     Michael Kaminsky (http://github.com/mkaminsky11)

    Original seti color scheme by Jesse Weed (https://github.com/jesseweed/seti-syntax)

*/


.cm-s-seti.CodeMirror {
  background-color: #151718 !important;
  color: #CFD2D1 !important;
  border: none;
}
.cm-s-seti .CodeMirror-gutters {
  color: #404b53;
  background-color: #0E1112;
  border: none;
}
.cm-s-seti .CodeMirror-cursor { border-left: solid thin #f8f8f0; }
.cm-s-seti .CodeMirror-linenumber { color: #6D8A88; }
.cm-s-seti.CodeMirror-focused div.CodeMirror-selected { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::selection, .cm-s-seti .CodeMirror-line > span::selection, .cm-s-seti .CodeMirror-line > span > span::selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti .CodeMirror-line::-moz-selection, .cm-s-seti .CodeMirror-line > span::-moz-selection, .cm-s-seti .CodeMirror-line > span > span::-moz-selection { background: rgba(255, 255, 255, 0.10); }
.cm-s-seti span.cm-comment { color: #41535b; }
.cm-s-seti span.cm-string, .cm-s-seti span.cm-string-2 { color: #55b5db; }
.cm-s-seti span.cm-number { color: #cd3f45; }
.cm-s-seti span.cm-variable { color: #55b5db; }
.cm-s-seti span.cm-variable-2 { color: #a074c4; }
.cm-s-seti span.cm-def { color: #55b5db; }
.cm-s-seti span.cm-keyword { color: #ff79c6; }
.cm-s-seti span.cm-operator { color: #9fca56; }
.cm-s-seti span.cm-keyword { color: #e6cd69; }
.cm-s-seti span.cm-atom { color: #cd3f45; }
.cm-s-seti span.cm-meta { color: #55b5db; }
.cm-s-seti span.cm-tag { color: #55b5db; }
.cm-s-seti span.cm-attribute { color: #9fca56; }
.cm-s-seti span.cm-qualifier { color: #9fca56; }
.cm-s-seti span.cm-property { color: #a074c4; }
.cm-s-seti span.cm-variable-3, .cm-s-seti span.cm-type { color: #9fca56; }
.cm-s-seti span.cm-builtin { color: #9fca56; }
.cm-s-seti .CodeMirror-activeline-background { background: #101213; }
.cm-s-seti .CodeMirror-matchingbracket { text-decoration: underline; color: white !important; }

/*
Solarized theme for code-mirror
http://ethanschoonover.com/solarized
*/

/*
Solarized color palette
http://ethanschoonover.com/solarized/img/solarized-palette.png
*/

.solarized.base03 { color: #002b36; }
.solarized.base02 { color: #073642; }
.solarized.base01 { color: #586e75; }
.solarized.base00 { color: #657b83; }
.solarized.base0 { color: #839496; }
.solarized.base1 { color: #93a1a1; }
.solarized.base2 { color: #eee8d5; }
.solarized.base3  { color: #fdf6e3; }
.solarized.solar-yellow  { color: #b58900; }
.solarized.solar-orange  { color: #cb4b16; }
.solarized.solar-red { color: #dc322f; }
.solarized.solar-magenta { color: #d33682; }
.solarized.solar-violet  { color: #6c71c4; }
.solarized.solar-blue { color: #268bd2; }
.solarized.solar-cyan { color: #2aa198; }
.solarized.solar-green { color: #859900; }

/* Color scheme for code-mirror */

.cm-s-solarized {
  line-height: 1.45em;
  color-profile: sRGB;
  rendering-intent: auto;
}
.cm-s-solarized.cm-s-dark {
  color: #839496;
  background-color: #002b36;
  text-shadow: #002b36 0 1px;
}
.cm-s-solarized.cm-s-light {
  background-color: #fdf6e3;
  color: #657b83;
  text-shadow: #eee8d5 0 1px;
}

.cm-s-solarized .CodeMirror-widget {
  text-shadow: none;
}

.cm-s-solarized .cm-header { color: #586e75; }
.cm-s-solarized .cm-quote { color: #93a1a1; }

.cm-s-solarized .cm-keyword { color: #cb4b16; }
.cm-s-solarized .cm-atom { color: #d33682; }
.cm-s-solarized .cm-number { color: #d33682; }
.cm-s-solarized .cm-def { color: #2aa198; }

.cm-s-solarized .cm-variable { color: #839496; }
.cm-s-solarized .cm-variable-2 { color: #b58900; }
.cm-s-solarized .cm-variable-3, .cm-s-solarized .cm-type { color: #6c71c4; }

.cm-s-solarized .cm-property { color: #2aa198; }
.cm-s-solarized .cm-operator { color: #6c71c4; }

.cm-s-solarized .cm-comment { color: #586e75; font-style:italic; }

.cm-s-solarized .cm-string { color: #859900; }
.cm-s-solarized .cm-string-2 { color: #b58900; }

.cm-s-solarized .cm-meta { color: #859900; }
.cm-s-solarized .cm-qualifier { color: #b58900; }
.cm-s-solarized .cm-builtin { color: #d33682; }
.cm-s-solarized .cm-bracket { color: #cb4b16; }
.cm-s-solarized .CodeMirror-matchingbracket { color: #859900; }
.cm-s-solarized .CodeMirror-nonmatchingbracket { color: #dc322f; }
.cm-s-solarized .cm-tag { color: #93a1a1; }
.cm-s-solarized .cm-attribute { color: #2aa198; }
.cm-s-solarized .cm-hr {
  color: transparent;
  border-top: 1px solid #586e75;
  display: block;
}
.cm-s-solarized .cm-link { color: #93a1a1; cursor: pointer; }
.cm-s-solarized .cm-special { color: #6c71c4; }
.cm-s-solarized .cm-em {
  color: #999;
  text-decoration: underline;
  text-decoration-style: dotted;
}
.cm-s-solarized .cm-error,
.cm-s-solarized .cm-invalidchar {
  color: #586e75;
  border-bottom: 1px dotted #dc322f;
}

.cm-s-solarized.cm-s-dark div.CodeMirror-selected { background: #073642; }
.cm-s-solarized.cm-s-dark.CodeMirror ::selection { background: rgba(7, 54, 66, 0.99); }
.cm-s-solarized.cm-s-dark .CodeMirror-line::-moz-selection, .cm-s-dark .CodeMirror-line > span::-moz-selection, .cm-s-dark .CodeMirror-line > span > span::-moz-selection { background: rgba(7, 54, 66, 0.99); }

.cm-s-solarized.cm-s-light div.CodeMirror-selected { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::selection, .cm-s-light .CodeMirror-line > span::selection, .cm-s-light .CodeMirror-line > span > span::selection { background: #eee8d5; }
.cm-s-solarized.cm-s-light .CodeMirror-line::-moz-selection, .cm-s-ligh .CodeMirror-line > span::-moz-selection, .cm-s-ligh .CodeMirror-line > span > span::-moz-selection { background: #eee8d5; }

/* Editor styling */



/* Little shadow on the view-port of the buffer view */
.cm-s-solarized.CodeMirror {
  -moz-box-shadow: inset 7px 0 12px -6px #000;
  -webkit-box-shadow: inset 7px 0 12px -6px #000;
  box-shadow: inset 7px 0 12px -6px #000;
}

/* Remove gutter border */
.cm-s-solarized .CodeMirror-gutters {
  border-right: 0;
}

/* Gutter colors and line number styling based of color scheme (dark / light) */

/* Dark */
.cm-s-solarized.cm-s-dark .CodeMirror-gutters {
  background-color: #073642;
}

.cm-s-solarized.cm-s-dark .CodeMirror-linenumber {
  color: #586e75;
  text-shadow: #021014 0 -1px;
}

/* Light */
.cm-s-solarized.cm-s-light .CodeMirror-gutters {
  background-color: #eee8d5;
}

.cm-s-solarized.cm-s-light .CodeMirror-linenumber {
  color: #839496;
}

/* Common */
.cm-s-solarized .CodeMirror-linenumber {
  padding: 0 5px;
}
.cm-s-solarized .CodeMirror-guttermarker-subtle { color: #586e75; }
.cm-s-solarized.cm-s-dark .CodeMirror-guttermarker { color: #ddd; }
.cm-s-solarized.cm-s-light .CodeMirror-guttermarker { color: #cb4b16; }

.cm-s-solarized .CodeMirror-gutter .CodeMirror-gutter-text {
  color: #586e75;
}

/* Cursor */
.cm-s-solarized .CodeMirror-cursor { border-left: 1px solid #819090; }

/* Fat cursor */
.cm-s-solarized.cm-s-light.cm-fat-cursor .CodeMirror-cursor { background: #77ee77; }
.cm-s-solarized.cm-s-light .cm-animate-fat-cursor { background-color: #77ee77; }
.cm-s-solarized.cm-s-dark.cm-fat-cursor .CodeMirror-cursor { background: #586e75; }
.cm-s-solarized.cm-s-dark .cm-animate-fat-cursor { background-color: #586e75; }

/* Active line */
.cm-s-solarized.cm-s-dark .CodeMirror-activeline-background {
  background: rgba(255, 255, 255, 0.06);
}
.cm-s-solarized.cm-s-light .CodeMirror-activeline-background {
  background: rgba(0, 0, 0, 0.06);
}

.cm-s-the-matrix.CodeMirror { background: #000000; color: #00FF00; }
.cm-s-the-matrix div.CodeMirror-selected { background: #2D2D2D; }
.cm-s-the-matrix .CodeMirror-line::selection, .cm-s-the-matrix .CodeMirror-line > span::selection, .cm-s-the-matrix .CodeMirror-line > span > span::selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-line::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span::-moz-selection, .cm-s-the-matrix .CodeMirror-line > span > span::-moz-selection { background: rgba(45, 45, 45, 0.99); }
.cm-s-the-matrix .CodeMirror-gutters { background: #060; border-right: 2px solid #00FF00; }
.cm-s-the-matrix .CodeMirror-guttermarker { color: #0f0; }
.cm-s-the-matrix .CodeMirror-guttermarker-subtle { color: white; }
.cm-s-the-matrix .CodeMirror-linenumber { color: #FFFFFF; }
.cm-s-the-matrix .CodeMirror-cursor { border-left: 1px solid #00FF00; }

.cm-s-the-matrix span.cm-keyword { color: #008803; font-weight: bold; }
.cm-s-the-matrix span.cm-atom { color: #3FF; }
.cm-s-the-matrix span.cm-number { color: #FFB94F; }
.cm-s-the-matrix span.cm-def { color: #99C; }
.cm-s-the-matrix span.cm-variable { color: #F6C; }
.cm-s-the-matrix span.cm-variable-2 { color: #C6F; }
.cm-s-the-matrix span.cm-variable-3, .cm-s-the-matrix span.cm-type { color: #96F; }
.cm-s-the-matrix span.cm-property { color: #62FFA0; }
.cm-s-the-matrix span.cm-operator { color: #999; }
.cm-s-the-matrix span.cm-comment { color: #CCCCCC; }
.cm-s-the-matrix span.cm-string { color: #39C; }
.cm-s-the-matrix span.cm-meta { color: #C9F; }
.cm-s-the-matrix span.cm-qualifier { color: #FFF700; }
.cm-s-the-matrix span.cm-builtin { color: #30a; }
.cm-s-the-matrix span.cm-bracket { color: #cc7; }
.cm-s-the-matrix span.cm-tag { color: #FFBD40; }
.cm-s-the-matrix span.cm-attribute { color: #FFF700; }
.cm-s-the-matrix span.cm-error { color: #FF0000; }

.cm-s-the-matrix .CodeMirror-activeline-background { background: #040; }

/*
Copyright (C) 2011 by MarkLogic Corporation
Author: Mike Brevoort <mike@brevoort.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
*/
.cm-s-xq-light span.cm-keyword { line-height: 1em; font-weight: bold; color: #5A5CAD; }
.cm-s-xq-light span.cm-atom { color: #6C8CD5; }
.cm-s-xq-light span.cm-number { color: #164; }
.cm-s-xq-light span.cm-def { text-decoration:underline; }
.cm-s-xq-light span.cm-variable { color: black; }
.cm-s-xq-light span.cm-variable-2 { color:black; }
.cm-s-xq-light span.cm-variable-3, .cm-s-xq-light span.cm-type { color: black; }
.cm-s-xq-light span.cm-property {}
.cm-s-xq-light span.cm-operator {}
.cm-s-xq-light span.cm-comment { color: #0080FF; font-style: italic; }
.cm-s-xq-light span.cm-string { color: red; }
.cm-s-xq-light span.cm-meta { color: yellow; }
.cm-s-xq-light span.cm-qualifier { color: grey; }
.cm-s-xq-light span.cm-builtin { color: #7EA656; }
.cm-s-xq-light span.cm-bracket { color: #cc7; }
.cm-s-xq-light span.cm-tag { color: #3F7F7F; }
.cm-s-xq-light span.cm-attribute { color: #7F007F; }
.cm-s-xq-light span.cm-error { color: #f00; }

.cm-s-xq-light .CodeMirror-activeline-background { background: #e8f2ff; }
.cm-s-xq-light .CodeMirror-matchingbracket { outline:1px solid grey;color:black !important;background:yellow; }

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.CodeMirror {
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  border: 0;
  border-radius: 0;
  height: auto;
  /* Changed to auto to autogrow */
}

.CodeMirror pre {
  padding: 0 var(--jp-code-padding);
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-dialog {
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* This causes https://github.com/jupyter/jupyterlab/issues/522 */
/* May not cause it not because we changed it! */
.CodeMirror-lines {
  padding: var(--jp-code-padding) 0;
}

.CodeMirror-linenumber {
  padding: 0 8px;
}

.jp-CodeMirrorEditor-static {
  margin: var(--jp-code-padding);
}

.jp-CodeMirrorEditor,
.jp-CodeMirrorEditor-static {
  cursor: text;
}

.jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}

/* When zoomed out 67% and 33% on a screen of 1440 width x 900 height */
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width1) solid
      var(--jp-editor-cursor-color);
  }
}

/* When zoomed out less than 33% */
@media screen and (min-width: 4320px) {
  .jp-CodeMirrorEditor[data-type='inline'] .CodeMirror-cursor {
    border-left: var(--jp-code-cursor-width2) solid
      var(--jp-editor-cursor-color);
  }
}

.CodeMirror.jp-mod-readOnly .CodeMirror-cursor {
  display: none;
}

.CodeMirror-gutters {
  border-right: 1px solid var(--jp-border-color2);
  background-color: var(--jp-layout-color0);
}

.jp-CollaboratorCursor {
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-top: none;
  border-bottom: 3px solid;
  background-clip: content-box;
  margin-left: -5px;
  margin-right: -5px;
}

.CodeMirror-selectedtext.cm-searching {
  background-color: var(--jp-search-selected-match-background-color) !important;
  color: var(--jp-search-selected-match-color) !important;
}

.cm-searching {
  background-color: var(
    --jp-search-unselected-match-background-color
  ) !important;
  color: var(--jp-search-unselected-match-color) !important;
}

.CodeMirror-focused .CodeMirror-selected {
  background-color: var(--jp-editor-selected-focused-background);
}

.CodeMirror-selected {
  background-color: var(--jp-editor-selected-background);
}

.jp-CollaboratorCursor-hover {
  position: absolute;
  z-index: 1;
  transform: translateX(-50%);
  color: white;
  border-radius: 3px;
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 1px;
  padding-bottom: 1px;
  text-align: center;
  font-size: var(--jp-ui-font-size1);
  white-space: nowrap;
}

.jp-CodeMirror-ruler {
  border-left: 1px dashed var(--jp-border-color2);
}

/**
 * Here is our jupyter theme for CodeMirror syntax highlighting
 * This is used in our marked.js syntax highlighting and CodeMirror itself
 * The string "jupyter" is set in ../codemirror/widget.DEFAULT_CODEMIRROR_THEME
 * This came from the classic notebook, which came form highlight.js/GitHub
 */

/**
 * CodeMirror themes are handling the background/color in this way. This works
 * fine for CodeMirror editors outside the notebook, but the notebook styles
 * these things differently.
 */
.CodeMirror.cm-s-jupyter {
  background: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
}

/* In the notebook, we want this styling to be handled by its container */
.jp-CodeConsole .CodeMirror.cm-s-jupyter,
.jp-Notebook .CodeMirror.cm-s-jupyter {
  background: transparent;
}

.cm-s-jupyter .CodeMirror-cursor {
  border-left: var(--jp-code-cursor-width0) solid var(--jp-editor-cursor-color);
}
.cm-s-jupyter span.cm-keyword {
  color: var(--jp-mirror-editor-keyword-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-atom {
  color: var(--jp-mirror-editor-atom-color);
}
.cm-s-jupyter span.cm-number {
  color: var(--jp-mirror-editor-number-color);
}
.cm-s-jupyter span.cm-def {
  color: var(--jp-mirror-editor-def-color);
}
.cm-s-jupyter span.cm-variable {
  color: var(--jp-mirror-editor-variable-color);
}
.cm-s-jupyter span.cm-variable-2 {
  color: var(--jp-mirror-editor-variable-2-color);
}
.cm-s-jupyter span.cm-variable-3 {
  color: var(--jp-mirror-editor-variable-3-color);
}
.cm-s-jupyter span.cm-punctuation {
  color: var(--jp-mirror-editor-punctuation-color);
}
.cm-s-jupyter span.cm-property {
  color: var(--jp-mirror-editor-property-color);
}
.cm-s-jupyter span.cm-operator {
  color: var(--jp-mirror-editor-operator-color);
  font-weight: bold;
}
.cm-s-jupyter span.cm-comment {
  color: var(--jp-mirror-editor-comment-color);
  font-style: italic;
}
.cm-s-jupyter span.cm-string {
  color: var(--jp-mirror-editor-string-color);
}
.cm-s-jupyter span.cm-string-2 {
  color: var(--jp-mirror-editor-string-2-color);
}
.cm-s-jupyter span.cm-meta {
  color: var(--jp-mirror-editor-meta-color);
}
.cm-s-jupyter span.cm-qualifier {
  color: var(--jp-mirror-editor-qualifier-color);
}
.cm-s-jupyter span.cm-builtin {
  color: var(--jp-mirror-editor-builtin-color);
}
.cm-s-jupyter span.cm-bracket {
  color: var(--jp-mirror-editor-bracket-color);
}
.cm-s-jupyter span.cm-tag {
  color: var(--jp-mirror-editor-tag-color);
}
.cm-s-jupyter span.cm-attribute {
  color: var(--jp-mirror-editor-attribute-color);
}
.cm-s-jupyter span.cm-header {
  color: var(--jp-mirror-editor-header-color);
}
.cm-s-jupyter span.cm-quote {
  color: var(--jp-mirror-editor-quote-color);
}
.cm-s-jupyter span.cm-link {
  color: var(--jp-mirror-editor-link-color);
}
.cm-s-jupyter span.cm-error {
  color: var(--jp-mirror-editor-error-color);
}
.cm-s-jupyter span.cm-hr {
  color: #999;
}

.cm-s-jupyter span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}

.cm-s-jupyter .CodeMirror-activeline-background,
.cm-s-jupyter .CodeMirror-gutter {
  background-color: var(--jp-layout-color2);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

.jp-RenderedText {
  text-align: left;
  padding-left: var(--jp-code-padding);
  line-height: var(--jp-code-line-height);
  font-family: var(--jp-code-font-family);
}

.jp-RenderedText pre,
.jp-RenderedJavaScript pre,
.jp-RenderedHTMLCommon pre {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-code-font-size);
  border: none;
  margin: 0px;
  padding: 0px;
  line-height: normal;
}

.jp-RenderedText pre a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}
.jp-RenderedText pre a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* console foregrounds and backgrounds */
.jp-RenderedText pre .ansi-black-fg {
  color: #3e424d;
}
.jp-RenderedText pre .ansi-red-fg {
  color: #e75c58;
}
.jp-RenderedText pre .ansi-green-fg {
  color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-fg {
  color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-fg {
  color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-fg {
  color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-fg {
  color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-fg {
  color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-bg {
  background-color: #3e424d;
}
.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
}
.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
}
.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
}
.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
}
.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
}
.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
}
.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
}

.jp-RenderedText pre .ansi-black-intense-fg {
  color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-fg {
  color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-fg {
  color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-fg {
  color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-fg {
  color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-fg {
  color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-fg {
  color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-fg {
  color: #a1a6b2;
}

.jp-RenderedText pre .ansi-black-intense-bg {
  background-color: #282c36;
}
.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
}
.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
}
.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
}
.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
}
.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
}
.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
}
.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}
.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
}

.jp-RenderedText pre .ansi-bold {
  font-weight: bold;
}
.jp-RenderedText pre .ansi-underline {
  text-decoration: underline;
}

.jp-RenderedText[data-mime-type='application/vnd.jupyter.stderr'] {
  background: var(--jp-rendermime-error-background);
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| RenderedLatex
|----------------------------------------------------------------------------*/

.jp-RenderedLatex {
  color: var(--jp-content-font-color1);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
}

/* Left-justify outputs.*/
.jp-OutputArea-output.jp-RenderedLatex {
  padding: var(--jp-code-padding);
  text-align: left;
}

/*-----------------------------------------------------------------------------
| RenderedHTML
|----------------------------------------------------------------------------*/

.jp-RenderedHTMLCommon {
  color: var(--jp-content-font-color1);
  font-family: var(--jp-content-font-family);
  font-size: var(--jp-content-font-size1);
  line-height: var(--jp-content-line-height);
  /* Give a bit more R padding on Markdown text to keep line lengths reasonable */
  padding-right: 20px;
}

.jp-RenderedHTMLCommon em {
  font-style: italic;
}

.jp-RenderedHTMLCommon strong {
  font-weight: bold;
}

.jp-RenderedHTMLCommon u {
  text-decoration: underline;
}

.jp-RenderedHTMLCommon a:link {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:hover {
  text-decoration: underline;
  color: var(--jp-content-link-color);
}

.jp-RenderedHTMLCommon a:visited {
  text-decoration: none;
  color: var(--jp-content-link-color);
}

/* Headings */

.jp-RenderedHTMLCommon h1,
.jp-RenderedHTMLCommon h2,
.jp-RenderedHTMLCommon h3,
.jp-RenderedHTMLCommon h4,
.jp-RenderedHTMLCommon h5,
.jp-RenderedHTMLCommon h6 {
  line-height: var(--jp-content-heading-line-height);
  font-weight: var(--jp-content-heading-font-weight);
  font-style: normal;
  margin: var(--jp-content-heading-margin-top) 0
    var(--jp-content-heading-margin-bottom) 0;
}

.jp-RenderedHTMLCommon h1:first-child,
.jp-RenderedHTMLCommon h2:first-child,
.jp-RenderedHTMLCommon h3:first-child,
.jp-RenderedHTMLCommon h4:first-child,
.jp-RenderedHTMLCommon h5:first-child,
.jp-RenderedHTMLCommon h6:first-child {
  margin-top: calc(0.5 * var(--jp-content-heading-margin-top));
}

.jp-RenderedHTMLCommon h1:last-child,
.jp-RenderedHTMLCommon h2:last-child,
.jp-RenderedHTMLCommon h3:last-child,
.jp-RenderedHTMLCommon h4:last-child,
.jp-RenderedHTMLCommon h5:last-child,
.jp-RenderedHTMLCommon h6:last-child {
  margin-bottom: calc(0.5 * var(--jp-content-heading-margin-bottom));
}

.jp-RenderedHTMLCommon h1 {
  font-size: var(--jp-content-font-size5);
}

.jp-RenderedHTMLCommon h2 {
  font-size: var(--jp-content-font-size4);
}

.jp-RenderedHTMLCommon h3 {
  font-size: var(--jp-content-font-size3);
}

.jp-RenderedHTMLCommon h4 {
  font-size: var(--jp-content-font-size2);
}

.jp-RenderedHTMLCommon h5 {
  font-size: var(--jp-content-font-size1);
}

.jp-RenderedHTMLCommon h6 {
  font-size: var(--jp-content-font-size0);
}

/* Lists */

.jp-RenderedHTMLCommon ul:not(.list-inline),
.jp-RenderedHTMLCommon ol:not(.list-inline) {
  padding-left: 2em;
}

.jp-RenderedHTMLCommon ul {
  list-style: disc;
}

.jp-RenderedHTMLCommon ul ul {
  list-style: square;
}

.jp-RenderedHTMLCommon ul ul ul {
  list-style: circle;
}

.jp-RenderedHTMLCommon ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol ol {
  list-style: upper-alpha;
}

.jp-RenderedHTMLCommon ol ol ol {
  list-style: lower-alpha;
}

.jp-RenderedHTMLCommon ol ol ol ol {
  list-style: lower-roman;
}

.jp-RenderedHTMLCommon ol ol ol ol ol {
  list-style: decimal;
}

.jp-RenderedHTMLCommon ol,
.jp-RenderedHTMLCommon ul {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon ul ul,
.jp-RenderedHTMLCommon ul ol,
.jp-RenderedHTMLCommon ol ul,
.jp-RenderedHTMLCommon ol ol {
  margin-bottom: 0em;
}

.jp-RenderedHTMLCommon hr {
  color: var(--jp-border-color2);
  background-color: var(--jp-border-color1);
  margin-top: 1em;
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon > pre {
  margin: 1.5em 2em;
}

.jp-RenderedHTMLCommon pre,
.jp-RenderedHTMLCommon code {
  border: 0;
  background-color: var(--jp-layout-color0);
  color: var(--jp-content-font-color1);
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  line-height: var(--jp-code-line-height);
  padding: 0;
  white-space: pre-wrap;
}

.jp-RenderedHTMLCommon :not(pre) > code {
  background-color: var(--jp-layout-color2);
  padding: 1px 5px;
}

/* Tables */

.jp-RenderedHTMLCommon table {
  border-collapse: collapse;
  border-spacing: 0;
  border: none;
  color: var(--jp-ui-font-color1);
  font-size: 12px;
  table-layout: fixed;
  margin-left: auto;
  margin-right: auto;
}

.jp-RenderedHTMLCommon thead {
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  vertical-align: bottom;
}

.jp-RenderedHTMLCommon td,
.jp-RenderedHTMLCommon th,
.jp-RenderedHTMLCommon tr {
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}

.jp-RenderedMarkdown.jp-RenderedHTMLCommon td,
.jp-RenderedMarkdown.jp-RenderedHTMLCommon th {
  max-width: none;
}

:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon td,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon th,
:not(.jp-RenderedMarkdown).jp-RenderedHTMLCommon tr {
  text-align: right;
}

.jp-RenderedHTMLCommon th {
  font-weight: bold;
}

.jp-RenderedHTMLCommon tbody tr:nth-child(odd) {
  background: var(--jp-layout-color0);
}

.jp-RenderedHTMLCommon tbody tr:nth-child(even) {
  background: var(--jp-rendermime-table-row-background);
}

.jp-RenderedHTMLCommon tbody tr:hover {
  background: var(--jp-rendermime-table-row-hover-background);
}

.jp-RenderedHTMLCommon table {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon p {
  text-align: left;
  margin: 0px;
}

.jp-RenderedHTMLCommon p {
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon img {
  -moz-force-broken-image-icon: 1;
}

/* Restrict to direct children as other images could be nested in other content. */
.jp-RenderedHTMLCommon > img {
  display: block;
  margin-left: 0;
  margin-right: 0;
  margin-bottom: 1em;
}

/* Change color behind transparent images if they need it... */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-light-background {
  background-color: var(--jp-inverse-layout-color1);
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-dark-background {
  background-color: var(--jp-inverse-layout-color1);
}
/* ...or leave it untouched if they don't */
[data-jp-theme-light='false'] .jp-RenderedImage img.jp-needs-dark-background {
}
[data-jp-theme-light='true'] .jp-RenderedImage img.jp-needs-light-background {
}

.jp-RenderedHTMLCommon img,
.jp-RenderedImage img,
.jp-RenderedHTMLCommon svg,
.jp-RenderedSVG svg {
  max-width: 100%;
  height: auto;
}

.jp-RenderedHTMLCommon img.jp-mod-unconfined,
.jp-RenderedImage img.jp-mod-unconfined,
.jp-RenderedHTMLCommon svg.jp-mod-unconfined,
.jp-RenderedSVG svg.jp-mod-unconfined {
  max-width: none;
}

.jp-RenderedHTMLCommon .alert {
  padding: var(--jp-notebook-padding);
  border: var(--jp-border-width) solid transparent;
  border-radius: var(--jp-border-radius);
  margin-bottom: 1em;
}

.jp-RenderedHTMLCommon .alert-info {
  color: var(--jp-info-color0);
  background-color: var(--jp-info-color3);
  border-color: var(--jp-info-color2);
}
.jp-RenderedHTMLCommon .alert-info hr {
  border-color: var(--jp-info-color3);
}
.jp-RenderedHTMLCommon .alert-info > p:last-child,
.jp-RenderedHTMLCommon .alert-info > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-warning {
  color: var(--jp-warn-color0);
  background-color: var(--jp-warn-color3);
  border-color: var(--jp-warn-color2);
}
.jp-RenderedHTMLCommon .alert-warning hr {
  border-color: var(--jp-warn-color3);
}
.jp-RenderedHTMLCommon .alert-warning > p:last-child,
.jp-RenderedHTMLCommon .alert-warning > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-success {
  color: var(--jp-success-color0);
  background-color: var(--jp-success-color3);
  border-color: var(--jp-success-color2);
}
.jp-RenderedHTMLCommon .alert-success hr {
  border-color: var(--jp-success-color3);
}
.jp-RenderedHTMLCommon .alert-success > p:last-child,
.jp-RenderedHTMLCommon .alert-success > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon .alert-danger {
  color: var(--jp-error-color0);
  background-color: var(--jp-error-color3);
  border-color: var(--jp-error-color2);
}
.jp-RenderedHTMLCommon .alert-danger hr {
  border-color: var(--jp-error-color3);
}
.jp-RenderedHTMLCommon .alert-danger > p:last-child,
.jp-RenderedHTMLCommon .alert-danger > ul:last-child {
  margin-bottom: 0;
}

.jp-RenderedHTMLCommon blockquote {
  margin: 1em 2em;
  padding: 0 1em;
  border-left: 5px solid var(--jp-border-color2);
}

a.jp-InternalAnchorLink {
  visibility: hidden;
  margin-left: 8px;
  color: var(--md-blue-800);
}

h1:hover .jp-InternalAnchorLink,
h2:hover .jp-InternalAnchorLink,
h3:hover .jp-InternalAnchorLink,
h4:hover .jp-InternalAnchorLink,
h5:hover .jp-InternalAnchorLink,
h6:hover .jp-InternalAnchorLink {
  visibility: visible;
}

.jp-RenderedHTMLCommon kbd {
  background-color: var(--jp-rendermime-table-row-background);
  border: 1px solid var(--jp-border-color0);
  border-bottom-color: var(--jp-border-color2);
  border-radius: 3px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
  display: inline-block;
  font-size: 0.8em;
  line-height: 1em;
  padding: 0.2em 0.5em;
}

/* Most direct children of .jp-RenderedHTMLCommon have a margin-bottom of 1.0.
 * At the bottom of cells this is a bit too much as there is also spacing
 * between cells. Going all the way to 0 gets too tight between markdown and
 * code cells.
 */
.jp-RenderedHTMLCommon > *:last-child {
  margin-bottom: 0.5em;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-MimeDocument {
  outline: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-filebrowser-button-height: 28px;
  --jp-private-filebrowser-button-width: 48px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-FileBrowser {
  display: flex;
  flex-direction: column;
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
   * relative to this base size */
  font-size: var(--jp-ui-font-size1);
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  border-bottom: none;
  height: auto;
  margin: var(--jp-toolbar-header-margin);
  box-shadow: none;
}

.jp-BreadCrumbs {
  flex: 0 0 auto;
  margin: 4px 12px;
}

.jp-BreadCrumbs-item {
  margin: 0px 2px;
  padding: 0px 2px;
  border-radius: var(--jp-border-radius);
  cursor: pointer;
}

.jp-BreadCrumbs-item:hover {
  background-color: var(--jp-layout-color2);
}

.jp-BreadCrumbs-item:first-child {
  margin-left: 0px;
}

.jp-BreadCrumbs-item.jp-mod-dropTarget {
  background-color: var(--jp-brand-color2);
  opacity: 0.7;
}

/*-----------------------------------------------------------------------------
| Buttons
|----------------------------------------------------------------------------*/

.jp-FileBrowser-toolbar.jp-Toolbar {
  padding: 0px;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  justify-content: space-evenly;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-Toolbar-item {
  flex: 1;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-ToolbarButtonComponent {
  width: 100%;
}

/*-----------------------------------------------------------------------------
| DirListing
|----------------------------------------------------------------------------*/

.jp-DirListing {
  flex: 1 1 auto;
  display: flex;
  flex-direction: column;
  outline: 0;
}

.jp-DirListing-header {
  flex: 0 0 auto;
  display: flex;
  flex-direction: row;
  overflow: hidden;
  border-top: var(--jp-border-width) solid var(--jp-border-color2);
  border-bottom: var(--jp-border-width) solid var(--jp-border-color1);
  box-shadow: var(--jp-toolbar-box-shadow);
  z-index: 2;
}

.jp-DirListing-headerItem {
  padding: 4px 12px 2px 12px;
  font-weight: 500;
}

.jp-DirListing-headerItem:hover {
  background: var(--jp-layout-color2);
}

.jp-DirListing-headerItem.jp-id-name {
  flex: 1 0 84px;
}

.jp-DirListing-headerItem.jp-id-modified {
  flex: 0 0 112px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
}

.jp-DirListing-narrow .jp-id-modified,
.jp-DirListing-narrow .jp-DirListing-itemModified {
  display: none;
}

.jp-DirListing-headerItem.jp-mod-selected {
  font-weight: 600;
}

/* increase specificity to override bundled default */
.jp-DirListing-content {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

/* Style the directory listing content when a user drops a file to upload */
.jp-DirListing.jp-mod-native-drop .jp-DirListing-content {
  outline: 5px dashed rgba(128, 128, 128, 0.5);
  outline-offset: -10px;
  cursor: copy;
}

.jp-DirListing-item {
  display: flex;
  flex-direction: row;
  padding: 4px 12px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-DirListing-item.jp-mod-selected {
  color: white;
  background: var(--jp-brand-color1);
}

.jp-DirListing-item.jp-mod-dropTarget {
  background: var(--jp-brand-color3);
}

.jp-DirListing-item:hover:not(.jp-mod-selected) {
  background: var(--jp-layout-color2);
}

.jp-DirListing-itemIcon {
  flex: 0 0 20px;
  margin-right: 4px;
}

.jp-DirListing-itemText {
  flex: 1 0 64px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  user-select: none;
}

.jp-DirListing-itemModified {
  flex: 0 0 125px;
  text-align: right;
}

.jp-DirListing-editor {
  flex: 1 0 64px;
  outline: none;
  border: none;
}

.jp-DirListing-item.jp-mod-running .jp-DirListing-itemIcon:before {
  color: limegreen;
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.lm-mod-drag-image,
.jp-DirListing-item.jp-mod-selected.lm-mod-drag-image {
  font-size: var(--jp-ui-font-size1);
  padding-left: 4px;
  margin-left: 4px;
  width: 160px;
  background-color: var(--jp-ui-inverse-font-color2);
  box-shadow: var(--jp-elevation-z2);
  border-radius: 0px;
  color: var(--jp-ui-font-color1);
  transform: translateX(-40%) translateY(-58%);
}

.jp-DirListing-deadSpace {
  flex: 1 1 auto;
  margin: 0;
  padding: 0;
  list-style-type: none;
  overflow: auto;
  background-color: var(--jp-layout-color1);
}

.jp-Document {
  min-width: 120px;
  min-height: 120px;
  outline: none;
}

.jp-FileDialog.jp-mod-conflict input {
  color: red;
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
}

/*-----------------------------------------------------------------------------
| Main OutputArea
| OutputArea has a list of Outputs
|----------------------------------------------------------------------------*/

.jp-OutputArea {
  overflow-y: auto;
}

.jp-OutputArea-child {
  display: flex;
  flex-direction: row;
}

.jp-OutputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-outprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

.jp-OutputArea-output {
  height: auto;
  overflow: auto;
  user-select: text;
  -moz-user-select: text;
  -webkit-user-select: text;
  -ms-user-select: text;
}

.jp-OutputArea-child .jp-OutputArea-output {
  flex-grow: 1;
  flex-shrink: 1;
}

/**
 * Isolated output.
 */
.jp-OutputArea-output.jp-mod-isolated {
  width: 100%;
  display: block;
}

/*
When drag events occur, `p-mod-override-cursor` is added to the body.
Because iframes steal all cursor events, the following two rules are necessary
to suppress pointer events while resize drags are occurring. There may be a
better solution to this problem.
*/
body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated {
  position: relative;
}

body.lm-mod-override-cursor .jp-OutputArea-output.jp-mod-isolated:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: transparent;
}

/* pre */

.jp-OutputArea-output pre {
  border: none;
  margin: 0px;
  padding: 0px;
  overflow-x: auto;
  overflow-y: auto;
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}

/* tables */

.jp-OutputArea-output.jp-RenderedHTMLCommon table {
  margin-left: 0;
  margin-right: 0;
}

/* description lists */

.jp-OutputArea-output dl,
.jp-OutputArea-output dt,
.jp-OutputArea-output dd {
  display: block;
}

.jp-OutputArea-output dl {
  width: 100%;
  overflow: hidden;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dt {
  font-weight: bold;
  float: left;
  width: 20%;
  padding: 0;
  margin: 0;
}

.jp-OutputArea-output dd {
  float: left;
  width: 80%;
  padding: 0;
  margin: 0;
}

/* Hide the gutter in case of
 *  - nested output areas (e.g. in the case of output widgets)
 *  - mirrored output areas
 */
.jp-OutputArea .jp-OutputArea .jp-OutputArea-prompt {
  display: none;
}

/*-----------------------------------------------------------------------------
| executeResult is added to any Output-result for the display of the object
| returned by a cell
|----------------------------------------------------------------------------*/

.jp-OutputArea-output.jp-OutputArea-executeResult {
  margin-left: 0px;
  flex: 1 1 auto;
}

.jp-OutputArea-executeResult.jp-RenderedText {
  padding-top: var(--jp-code-padding);
}

/*-----------------------------------------------------------------------------
| The Stdin output
|----------------------------------------------------------------------------*/

.jp-OutputArea-stdin {
  line-height: var(--jp-code-line-height);
  padding-top: var(--jp-code-padding);
  display: flex;
}

.jp-Stdin-prompt {
  color: var(--jp-content-font-color0);
  padding-right: var(--jp-code-padding);
  vertical-align: baseline;
  flex: 0 0 auto;
}

.jp-Stdin-input {
  font-family: var(--jp-code-font-family);
  font-size: inherit;
  color: inherit;
  background-color: inherit;
  width: 42%;
  min-width: 200px;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
  flex: 0 0 70%;
}

.jp-Stdin-input:focus {
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Output Area View
|----------------------------------------------------------------------------*/

.jp-LinkedOutputView .jp-OutputArea {
  height: 100%;
  display: block;
}

.jp-LinkedOutputView .jp-OutputArea-output:only-child {
  height: 100%;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

.jp-Collapser {
  flex: 0 0 var(--jp-cell-collapser-width);
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
  border-radius: var(--jp-border-radius);
  opacity: 1;
}

.jp-Collapser-child {
  display: block;
  width: 100%;
  box-sizing: border-box;
  /* height: 100% doesn't work because the height of its parent is computed from content */
  position: absolute;
  top: 0px;
  bottom: 0px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Header/Footer
|----------------------------------------------------------------------------*/

/* Hidden by zero height by default */
.jp-CellHeader,
.jp-CellFooter {
  height: 0px;
  width: 100%;
  padding: 0px;
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Input
|----------------------------------------------------------------------------*/

/* All input areas */
.jp-InputArea {
  display: flex;
  flex-direction: row;
}

.jp-InputArea-editor {
  flex: 1 1 auto;
}

.jp-InputArea-editor {
  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0px;
  background: var(--jp-cell-editor-background);
}

.jp-InputPrompt {
  flex: 0 0 var(--jp-cell-prompt-width);
  color: var(--jp-cell-inprompt-font-color);
  font-family: var(--jp-cell-prompt-font-family);
  padding: var(--jp-code-padding);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  opacity: var(--jp-cell-prompt-opacity);
  line-height: var(--jp-code-line-height);
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
  opacity: var(--jp-cell-prompt-opacity);
  /* Right align prompt text, don't wrap to handle large prompt numbers */
  text-align: right;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  /* Disable text selection */
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Placeholder {
  display: flex;
  flex-direction: row;
  flex: 1 1 auto;
}

.jp-Placeholder-prompt {
  box-sizing: border-box;
}

.jp-Placeholder-content {
  flex: 1 1 auto;
  border: none;
  background: transparent;
  height: 20px;
  box-sizing: border-box;
}

.jp-Placeholder-content .jp-MoreHorizIcon {
  width: 32px;
  height: 16px;
  border: 1px solid transparent;
  border-radius: var(--jp-border-radius);
}

.jp-Placeholder-content .jp-MoreHorizIcon:hover {
  border: 1px solid var(--jp-border-color1);
  box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.25);
  background-color: var(--jp-layout-color0);
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-cell-scrolling-output-offset: 5px;
}

/*-----------------------------------------------------------------------------
| Cell
|----------------------------------------------------------------------------*/

.jp-Cell {
  padding: var(--jp-cell-padding);
  margin: 0px;
  border: none;
  outline: none;
  background: transparent;
}

/*-----------------------------------------------------------------------------
| Common input/output
|----------------------------------------------------------------------------*/

.jp-Cell-inputWrapper,
.jp-Cell-outputWrapper {
  display: flex;
  flex-direction: row;
  padding: 0px;
  margin: 0px;
  /* Added to reveal the box-shadow on the input and output collapsers. */
  overflow: visible;
}

/* Only input/output areas inside cells */
.jp-Cell-inputArea,
.jp-Cell-outputArea {
  flex: 1 1 auto;
}

/*-----------------------------------------------------------------------------
| Collapser
|----------------------------------------------------------------------------*/

/* Make the output collapser disappear when there is not output, but do so
 * in a manner that leaves it in the layout and preserves its width.
 */
.jp-Cell.jp-mod-noOutputs .jp-Cell-outputCollapser {
  border: none !important;
  background: transparent !important;
}

.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputCollapser {
  min-height: var(--jp-cell-collapser-min-height);
}

/*-----------------------------------------------------------------------------
| Output
|----------------------------------------------------------------------------*/

/* Put a space between input and output when there IS output */
.jp-Cell:not(.jp-mod-noOutputs) .jp-Cell-outputWrapper {
  margin-top: 5px;
}

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-Cell-outputArea {
  overflow-y: auto;
  max-height: 200px;
  box-shadow: inset 0 0 6px 2px rgba(0, 0, 0, 0.3);
  margin-left: var(--jp-private-cell-scrolling-output-offset);
}

.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  flex: 0 0
    calc(
      var(--jp-cell-prompt-width) -
        var(--jp-private-cell-scrolling-output-offset)
    );
}

/*-----------------------------------------------------------------------------
| CodeCell
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| MarkdownCell
|----------------------------------------------------------------------------*/

.jp-MarkdownOutput {
  flex: 1 1 auto;
  margin-top: 0;
  margin-bottom: 0;
  padding-left: var(--jp-code-padding);
}

.jp-MarkdownOutput.jp-RenderedHTMLCommon {
  overflow: auto;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Variables
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------

/*-----------------------------------------------------------------------------
| Styles
|----------------------------------------------------------------------------*/

.jp-NotebookPanel-toolbar {
  padding: 2px;
}

.jp-Toolbar-item.jp-Notebook-toolbarCellType .jp-select-wrapper.jp-mod-focused {
  border: none;
  box-shadow: none;
}

.jp-Notebook-toolbarCellTypeDropdown select {
  height: 24px;
  font-size: var(--jp-ui-font-size1);
  line-height: 14px;
  border-radius: 0;
  display: block;
}

.jp-Notebook-toolbarCellTypeDropdown span {
  top: 5px !important;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Private CSS variables
|----------------------------------------------------------------------------*/

:root {
  --jp-private-notebook-dragImage-width: 304px;
  --jp-private-notebook-dragImage-height: 36px;
  --jp-private-notebook-selected-color: var(--md-blue-400);
  --jp-private-notebook-active-color: var(--md-green-400);
}

/*-----------------------------------------------------------------------------
| Imports
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| Notebook
|----------------------------------------------------------------------------*/

.jp-NotebookPanel {
  display: block;
  height: 100%;
}

.jp-NotebookPanel.jp-Document {
  min-width: 240px;
  min-height: 120px;
}

.jp-Notebook {
  padding: var(--jp-notebook-padding);
  outline: none;
  overflow: auto;
  background: var(--jp-layout-color0);
}

.jp-Notebook.jp-mod-scrollPastEnd::after {
  display: block;
  content: '';
  min-height: var(--jp-notebook-scroll-padding);
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
}

/*-----------------------------------------------------------------------------
| Notebook state related styling
|
| The notebook and cells each have states, here are the possibilities:
|
| - Notebook
|   - Command
|   - Edit
| - Cell
|   - None
|   - Active (only one can be active)
|   - Selected (the cells actions are applied to)
|   - Multiselected (when multiple selected, the cursor)
|   - No outputs
|----------------------------------------------------------------------------*/

/* Command or edit modes */

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-InputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

.jp-Notebook .jp-Cell:not(.jp-mod-active) .jp-OutputPrompt {
  opacity: var(--jp-cell-prompt-not-active-opacity);
  color: var(--jp-cell-prompt-not-active-font-color);
}

/* cell is active */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser {
  background: var(--jp-brand-color1);
}

/* collapser is hovered */
.jp-Notebook .jp-Cell .jp-Collapser:hover {
  box-shadow: var(--jp-elevation-z2);
  background: var(--jp-brand-color1);
  opacity: var(--jp-cell-collapser-not-active-hover-opacity);
}

/* cell is active and collapser is hovered */
.jp-Notebook .jp-Cell.jp-mod-active .jp-Collapser:hover {
  background: var(--jp-brand-color0);
  opacity: 1;
}

/* Command mode */

.jp-Notebook.jp-mod-commandMode .jp-Cell.jp-mod-selected {
  background: var(--jp-notebook-multiselected-color);
}

.jp-Notebook.jp-mod-commandMode
  .jp-Cell.jp-mod-active.jp-mod-selected:not(.jp-mod-multiSelected) {
  background: transparent;
}

/* Edit mode */

.jp-Notebook.jp-mod-editMode .jp-Cell.jp-mod-active .jp-InputArea-editor {
  border: var(--jp-border-width) solid var(--jp-cell-editor-active-border-color);
  box-shadow: var(--jp-input-box-shadow);
  background-color: var(--jp-cell-editor-active-background);
}

/*-----------------------------------------------------------------------------
| Notebook drag and drop
|----------------------------------------------------------------------------*/

.jp-Notebook-cell.jp-mod-dropSource {
  opacity: 0.5;
}

.jp-Notebook-cell.jp-mod-dropTarget,
.jp-Notebook.jp-mod-commandMode
  .jp-Notebook-cell.jp-mod-active.jp-mod-selected.jp-mod-dropTarget {
  border-top-color: var(--jp-private-notebook-selected-color);
  border-top-style: solid;
  border-top-width: 2px;
}

.jp-dragImage {
  display: flex;
  flex-direction: row;
  width: var(--jp-private-notebook-dragImage-width);
  height: var(--jp-private-notebook-dragImage-height);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background);
  overflow: visible;
}

.jp-dragImage-singlePrompt {
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

.jp-dragImage .jp-dragImage-content {
  flex: 1 1 auto;
  z-index: 2;
  font-size: var(--jp-code-font-size);
  font-family: var(--jp-code-font-family);
  line-height: var(--jp-code-line-height);
  padding: var(--jp-code-padding);
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  background: var(--jp-cell-editor-background-color);
  color: var(--jp-content-font-color3);
  text-align: left;
  margin: 4px 4px 4px 0px;
}

.jp-dragImage .jp-dragImage-prompt {
  flex: 0 0 auto;
  min-width: 36px;
  color: var(--jp-cell-inprompt-font-color);
  padding: var(--jp-code-padding);
  padding-left: 12px;
  font-family: var(--jp-cell-prompt-font-family);
  letter-spacing: var(--jp-cell-prompt-letter-spacing);
  line-height: 1.9;
  font-size: var(--jp-code-font-size);
  border: var(--jp-border-width) solid transparent;
}

.jp-dragImage-multipleBack {
  z-index: -1;
  position: absolute;
  height: 32px;
  width: 300px;
  top: 8px;
  left: 8px;
  background: var(--jp-layout-color2);
  border: var(--jp-border-width) solid var(--jp-input-border-color);
  box-shadow: 2px 2px 4px 0px rgba(0, 0, 0, 0.12);
}

/*-----------------------------------------------------------------------------
| Cell toolbar
|----------------------------------------------------------------------------*/

.jp-NotebookTools {
  display: block;
  min-width: var(--jp-sidebar-min-width);
  color: var(--jp-ui-font-color1);
  background: var(--jp-layout-color1);
  /* This is needed so that all font sizing of children done in ems is
    * relative to this base size */
  font-size: var(--jp-ui-font-size1);
  overflow: auto;
}

.jp-NotebookTools-tool {
  padding: 0px 12px 0 12px;
}

.jp-ActiveCellTool {
  padding: 12px;
  background-color: var(--jp-layout-color1);
  border-top: none !important;
}

.jp-ActiveCellTool .jp-InputArea-prompt {
  flex: 0 0 auto;
  padding-left: 0px;
}

.jp-ActiveCellTool .jp-InputArea-editor {
  flex: 1 1 auto;
  background: var(--jp-cell-editor-background);
  border-color: var(--jp-cell-editor-border-color);
}

.jp-ActiveCellTool .jp-InputArea-editor .CodeMirror {
  background: transparent;
}

.jp-MetadataEditorTool {
  flex-direction: column;
  padding: 12px 0px 12px 0px;
}

.jp-RankedPanel > :not(:first-child) {
  margin-top: 12px;
}

.jp-KeySelector select.jp-mod-styled {
  font-size: var(--jp-ui-font-size1);
  color: var(--jp-ui-font-color0);
  border: var(--jp-border-width) solid var(--jp-border-color1);
}

.jp-KeySelector label,
.jp-MetadataEditorTool label {
  line-height: 1.4;
}

/*-----------------------------------------------------------------------------
| Presentation Mode (.jp-mod-presentationMode)
|----------------------------------------------------------------------------*/

.jp-mod-presentationMode .jp-Notebook {
  --jp-content-font-size1: var(--jp-content-presentation-font-size1);
  --jp-code-font-size: var(--jp-code-presentation-font-size);
}

.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-InputPrompt,
.jp-mod-presentationMode .jp-Notebook .jp-Cell .jp-OutputPrompt {
  flex: 0 0 110px;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/* This file was auto-generated by ensurePackage() in @jupyterlab/buildutils */

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

</style>

    <style type="text/css">
/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*
The following CSS variables define the main, public API for styling JupyterLab.
These variables should be used by all plugins wherever possible. In other
words, plugins should not define custom colors, sizes, etc unless absolutely
necessary. This enables users to change the visual theme of JupyterLab
by changing these variables.

Many variables appear in an ordered sequence (0,1,2,3). These sequences
are designed to work well together, so for example, `--jp-border-color1` should
be used with `--jp-layout-color1`. The numbers have the following meanings:

* 0: super-primary, reserved for special emphasis
* 1: primary, most important under normal situations
* 2: secondary, next most important under normal situations
* 3: tertiary, next most important under normal situations

Throughout JupyterLab, we are mostly following principles from Google's
Material Design when selecting colors. We are not, however, following
all of MD as it is not optimized for dense, information rich UIs.
*/

:root {
  /* Elevation
   *
   * We style box-shadows using Material Design's idea of elevation. These particular numbers are taken from here:
   *
   * https://github.com/material-components/material-components-web
   * https://material-components-web.appspot.com/elevation.html
   */

  --jp-shadow-base-lightness: 0;
  --jp-shadow-umbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.2
  );
  --jp-shadow-penumbra-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.14
  );
  --jp-shadow-ambient-color: rgba(
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    var(--jp-shadow-base-lightness),
    0.12
  );
  --jp-elevation-z0: none;
  --jp-elevation-z1: 0px 2px 1px -1px var(--jp-shadow-umbra-color),
    0px 1px 1px 0px var(--jp-shadow-penumbra-color),
    0px 1px 3px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z2: 0px 3px 1px -2px var(--jp-shadow-umbra-color),
    0px 2px 2px 0px var(--jp-shadow-penumbra-color),
    0px 1px 5px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z4: 0px 2px 4px -1px var(--jp-shadow-umbra-color),
    0px 4px 5px 0px var(--jp-shadow-penumbra-color),
    0px 1px 10px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z6: 0px 3px 5px -1px var(--jp-shadow-umbra-color),
    0px 6px 10px 0px var(--jp-shadow-penumbra-color),
    0px 1px 18px 0px var(--jp-shadow-ambient-color);
  --jp-elevation-z8: 0px 5px 5px -3px var(--jp-shadow-umbra-color),
    0px 8px 10px 1px var(--jp-shadow-penumbra-color),
    0px 3px 14px 2px var(--jp-shadow-ambient-color);
  --jp-elevation-z12: 0px 7px 8px -4px var(--jp-shadow-umbra-color),
    0px 12px 17px 2px var(--jp-shadow-penumbra-color),
    0px 5px 22px 4px var(--jp-shadow-ambient-color);
  --jp-elevation-z16: 0px 8px 10px -5px var(--jp-shadow-umbra-color),
    0px 16px 24px 2px var(--jp-shadow-penumbra-color),
    0px 6px 30px 5px var(--jp-shadow-ambient-color);
  --jp-elevation-z20: 0px 10px 13px -6px var(--jp-shadow-umbra-color),
    0px 20px 31px 3px var(--jp-shadow-penumbra-color),
    0px 8px 38px 7px var(--jp-shadow-ambient-color);
  --jp-elevation-z24: 0px 11px 15px -7px var(--jp-shadow-umbra-color),
    0px 24px 38px 3px var(--jp-shadow-penumbra-color),
    0px 9px 46px 8px var(--jp-shadow-ambient-color);

  /* Borders
   *
   * The following variables, specify the visual styling of borders in JupyterLab.
   */

  --jp-border-width: 1px;
  --jp-border-color0: var(--md-grey-400);
  --jp-border-color1: var(--md-grey-400);
  --jp-border-color2: var(--md-grey-300);
  --jp-border-color3: var(--md-grey-200);
  --jp-border-radius: 2px;

  /* UI Fonts
   *
   * The UI font CSS variables are used for the typography all of the JupyterLab
   * user interface elements that are not directly user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-ui-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-ui-font-scale-factor: 1.2;
  --jp-ui-font-size0: 0.83333em;
  --jp-ui-font-size1: 13px; /* Base font size */
  --jp-ui-font-size2: 1.2em;
  --jp-ui-font-size3: 1.44em;

  --jp-ui-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica,
    Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';

  /*
   * Use these font colors against the corresponding main layout colors.
   * In a light theme, these go from dark to light.
   */

  /* Defaults use Material Design specification */
  --jp-ui-font-color0: rgba(0, 0, 0, 1);
  --jp-ui-font-color1: rgba(0, 0, 0, 0.87);
  --jp-ui-font-color2: rgba(0, 0, 0, 0.54);
  --jp-ui-font-color3: rgba(0, 0, 0, 0.38);

  /*
   * Use these against the brand/accent/warn/error colors.
   * These will typically go from light to darker, in both a dark and light theme.
   */

  --jp-ui-inverse-font-color0: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color1: rgba(255, 255, 255, 1);
  --jp-ui-inverse-font-color2: rgba(255, 255, 255, 0.7);
  --jp-ui-inverse-font-color3: rgba(255, 255, 255, 0.5);

  /* Content Fonts
   *
   * Content font variables are used for typography of user generated content.
   *
   * The font sizing here is done assuming that the body font size of --jp-content-font-size1
   * is applied to a parent element. When children elements, such as headings, are sized
   * in em all things will be computed relative to that body size.
   */

  --jp-content-line-height: 1.6;
  --jp-content-font-scale-factor: 1.2;
  --jp-content-font-size0: 0.83333em;
  --jp-content-font-size1: 14px; /* Base font size */
  --jp-content-font-size2: 1.2em;
  --jp-content-font-size3: 1.44em;
  --jp-content-font-size4: 1.728em;
  --jp-content-font-size5: 2.0736em;

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-content-presentation-font-size1: 17px;

  --jp-content-heading-line-height: 1;
  --jp-content-heading-margin-top: 1.2em;
  --jp-content-heading-margin-bottom: 0.8em;
  --jp-content-heading-font-weight: 500;

  /* Defaults use Material Design specification */
  --jp-content-font-color0: rgba(0, 0, 0, 1);
  --jp-content-font-color1: rgba(0, 0, 0, 0.87);
  --jp-content-font-color2: rgba(0, 0, 0, 0.54);
  --jp-content-font-color3: rgba(0, 0, 0, 0.38);

  --jp-content-link-color: var(--md-blue-700);

  --jp-content-font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Helvetica, Arial, sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol';

  /*
   * Code Fonts
   *
   * Code font variables are used for typography of code and other monospaces content.
   */

  --jp-code-font-size: 13px;
  --jp-code-line-height: 1.3077; /* 17px for 13px base */
  --jp-code-padding: 5px; /* 5px for 13px base, codemirror highlighting needs integer px value */
  --jp-code-font-family-default: Menlo, Consolas, 'DejaVu Sans Mono', monospace;
  --jp-code-font-family: var(--jp-code-font-family-default);

  /* This gives a magnification of about 125% in presentation mode over normal. */
  --jp-code-presentation-font-size: 16px;

  /* may need to tweak cursor width if you change font size */
  --jp-code-cursor-width0: 1.4px;
  --jp-code-cursor-width1: 2px;
  --jp-code-cursor-width2: 4px;

  /* Layout
   *
   * The following are the main layout colors use in JupyterLab. In a light
   * theme these would go from light to dark.
   */

  --jp-layout-color0: white;
  --jp-layout-color1: white;
  --jp-layout-color2: var(--md-grey-200);
  --jp-layout-color3: var(--md-grey-400);
  --jp-layout-color4: var(--md-grey-600);

  /* Inverse Layout
   *
   * The following are the inverse layout colors use in JupyterLab. In a light
   * theme these would go from dark to light.
   */

  --jp-inverse-layout-color0: #111111;
  --jp-inverse-layout-color1: var(--md-grey-900);
  --jp-inverse-layout-color2: var(--md-grey-800);
  --jp-inverse-layout-color3: var(--md-grey-700);
  --jp-inverse-layout-color4: var(--md-grey-600);

  /* Brand/accent */

  --jp-brand-color0: var(--md-blue-700);
  --jp-brand-color1: var(--md-blue-500);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);

  --jp-accent-color0: var(--md-green-700);
  --jp-accent-color1: var(--md-green-500);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-700);
  --jp-warn-color1: var(--md-orange-500);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);

  --jp-error-color0: var(--md-red-700);
  --jp-error-color1: var(--md-red-500);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);

  --jp-success-color0: var(--md-green-700);
  --jp-success-color1: var(--md-green-500);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);

  --jp-info-color0: var(--md-cyan-700);
  --jp-info-color1: var(--md-cyan-500);
  --jp-info-color2: var(--md-cyan-300);
  --jp-info-color3: var(--md-cyan-100);

  /* Cell specific styles */

  --jp-cell-padding: 5px;

  --jp-cell-collapser-width: 8px;
  --jp-cell-collapser-min-height: 20px;
  --jp-cell-collapser-not-active-hover-opacity: 0.6;

  --jp-cell-editor-background: var(--md-grey-100);
  --jp-cell-editor-border-color: var(--md-grey-300);
  --jp-cell-editor-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-cell-editor-active-background: var(--jp-layout-color0);
  --jp-cell-editor-active-border-color: var(--jp-brand-color1);

  --jp-cell-prompt-width: 64px;
  --jp-cell-prompt-font-family: 'Source Code Pro', monospace;
  --jp-cell-prompt-letter-spacing: 0px;
  --jp-cell-prompt-opacity: 1;
  --jp-cell-prompt-not-active-opacity: 0.5;
  --jp-cell-prompt-not-active-font-color: var(--md-grey-700);
  /* A custom blend of MD grey and blue 600
   * See https://meyerweb.com/eric/tools/color-blend/#546E7A:1E88E5:5:hex */
  --jp-cell-inprompt-font-color: #307fc1;
  /* A custom blend of MD grey and orange 600
   * https://meyerweb.com/eric/tools/color-blend/#546E7A:F4511E:5:hex */
  --jp-cell-outprompt-font-color: #bf5b3d;

  /* Notebook specific styles */

  --jp-notebook-padding: 10px;
  --jp-notebook-select-background: var(--jp-layout-color1);
  --jp-notebook-multiselected-color: var(--md-blue-50);

  /* The scroll padding is calculated to fill enough space at the bottom of the
  notebook to show one single-line cell (with appropriate padding) at the top
  when the notebook is scrolled all the way to the bottom. We also subtract one
  pixel so that no scrollbar appears if we have just one single-line cell in the
  notebook. This padding is to enable a 'scroll past end' feature in a notebook.
  */
  --jp-notebook-scroll-padding: calc(
    100% - var(--jp-code-font-size) * var(--jp-code-line-height) -
      var(--jp-code-padding) - var(--jp-cell-padding) - 1px
  );

  /* Rendermime styles */

  --jp-rendermime-error-background: #fdd;
  --jp-rendermime-table-row-background: var(--md-grey-100);
  --jp-rendermime-table-row-hover-background: var(--md-light-blue-50);

  /* Dialog specific styles */

  --jp-dialog-background: rgba(0, 0, 0, 0.25);

  /* Console specific styles */

  --jp-console-padding: 10px;

  /* Toolbar specific styles */

  --jp-toolbar-border-color: var(--jp-border-color1);
  --jp-toolbar-micro-height: 8px;
  --jp-toolbar-background: var(--jp-layout-color1);
  --jp-toolbar-box-shadow: 0px 0px 2px 0px rgba(0, 0, 0, 0.24);
  --jp-toolbar-header-margin: 4px 4px 0px 4px;
  --jp-toolbar-active-background: var(--md-grey-300);

  /* Input field styles */

  --jp-input-box-shadow: inset 0 0 2px var(--md-blue-300);
  --jp-input-active-background: var(--jp-layout-color1);
  --jp-input-hover-background: var(--jp-layout-color1);
  --jp-input-background: var(--md-grey-100);
  --jp-input-border-color: var(--jp-border-color1);
  --jp-input-active-border-color: var(--jp-brand-color1);
  --jp-input-active-box-shadow-color: rgba(19, 124, 189, 0.3);

  /* General editor styles */

  --jp-editor-selected-background: #d9d9d9;
  --jp-editor-selected-focused-background: #d7d4f0;
  --jp-editor-cursor-color: var(--jp-ui-font-color0);

  /* Code mirror specific styles */

  --jp-mirror-editor-keyword-color: #008000;
  --jp-mirror-editor-atom-color: #88f;
  --jp-mirror-editor-number-color: #080;
  --jp-mirror-editor-def-color: #00f;
  --jp-mirror-editor-variable-color: var(--md-grey-900);
  --jp-mirror-editor-variable-2-color: #05a;
  --jp-mirror-editor-variable-3-color: #085;
  --jp-mirror-editor-punctuation-color: #05a;
  --jp-mirror-editor-property-color: #05a;
  --jp-mirror-editor-operator-color: #aa22ff;
  --jp-mirror-editor-comment-color: #408080;
  --jp-mirror-editor-string-color: #ba2121;
  --jp-mirror-editor-string-2-color: #708;
  --jp-mirror-editor-meta-color: #aa22ff;
  --jp-mirror-editor-qualifier-color: #555;
  --jp-mirror-editor-builtin-color: #008000;
  --jp-mirror-editor-bracket-color: #997;
  --jp-mirror-editor-tag-color: #170;
  --jp-mirror-editor-attribute-color: #00c;
  --jp-mirror-editor-header-color: blue;
  --jp-mirror-editor-quote-color: #090;
  --jp-mirror-editor-link-color: #00c;
  --jp-mirror-editor-error-color: #f00;
  --jp-mirror-editor-hr-color: #999;

  /* Vega extension styles */

  --jp-vega-background: white;

  /* Sidebar-related styles */

  --jp-sidebar-min-width: 180px;

  /* Search-related styles */

  --jp-search-toggle-off-opacity: 0.5;
  --jp-search-toggle-hover-opacity: 0.8;
  --jp-search-toggle-on-opacity: 1;
  --jp-search-selected-match-background-color: rgb(245, 200, 0);
  --jp-search-selected-match-color: black;
  --jp-search-unselected-match-background-color: var(
    --jp-inverse-layout-color0
  );
  --jp-search-unselected-match-color: var(--jp-ui-inverse-font-color0);

  /* Icon colors that work well with light or dark backgrounds */
  --jp-icon-contrast-color0: var(--md-purple-600);
  --jp-icon-contrast-color1: var(--md-green-600);
  --jp-icon-contrast-color2: var(--md-pink-600);
  --jp-icon-contrast-color3: var(--md-blue-600);
}
</style>

<style type="text/css">
a.anchor-link {
   display: none;
}
.highlight  {
    margin: 0.4em;
}

/* Input area styling */
.jp-InputArea {
    overflow: hidden;
}

.jp-InputArea-editor {
    overflow: hidden;
}

@media print {
  body {
    margin: 0;
  }
}
</style>



<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-MML-AM_CHTML-full,Safe"> </script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    init_mathjax = function() {
        if (window.MathJax) {
        // MathJax loaded
            MathJax.Hub.Config({
                TeX: {
                    equationNumbers: {
                    autoNumber: "AMS",
                    useLabelIds: true
                    }
                },
                tex2jax: {
                    inlineMath: [ ['$','$'], ["\\(","\\)"] ],
                    displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
                    processEscapes: true,
                    processEnvironments: true
                },
                displayAlign: 'center',
                CommonHTML: {
                    linebreaks: { 
                    automatic: true 
                    }
                },
                "HTML-CSS": {
                    linebreaks: { 
                    automatic: true 
                    }
                }
            });
        
            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
    <!-- End of mathjax configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">

<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="A-Deep-Dive-Into-My-League-of-Legends-Stats"><center>A Deep Dive Into My League of Legends Stats</center><a class="anchor-link" href="#A-Deep-Dive-Into-My-League-of-Legends-Stats">&#182;</a></h1><h3 id="-By-Patrick-Hogan-"><center> By Patrick Hogan </center><a class="anchor-link" href="#-By-Patrick-Hogan-">&#182;</a></h3><p><br> <br>
<img align="center" src="http://ddragon.leagueoflegends.com/cdn/img/champion/splash/TahmKench_0.jpg" alt="drawing" width="500"/></p>
<p><br>
<br></p>
<hr>
<h2 id="Introduction">Introduction<a class="anchor-link" href="#Introduction">&#182;</a></h2><p>League of Legends is a 2009 multiplayer video game from Riot Games, and in its nearly 12 year run has become one of, if not the most popular esport on the planet. Millions upons millions of people around the world play the game, and like some <strong>real</strong> sports (e.g. Baseball), there are tons of statistics and data to sift through. In this tutorial I will show you the entire data science pipeline using my own personal data from the 2021 Ranked season thus far. I have been playing League of Legends since late 2015, but have only recently become more involved in playing the game competitively. Furthermore, this method can be applied to any player, with only minor tweaks depending on your role and amount of games played. I wanted a personalized, in depth look at what makes me tick as a player. I think I delivered on that, but please, take a look for yourself!</p>
<h2 id="The-Game">The Game<a class="anchor-link" href="#The-Game">&#182;</a></h2><p>League of Legends is referred to as a Multiplayer Online Battle Arena (<a href="https://en.wikipedia.org/wiki/Multiplayer_online_battle_arena">more about the MOBA genre</a>). In League, or LoL, two teams of five are pitted against each other on the map Summoner's Rift, which has remained largely the same over time. The main goal for either team is to destroy your enemy's base, represented by the Nexus. The first team to lose their Nexus (or forfeit) loses. There are countless other aspects of the game, such as vision, dragons, Baron Nashor, team composition, and itemization. To say it's a complex game would be an understatement. It also comes with an extremely steep learning curve, as many new players are typically much worse than regulars, and it takes time to understand the flow of the game, as well as mechanics.</p>
<h2 id="Why-Was-I-Motivated-to-Work-on-This?">Why Was I Motivated to Work on This?<a class="anchor-link" href="#Why-Was-I-Motivated-to-Work-on-This?">&#182;</a></h2><p>In League, there are five roles: Top Lane, Jungle, Middle Lane, Bottom Lane, and Support (who also goes into the Bottom Lane). I have been playing Support as my main role for over 5 years (on and off), and I have mainly been playing the same character: Tahm Kench, the River King, pictured above. Read more about Tahm Kench <a href="https://na.leagueoflegends.com/en-us/champions/tahm-kench/">here</a>. Over time I have picked up various other characters, but to this day I am still mainly playing Tahm. I chose to do my project on my personal statistics due to the fact that I am quite invested in this game, and I create my own data, essentially. In addition, I'm personally excited to see breakdowns of my statistics, specifically ones that common stat sites will not tell you. I will be answering and modeling various aspects of the game, such as team composition, enemy matchups, and kill participation in order to obtain a better understanding of how I play the game.</p>
<h3 id="Imports">Imports<a class="anchor-link" href="#Imports">&#182;</a></h3><p>In the Python below, we have to import some packages that contain essential functions. Which ones you import may depend, but Pandas and Numpy are staples. Read more about Pandas <a href="https://pandas.pydata.org/">here</a>, Numpy <a href="https://numpy.org/">here</a> and matplotlib's pyplot <a href="https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html#:~:text=pyplot%20is%20a%20state%2Dbased,pyplot%20as%20plt%20x%20%3D%20np.">here</a>.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[1]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">mpl</span>
<span class="kn">import</span> <span class="nn">requests</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Data-Scraping-and-Wrangling">Data Scraping and Wrangling<a class="anchor-link" href="#Data-Scraping-and-Wrangling">&#182;</a></h2><p>To begin, let's actually get my data from Riot's databases. Unfortunately the API is limited, and they still have not reviewed my application, so I am importing a text file here that contains my temporary API key. You can receive one via the <a href="https://developer.riotgames.com/">Riot Games Developer Portal</a>. This data is publicly available to anyone with an API key, and keys are free to obtain.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[2]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Opening the api text file</span>
<span class="k">with</span> <span class="nb">open</span> <span class="p">(</span><span class="s2">&quot;api.txt&quot;</span><span class="p">,</span> <span class="s2">&quot;r&quot;</span><span class="p">)</span> <span class="k">as</span> <span class="n">myfile</span><span class="p">:</span>
    <span class="n">data</span><span class="o">=</span><span class="n">myfile</span><span class="o">.</span><span class="n">readlines</span><span class="p">()</span>
    
<span class="n">api</span> <span class="o">=</span> <span class="n">data</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>

<span class="c1"># Using the api to format the account API request URL properly.</span>
<span class="n">request_account</span> <span class="o">=</span> <span class="s2">&quot;https://na1.api.riotgames.com/lol/summoner/v4/summoners/by-name/OG%20Zoidberg?api_key=</span><span class="si">{}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">api</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[3]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Riot utilizes JSON for their API, so I can convert the raw request module data into json using the appropriate function.</span>
<span class="n">account_json</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">request_account</span><span class="p">)</span><span class="o">.</span><span class="n">json</span><span class="p">()</span>
<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="o">.</span><span class="n">from_dict</span><span class="p">(</span><span class="n">account_json</span><span class="p">,</span> <span class="s1">&#39;index&#39;</span><span class="p">)</span>
<span class="c1"># pandas supports json, so you can immediately put the json into a dataframe. It may need work, but it&#39;s a good start.</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>The produced dataframe contains some account details, none of which are super sensitive, since anyone can search "OG Zoidberg" on the API. Anyways, now that we have the accountId, we can request from the match history API to receive a list of matches. Notice below there are several dataframes for matches. This is another limiation of the Riot API. The maximum number of games I can request is 100 per request, and I have player over 200 games, but not over 300. In addition, for the purposes of this assignment, I have stopped playing Ranked in order to ensure my dataset is of a fixed size. There are other important parameters to consider. Accoring to official documentation (found <a href="https://developer.riotgames.com/docs/lol">here</a>), there is a file for Queue types (Ranked, Unranked, etc) as well as a file containing the different "seasons" (though it is now deprecated, I can cross reference the amount of games I've played this season with the query in order to make sure I don't actually request any preseason or Season 2020 games). The Queue ID for ranked is 420, and the Season ID is 13, so we can factor these into the three requests as well.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[4]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">acc_id</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">1</span><span class="p">,</span><span class="mi">0</span><span class="p">]</span>
<span class="n">acc_id</span>
<span class="n">request_match_history</span> <span class="o">=</span> <span class="s2">&quot;https://na1.api.riotgames.com/lol/match/v4/matchlists/by-account/</span><span class="si">{}</span><span class="s2">?queue=420&amp;season=13&amp;api_key=</span><span class="si">{}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">acc_id</span><span class="p">,</span> <span class="n">api</span><span class="p">)</span>
<span class="n">matches_json</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">request_match_history</span><span class="p">)</span><span class="o">.</span><span class="n">json</span><span class="p">()</span>
<span class="n">match_df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="o">.</span><span class="n">from_dict</span><span class="p">(</span><span class="n">matches_json</span><span class="p">)</span>

<span class="c1">#according to the totalGames column, I have recorded 284 games this season, but the DataFrame only accounts for 100. We need to requery to get</span>
<span class="c1">#games 101-200 and 201-284. This limitation is not on our end, but rather the API designer.</span>
<span class="n">match_df2</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="o">.</span><span class="n">from_dict</span><span class="p">(</span><span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;https://na1.api.riotgames.com/lol/match/v4/matchlists/by-account/niRqhyE4liN4qzGIsmGuIO6jqEqbt6Qfj0IH8U_hV6E-468?queue=420&amp;season=13&amp;beginIndex=100&amp;api_key=</span><span class="si">{}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">api</span><span class="p">))</span><span class="o">.</span><span class="n">json</span><span class="p">())</span>
<span class="n">match_df3</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="o">.</span><span class="n">from_dict</span><span class="p">(</span><span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;https://na1.api.riotgames.com/lol/match/v4/matchlists/by-account/niRqhyE4liN4qzGIsmGuIO6jqEqbt6Qfj0IH8U_hV6E-468?queue=420&amp;season=13&amp;endIndex=272&amp;beginIndex=200&amp;api_key=</span><span class="si">{}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">api</span><span class="p">))</span><span class="o">.</span><span class="n">json</span><span class="p">())</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[5]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">match_df2</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[5]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>matches</th>
      <th>startIndex</th>
      <th>endIndex</th>
      <th>totalGames</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>{'platformId': 'NA1', 'gameId': 3838696903, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
    <tr>
      <th>1</th>
      <td>{'platformId': 'NA1', 'gameId': 3837335394, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
    <tr>
      <th>2</th>
      <td>{'platformId': 'NA1', 'gameId': 3837166306, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
    <tr>
      <th>3</th>
      <td>{'platformId': 'NA1', 'gameId': 3837133018, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
    <tr>
      <th>4</th>
      <td>{'platformId': 'NA1', 'gameId': 3837069642, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>95</th>
      <td>{'platformId': 'NA1', 'gameId': 3778279919, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
    <tr>
      <th>96</th>
      <td>{'platformId': 'NA1', 'gameId': 3776881116, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
    <tr>
      <th>97</th>
      <td>{'platformId': 'NA1', 'gameId': 3776668969, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
    <tr>
      <th>98</th>
      <td>{'platformId': 'NA1', 'gameId': 3773560435, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
    <tr>
      <th>99</th>
      <td>{'platformId': 'NA1', 'gameId': 3772701028, 'c...</td>
      <td>100</td>
      <td>200</td>
      <td>304</td>
    </tr>
  </tbody>
</table>
<p>100 rows × 4 columns</p>
</div>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>This is an example output of a request. Here the only column worth anything is the first column, so we can put them all into a list, and then into a dataframe. We don't have to worry about the other columns since they are just static indices and are the same within each dataframe. The method I am using below uses three iterators, one for each dataframe, using the <a href="https://pandas.pydata.org/pandas-docs/version/1.1.5/reference/api/pandas.DataFrame.iterrows.html">.iterrows() function</a>. This was one way of doing it, but you could also just iterate through the indices and switch to the different dataframes at the correct intervals. That method would result in more code, though. In addition, the amount of loops will vary based on the amount of games you want to analyze. For example, an account like <a href="https://na.op.gg/summoner/userName=HULKSMASH1337">HULKSMASH1337</a> has over 5 times the amount of games I have, so the amount of requests and loops would be much higher.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[6]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Now let&#39;s make a list of just the matches columns throughout each table. Don&#39;t worry, this will be simple.</span>
<span class="n">match_list</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">match_df</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">match_list</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">match_df</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;matches&#39;</span><span class="p">])</span>

<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">match_df2</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">match_list</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">match_df2</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;matches&#39;</span><span class="p">])</span>
    
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">match_df3</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">match_list</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">match_df3</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;matches&#39;</span><span class="p">])</span>
    

    
<span class="n">matches</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">match_list</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[7]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">matches</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[7]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>platformId</th>
      <th>gameId</th>
      <th>champion</th>
      <th>queue</th>
      <th>season</th>
      <th>timestamp</th>
      <th>role</th>
      <th>lane</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NA1</td>
      <td>3891078743</td>
      <td>223</td>
      <td>420</td>
      <td>13</td>
      <td>1620000480427</td>
      <td>DUO_SUPPORT</td>
      <td>BOTTOM</td>
    </tr>
    <tr>
      <th>1</th>
      <td>NA1</td>
      <td>3890814530</td>
      <td>223</td>
      <td>420</td>
      <td>13</td>
      <td>1619982025999</td>
      <td>DUO_SUPPORT</td>
      <td>MID</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NA1</td>
      <td>3887847786</td>
      <td>223</td>
      <td>420</td>
      <td>13</td>
      <td>1619808283274</td>
      <td>DUO_SUPPORT</td>
      <td>BOTTOM</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NA1</td>
      <td>3887833651</td>
      <td>223</td>
      <td>420</td>
      <td>13</td>
      <td>1619806038840</td>
      <td>DUO_SUPPORT</td>
      <td>BOTTOM</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NA1</td>
      <td>3884906923</td>
      <td>50</td>
      <td>420</td>
      <td>13</td>
      <td>1619637970972</td>
      <td>DUO_SUPPORT</td>
      <td>BOTTOM</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>267</th>
      <td>NA1</td>
      <td>3737087437</td>
      <td>223</td>
      <td>420</td>
      <td>13</td>
      <td>1610218825794</td>
      <td>SOLO</td>
      <td>BOTTOM</td>
    </tr>
    <tr>
      <th>268</th>
      <td>NA1</td>
      <td>3736287048</td>
      <td>223</td>
      <td>420</td>
      <td>13</td>
      <td>1610159355278</td>
      <td>DUO_SUPPORT</td>
      <td>BOTTOM</td>
    </tr>
    <tr>
      <th>269</th>
      <td>NA1</td>
      <td>3735983822</td>
      <td>223</td>
      <td>420</td>
      <td>13</td>
      <td>1610141302677</td>
      <td>SOLO</td>
      <td>MID</td>
    </tr>
    <tr>
      <th>270</th>
      <td>NA1</td>
      <td>3735928268</td>
      <td>115</td>
      <td>420</td>
      <td>13</td>
      <td>1610138756604</td>
      <td>SOLO</td>
      <td>MID</td>
    </tr>
    <tr>
      <th>271</th>
      <td>NA1</td>
      <td>3735953139</td>
      <td>115</td>
      <td>420</td>
      <td>13</td>
      <td>1610136275311</td>
      <td>SOLO</td>
      <td>MID</td>
    </tr>
  </tbody>
</table>
<p>272 rows × 8 columns</p>
</div>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Now that we have the list of match histories, we can remove all those in which I did NOT play support, or in other words, games in which I played outside of the bottom lane. The easiest way to do this is via checking my champions, because the  role and lane colummns are not always accurate. <a href="https://na.op.gg/summoner/userName=OG%20Zoidberg">According to my profile on OP.gg</a>, in addition to the 4 support champions, there are two middle lane mages, in Azir and Ziggs. I am omitting these games as middle is not my main role, and they do not accurately reflect on me as a player. In addition, I played a single game of Tahm Kench middle at the start of the season due to an inattentive teammate. We can iterate through the dataframe and drop the rows were champion ID equals anything other than 223 (Tahm Kench), 50 (Swain), 267 (Nami), and 412 (Thresh). These values are given via <a href="http://ddragon.leagueoflegends.com/cdn/11.9.1/data/en_US/champion.json">the champion json file</a>. In addition, I remember my first two games of the season were played on Ziggs, and you can tell that the requests were correct given the last two rows have ID 115 for Ziggs.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[8]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">to_rem_list</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">matches</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="k">if</span> <span class="n">matches</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="mi">2</span><span class="p">]</span> <span class="o">!=</span> <span class="mi">223</span> <span class="ow">and</span> <span class="n">matches</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="mi">2</span><span class="p">]</span> <span class="o">!=</span> <span class="mi">50</span> <span class="ow">and</span> <span class="n">matches</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="mi">2</span><span class="p">]</span> <span class="o">!=</span> <span class="mi">267</span> <span class="ow">and</span> <span class="n">matches</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="mi">2</span><span class="p">]</span> <span class="o">!=</span> <span class="mi">412</span><span class="p">:</span>
        <span class="n">to_rem_list</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">index</span><span class="p">)</span>
        
<span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">to_rem_list</span><span class="p">:</span>
    <span class="n">matches</span> <span class="o">=</span> <span class="n">matches</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
    
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Now to remove the Tahm Mid game, since it won't be useful in my analyses:</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[9]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">matches</span> <span class="o">=</span> <span class="n">matches</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="mi">269</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[10]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">match_list_detailed</span> <span class="o">=</span> <span class="p">[]</span>
<span class="kn">import</span> <span class="nn">time</span>
<span class="n">matches</span> <span class="o">=</span> <span class="n">matches</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span> <span class="c1"># resetting indices so the following loop will ACTUALLY work :)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We have some kind of data, but it's really not what we want, or need. Using the API again, we can use the gameId field with the NA1_ prefix (since I play on the North American server) to get a list of detailed match statistics. The API has a rate limit, so this always takes a few minutes to complete. I imported the time module above in order to prevent a break in the rate limit. You could change the code for different servers, such as the legendary Korean server or one of the EU servers.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[11]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">matches</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">time</span><span class="o">.</span><span class="n">sleep</span><span class="p">(</span><span class="mf">1.3</span><span class="p">)</span>
    <span class="n">game_example_dict</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;https://americas.api.riotgames.com/lol/match/v5/matches/NA1_</span><span class="si">{}</span><span class="s2">?api_key=</span><span class="si">{}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">matches</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="mi">2</span><span class="p">],</span> <span class="n">api</span><span class="p">))</span><span class="o">.</span><span class="n">json</span><span class="p">()</span>
    <span class="n">match_list_detailed</span><span class="o">.</span><span class="n">append</span><span class="p">((</span><span class="n">game_example_dict</span><span class="p">[</span><span class="s1">&#39;info&#39;</span><span class="p">])[</span><span class="s1">&#39;participants&#39;</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[12]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_list</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="n">match_list_detailed</span><span class="p">:</span>
    <span class="n">df_list</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">(</span><span class="n">x</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Let's drop some of the columns we don't need:</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[13]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df_list2</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">data</span> <span class="ow">in</span> <span class="n">df_list</span><span class="p">:</span>
    <span class="n">df_list2</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">data</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">columns</span><span class="o">=</span><span class="p">[</span><span class="s1">&#39;championTransform&#39;</span><span class="p">,</span> <span class="s1">&#39;participantId&#39;</span><span class="p">,</span> <span class="s1">&#39;perks&#39;</span><span class="p">,</span> <span class="s1">&#39;profileIcon&#39;</span><span class="p">,</span> <span class="s1">&#39;riotIdTagline&#39;</span><span class="p">,</span> <span class="s1">&#39;sightWardsBoughtInGame&#39;</span><span class="p">,</span> <span class="s1">&#39;summonerId&#39;</span><span class="p">,</span> <span class="s1">&#39;summonerLevel&#39;</span><span class="p">,</span> <span class="s1">&#39;timePlayed&#39;</span><span class="p">,</span><span class="s1">&#39;bountyLevel&#39;</span><span class="p">,</span><span class="s1">&#39;champExperience&#39;</span><span class="p">,</span><span class="s1">&#39;consumablesPurchased&#39;</span><span class="p">,</span> <span class="s1">&#39;unrealKills&#39;</span><span class="p">,</span><span class="s1">&#39;spell1Casts&#39;</span><span class="p">,</span><span class="s1">&#39;spell2Casts&#39;</span><span class="p">,</span><span class="s1">&#39;spell3Casts&#39;</span><span class="p">,</span><span class="s1">&#39;spell4Casts&#39;</span><span class="p">]))</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Sweet! This should give us a list of match dataframes. I also dropped several columns that will not be useful in our analysis, like bounties, ability cast numbers, and more. Now we can actually explore this data and find things the League Client won't tell you! Let's see what a single game looks like:</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[14]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">pd</span><span class="o">.</span><span class="n">set_option</span><span class="p">(</span><span class="s1">&#39;display.max_columns&#39;</span><span class="p">,</span> <span class="mi">20</span><span class="p">)</span>
<span class="n">df_list2</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[14]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>assists</th>
      <th>baronKills</th>
      <th>champLevel</th>
      <th>championId</th>
      <th>championName</th>
      <th>damageDealtToBuildings</th>
      <th>damageDealtToObjectives</th>
      <th>damageDealtToTurrets</th>
      <th>damageSelfMitigated</th>
      <th>deaths</th>
      <th>...</th>
      <th>trueDamageDealt</th>
      <th>trueDamageDealtToChampions</th>
      <th>trueDamageTaken</th>
      <th>turretKills</th>
      <th>turretsLost</th>
      <th>visionScore</th>
      <th>visionWardsBoughtInGame</th>
      <th>wardsKilled</th>
      <th>wardsPlaced</th>
      <th>win</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>0</td>
      <td>17</td>
      <td>62</td>
      <td>MonkeyKing</td>
      <td>8103</td>
      <td>29974</td>
      <td>8103</td>
      <td>27326</td>
      <td>5</td>
      <td>...</td>
      <td>10929</td>
      <td>1485</td>
      <td>1355</td>
      <td>7</td>
      <td>5</td>
      <td>26</td>
      <td>2</td>
      <td>5</td>
      <td>12</td>
      <td>True</td>
    </tr>
    <tr>
      <th>1</th>
      <td>8</td>
      <td>0</td>
      <td>15</td>
      <td>121</td>
      <td>Khazix</td>
      <td>467</td>
      <td>19758</td>
      <td>467</td>
      <td>20291</td>
      <td>11</td>
      <td>...</td>
      <td>9919</td>
      <td>187</td>
      <td>1275</td>
      <td>0</td>
      <td>5</td>
      <td>30</td>
      <td>3</td>
      <td>4</td>
      <td>5</td>
      <td>True</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7</td>
      <td>0</td>
      <td>17</td>
      <td>74</td>
      <td>Heimerdinger</td>
      <td>9467</td>
      <td>18869</td>
      <td>9467</td>
      <td>11781</td>
      <td>9</td>
      <td>...</td>
      <td>6207</td>
      <td>744</td>
      <td>723</td>
      <td>2</td>
      <td>5</td>
      <td>33</td>
      <td>3</td>
      <td>2</td>
      <td>14</td>
      <td>True</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5</td>
      <td>0</td>
      <td>14</td>
      <td>202</td>
      <td>Jhin</td>
      <td>1285</td>
      <td>4531</td>
      <td>1285</td>
      <td>8915</td>
      <td>11</td>
      <td>...</td>
      <td>410</td>
      <td>168</td>
      <td>1368</td>
      <td>0</td>
      <td>5</td>
      <td>14</td>
      <td>1</td>
      <td>2</td>
      <td>8</td>
      <td>True</td>
    </tr>
    <tr>
      <th>4</th>
      <td>10</td>
      <td>0</td>
      <td>13</td>
      <td>223</td>
      <td>TahmKench</td>
      <td>117</td>
      <td>1407</td>
      <td>117</td>
      <td>41249</td>
      <td>7</td>
      <td>...</td>
      <td>4240</td>
      <td>0</td>
      <td>2331</td>
      <td>1</td>
      <td>5</td>
      <td>55</td>
      <td>3</td>
      <td>5</td>
      <td>22</td>
      <td>True</td>
    </tr>
    <tr>
      <th>5</th>
      <td>11</td>
      <td>0</td>
      <td>14</td>
      <td>114</td>
      <td>Fiora</td>
      <td>370</td>
      <td>1471</td>
      <td>370</td>
      <td>16410</td>
      <td>8</td>
      <td>...</td>
      <td>20220</td>
      <td>4610</td>
      <td>324</td>
      <td>0</td>
      <td>10</td>
      <td>22</td>
      <td>2</td>
      <td>5</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>6</th>
      <td>8</td>
      <td>0</td>
      <td>16</td>
      <td>64</td>
      <td>LeeSin</td>
      <td>0</td>
      <td>14219</td>
      <td>0</td>
      <td>32768</td>
      <td>8</td>
      <td>...</td>
      <td>5689</td>
      <td>734</td>
      <td>357</td>
      <td>0</td>
      <td>10</td>
      <td>43</td>
      <td>13</td>
      <td>4</td>
      <td>20</td>
      <td>False</td>
    </tr>
    <tr>
      <th>7</th>
      <td>14</td>
      <td>0</td>
      <td>18</td>
      <td>8</td>
      <td>Vladimir</td>
      <td>1492</td>
      <td>1492</td>
      <td>1492</td>
      <td>14985</td>
      <td>8</td>
      <td>...</td>
      <td>1410</td>
      <td>1016</td>
      <td>728</td>
      <td>1</td>
      <td>10</td>
      <td>30</td>
      <td>3</td>
      <td>2</td>
      <td>15</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8</th>
      <td>16</td>
      <td>0</td>
      <td>17</td>
      <td>51</td>
      <td>Caitlyn</td>
      <td>11417</td>
      <td>17893</td>
      <td>11417</td>
      <td>10754</td>
      <td>8</td>
      <td>...</td>
      <td>2243</td>
      <td>693</td>
      <td>692</td>
      <td>3</td>
      <td>10</td>
      <td>18</td>
      <td>1</td>
      <td>2</td>
      <td>12</td>
      <td>False</td>
    </tr>
    <tr>
      <th>9</th>
      <td>16</td>
      <td>0</td>
      <td>16</td>
      <td>101</td>
      <td>Xerath</td>
      <td>1734</td>
      <td>1734</td>
      <td>1734</td>
      <td>7138</td>
      <td>6</td>
      <td>...</td>
      <td>276</td>
      <td>0</td>
      <td>483</td>
      <td>0</td>
      <td>10</td>
      <td>50</td>
      <td>0</td>
      <td>2</td>
      <td>28</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
<p>10 rows × 85 columns</p>
</div>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>WOW! That's a lot of columns! As you can see very many stats go into the game overall. These column names are given by Riot, and if I use one, I will explain its name if it is not apparent.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Data-Analysis-1:-Keep-Your-Friends-Close...">Data Analysis 1: Keep Your Friends Close...<a class="anchor-link" href="#Data-Analysis-1:-Keep-Your-Friends-Close...">&#182;</a></h2><p>We're finally in to the nitty-gritty of the project, where we, as Data Scientists, have to make sense of it all. There are a laundry list of things I could focus on such as overall win rate, win rate over time, Wards bought vs Wins, and more! First though, let's take a look at my lane partners: The Notorious ADCs. Attack Damage Carries (ADCs) are a class of champion typically played alongside supports in the bottom lane. In addition to these champions, there are also several flex picks (typically mages). Team Composition is one of the most important aspects of League, as many games can be decided before the game begins. Some teams pick a more balanced composition, while others may be extremely unbalanced or underpowered. Let's go through each game, find out who my lane partner was, and whether or not we won!</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[15]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">adc_dict</span> <span class="o">=</span> <span class="p">{}</span>
<span class="n">i</span> <span class="o">=</span> <span class="mi">0</span>
<span class="k">while</span> <span class="n">i</span> <span class="o">&lt;</span> <span class="mi">267</span><span class="p">:</span>
    <span class="c1"># The method in which one finds the ADC is easy, since they are always displayed next to me. In the above DF you can see</span>
    <span class="c1"># TahmKench as the championName in row 4. The ADC is always rowindex-1 compared to me. </span>
    <span class="nb">id</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">][</span><span class="s1">&#39;summonerName&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;OG Zoidberg&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">-</span><span class="mi">1</span>
    <span class="n">adc_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="p">]]</span>
    <span class="n">adc_name</span> <span class="o">=</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">4</span><span class="p">]</span>
    
    <span class="k">if</span> <span class="n">i</span> <span class="o">==</span> <span class="mi">199</span><span class="p">:</span>      <span class="c1"># SPECIAL CASE: KATARINA. Katarina swapped with my ADC leading to a mismatch in the dataframe.</span>
        <span class="nb">id</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">][</span><span class="s1">&#39;summonerName&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;OG Zoidberg&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">-</span><span class="mi">2</span>
        <span class="n">adc_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="p">]]</span>
        <span class="n">adc_name</span> <span class="o">=</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">4</span><span class="p">]</span>
        <span class="k">if</span> <span class="n">adc_name</span> <span class="ow">in</span> <span class="n">adc_dict</span><span class="p">:</span>
            <span class="n">tup</span> <span class="o">=</span> <span class="n">adc_dict</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">adc_name</span><span class="p">)</span>
            <span class="k">if</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">84</span><span class="p">]:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">,</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">)</span>
            
        <span class="k">else</span><span class="p">:</span>
            <span class="k">if</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">84</span><span class="p">]:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
    
    <span class="k">elif</span> <span class="n">i</span> <span class="o">==</span> <span class="mi">75</span><span class="p">:</span>     <span class="c1"># SPECIAL CASE: VOLIBEAR. Volibear swapped with my ADC leading to a mismatch in the dataframe.</span>
        <span class="nb">id</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">][</span><span class="s1">&#39;summonerName&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;OG Zoidberg&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">-</span><span class="mi">3</span>
        <span class="n">adc_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="p">]]</span>
        <span class="n">adc_name</span> <span class="o">=</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">4</span><span class="p">]</span>
        <span class="k">if</span> <span class="n">adc_name</span> <span class="ow">in</span> <span class="n">adc_dict</span><span class="p">:</span>
            <span class="n">tup</span> <span class="o">=</span> <span class="n">adc_dict</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">adc_name</span><span class="p">)</span>
            <span class="k">if</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">84</span><span class="p">]:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">,</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">)</span>
            
        <span class="k">else</span><span class="p">:</span>
            <span class="k">if</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">84</span><span class="p">]:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
    
    <span class="k">elif</span> <span class="n">i</span> <span class="o">&lt;</span> <span class="mi">200</span><span class="p">:</span>        <span class="c1"># Normal case pre-200</span>
        <span class="k">if</span> <span class="n">adc_name</span> <span class="ow">in</span> <span class="n">adc_dict</span><span class="p">:</span>
            <span class="n">tup</span> <span class="o">=</span> <span class="n">adc_dict</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">adc_name</span><span class="p">)</span>
            <span class="k">if</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">84</span><span class="p">]:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">,</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span> <span class="c1"># Increment both elements for a win</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">)</span>
            
        <span class="k">else</span><span class="p">:</span>
            <span class="k">if</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">84</span><span class="p">]:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
                
    <span class="k">else</span><span class="p">:</span>                <span class="c1"># For some reason there are less columns in the games after 0-199 in the list, need to take that into account.</span>
        <span class="k">if</span> <span class="n">adc_name</span> <span class="ow">in</span> <span class="n">adc_dict</span><span class="p">:</span>
            <span class="n">tup</span> <span class="o">=</span> <span class="n">adc_dict</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">adc_name</span><span class="p">)</span>
            <span class="k">if</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">80</span><span class="p">]:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">,</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">)</span>
            
        <span class="k">else</span><span class="p">:</span>
            <span class="k">if</span> <span class="n">adc_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">80</span><span class="p">]:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">adc_dict</span><span class="p">[</span><span class="n">adc_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
    
   
    <span class="n">i</span> <span class="o">+=</span> <span class="mi">1</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>After that long-winded algorithm we should have a dictionary containing each ADC, as well as the number of times I have played with them, and our wins. Notice how I used .iat for calling data. This meant I had to account for the change in number of columns. If you want less lengthy code you can just use .at with the column name in the second position. It's another way to compute the same thing, essentially.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[16]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">adc_wins</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="o">.</span><span class="n">from_dict</span><span class="p">(</span><span class="n">adc_dict</span><span class="p">,</span> <span class="n">orient</span><span class="o">=</span><span class="s1">&#39;index&#39;</span><span class="p">)</span>
<span class="n">adc_wins</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;wins&#39;</span><span class="p">,</span> <span class="s1">&#39;games_played&#39;</span><span class="p">]</span>
<span class="c1"># Renaming cols for accessibility.</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[17]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">adc_wins</span><span class="p">[</span><span class="s1">&#39;win_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="mf">0.0</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">adc_wins</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">adc_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;win_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="nb">float</span><span class="p">(</span><span class="n">adc_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;wins&#39;</span><span class="p">])</span><span class="o">/</span><span class="nb">float</span><span class="p">(</span><span class="n">adc_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;games_played&#39;</span><span class="p">])</span>
    
<span class="c1"># Calculating win percentage</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Let's plot the data! We can use a bar graph to plot the win rates per champion. We can use the built in plot method with pandas. To increase readability we can also specify labels for both axes as well as a title.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[18]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plot</span> <span class="o">=</span> <span class="n">adc_wins</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;win_rate&#39;</span><span class="p">,</span> <span class="n">xlabel</span><span class="o">=</span><span class="s1">&#39;Lane Partner&#39;</span><span class="p">,</span> <span class="n">ylabel</span><span class="o">=</span><span class="s1">&#39;Win Rate&#39;</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s2">&quot;Bottom Lane Partner Win Rates Across All Games&quot;</span><span class="p">)</span>
<span class="n">plot</span><span class="o">.</span><span class="n">axhline</span><span class="p">(</span><span class="n">y</span> <span class="o">=</span> <span class="mf">0.5</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;g&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[18]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;matplotlib.lines.Line2D at 0x7f556b096850&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Ta-da! This graph is a little bit misleading though, since the games played differ across all of the champions. We can calculate the appearance percentage for each champion.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[19]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">adc_wins</span><span class="p">[</span><span class="s1">&#39;appearance_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="mf">0.0</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">adc_wins</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">adc_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;appearance_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="nb">float</span><span class="p">(</span><span class="n">adc_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;games_played&#39;</span><span class="p">])</span><span class="o">/</span><span class="nb">float</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">df_list2</span><span class="p">))</span>
    
<span class="c1"># calculating appearance rate (games played against / total games)</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>There are many instances of champions with extremely low appearance rates. This is due to the current competitive "meta", in which people tend to play a handful of strong champions, while never playing others. In my case, Tahm Kench Support is very rare, since the <a href="https://leagueoflegends.fandom.com/wiki/Tahm_Kench/LoL/Patch_history">patch history</a> has not been particularly kind to him over the years, and his pick rate currently sits at <a href="https://u.gg/lol/champions/tahmkench/build?rank=overall&amp;role=support">0.4% in the support role across all ranks</a>. Let's just remove all of the champions that have less than a, say, 4 percent appearance rate as my lane partner. We can accumulate these in a list, and then make a copy of the original dataframe as to prevent indexing errors.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[20]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">champs_to_drop</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">adc_wins</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="k">if</span> <span class="n">adc_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;appearance_rate&#39;</span><span class="p">]</span> <span class="o">&lt;</span> <span class="mf">0.04</span><span class="p">:</span>
        <span class="n">champs_to_drop</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">index</span><span class="p">)</span>
        
<span class="n">new_adc_list</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="o">.</span><span class="n">copy</span><span class="p">(</span><span class="n">adc_wins</span><span class="p">)</span>
<span class="k">for</span> <span class="n">champ</span> <span class="ow">in</span> <span class="n">champs_to_drop</span><span class="p">:</span>
    <span class="n">new_adc_list</span> <span class="o">=</span> <span class="n">new_adc_list</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">champ</span><span class="p">)</span>
    
<span class="n">new_adc_list</span> <span class="c1"># let&#39;s see the &quot;most common&quot; ADCs in my games.</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[20]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>wins</th>
      <th>games_played</th>
      <th>win_rate</th>
      <th>appearance_rate</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Jhin</th>
      <td>20</td>
      <td>29</td>
      <td>0.689655</td>
      <td>0.108614</td>
    </tr>
    <tr>
      <th>Caitlyn</th>
      <td>12</td>
      <td>17</td>
      <td>0.705882</td>
      <td>0.063670</td>
    </tr>
    <tr>
      <th>Samira</th>
      <td>8</td>
      <td>12</td>
      <td>0.666667</td>
      <td>0.044944</td>
    </tr>
    <tr>
      <th>Kaisa</th>
      <td>11</td>
      <td>20</td>
      <td>0.550000</td>
      <td>0.074906</td>
    </tr>
    <tr>
      <th>Jinx</th>
      <td>9</td>
      <td>18</td>
      <td>0.500000</td>
      <td>0.067416</td>
    </tr>
    <tr>
      <th>Ezreal</th>
      <td>8</td>
      <td>11</td>
      <td>0.727273</td>
      <td>0.041199</td>
    </tr>
    <tr>
      <th>Ashe</th>
      <td>8</td>
      <td>19</td>
      <td>0.421053</td>
      <td>0.071161</td>
    </tr>
    <tr>
      <th>Tristana</th>
      <td>16</td>
      <td>27</td>
      <td>0.592593</td>
      <td>0.101124</td>
    </tr>
    <tr>
      <th>MissFortune</th>
      <td>17</td>
      <td>35</td>
      <td>0.485714</td>
      <td>0.131086</td>
    </tr>
    <tr>
      <th>Lucian</th>
      <td>5</td>
      <td>11</td>
      <td>0.454545</td>
      <td>0.041199</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[115]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plot2</span> <span class="o">=</span> <span class="n">new_adc_list</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;win_rate&#39;</span><span class="p">,</span> <span class="n">xlabel</span><span class="o">=</span><span class="s1">&#39;Lane Partner&#39;</span><span class="p">,</span> <span class="n">ylabel</span><span class="o">=</span><span class="s1">&#39;Win Rate&#39;</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s2">&quot;Most Frequent Partner Win Rates&quot;</span><span class="p">)</span>
<span class="n">plot2</span><span class="o">.</span><span class="n">axhline</span><span class="p">(</span><span class="n">y</span> <span class="o">=</span> <span class="mf">0.5</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;g&#39;</span><span class="p">)</span>
<span class="n">plot2</span> <span class="c1"># Plotting based on Win Rate</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[115]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;AxesSubplot:title={&#39;center&#39;:&#39;Most Frequent Partner Win Rates&#39;}, xlabel=&#39;Lane Partner&#39;, ylabel=&#39;Win Rate&#39;&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAYIAAAFJCAYAAACW1Sr+AAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjMuMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/Il7ecAAAACXBIWXMAAAsTAAALEwEAmpwYAAAs/UlEQVR4nO3deZgdZZn+8e9NDPsShTBqQkhUVJYBhLAOCaCCiGJcWAURFBl+sokr6KiMjoOi48KiERVEEUEEFTUjKCMhbJpEAhIUjRBNsyg7AVkSuH9/VHVy0jnd6SRddQ6p+3NdfeXUcup9zkl3PfUu9ZZsExERzbVapwOIiIjOSiKIiGi4JIKIiIZLIoiIaLgkgoiIhksiiIhouCSCiFiKpDGSHpM0rNOxRPWSCFYRkuZKelrSRn3Wz5JkSWNX8viW9LIBth8h6Zny5NH7c9bKlFknSWPLz/i8AfY5VdKC8rM9LOl6SbusYHlHSLp2xSNe7vIOkXRbn3W/7Gfdybb/Zntd28+sQFl7SHq2/J7mS7pd0pHL8f6rJR21vOXGiksiWLXcCRzSuyDpX4G1aiz/hvLk0ftzXN8dBjrRPkdcbHtdYCRwLXCZJC3PAer4DtpcyU8FNpc0siWGbYC1+6zbBbhmCEK4u/ye1gdOAr4h6RVDcNyoQBLBquW7wOEty+8EvtO6g6QNJH1H0n2S/irpPyStVm57maSpkh6RdL+ki8v1vSeGm8urvIMGG1B5Ff1DSRdIehQ4oozhW5LukXSXpP/qPXFJGibpC2X5d0g6tvVKvaz5vLbP8S9oWd65vFJ/WNLNkvZo2Xa1pE9Luq68Ur2ypQbV+xkfLj/jgFf6thcA5wMvBDaUdLKkv5THvU3SW1rKPaIs80uSHgQuBiYDu/TWLsr9vi3pbEk/L4/zG0kvbTnOK8sr9gfLq+wDW7Z9W9LXJE2R9DiwZ5947wbuACaWq7YDZlMkiNZ1qwEz+taQlvHdDfQ92fYU4EFg6/JYz5f0s/J38KHy9ehy22eACcBZaqlVLuOz71t+5/PL36cPLiuuWFISwarlRmB9SZuXJ9aDgAv67HMmsAHwEmB3isTRW23/NHAl8HxgdLkvtntPFNuUV/oXL2dck4AfAiOA71GcQBcCLwNeBewN9DYFvAd4Y7l+PLD/YAuRNAr4OfBfwAuADwKX9l7xlt5O8Xk3BlYv94HFJ8MR5We8YRllrQEcAfTYvh/4C8UJbAPgP4ELJL2o5S07UZyINwYOA45hcQ1qRMt+h5Tvfz4wB/hMWd46wC+BC8tjHAJ8VdKWfT7bZ4D1KGorfV3T8jknAtPK/VrX3Wj76X4+dn/fXb8krSbpTcBG5eeB4rxzHrApMAZ4AjgLwPbHyriO661VDuKzfwv4d9vrAVsB/7esuGJJSQSrnt5awV7AH4G7eje0JIdTbM+3PRf4H+Ad5S4LKP44X2z7SdvL24a9c3kl3vuzc7n+Bts/tv0sRVPB64H32X7c9j+ALwEHl/seCHzZ9jzbDwKnLUf5hwFTbE+x/aztXwIzgH1b9jnP9p9sPwH8ANh2OT/jgeUV/Dxge+DNALYvsX13We7FwJ+BHVved7ftM20vLMvuz2W2f2t7IUXS7I3vjcBc2+eVx/gdcClLJsqf2L6ujOHJNsduvfqfQHHCndZn3dQBYlue7+7F5ff0BPAj4P22bwKw/YDtS23/0/Z8iuS1+wDHWtZnXwBsIWl92w+V22M5JBGser5LceV2BH2ahSiuylYH/tqy7q/AqPL1hwEBv5U0W9K7lrPsG22PaPm5sVw/r2WfTYHhwD29CQP4OsWVHsCL++zfGuuybAoc0JqMgN2A1ivze1te/xNYdzmOD/CD8rNtbPvVtmcCSDpcRcd8b7lbUXzfvea1O1gb/cW3KbBTn892KEXT1GDLuAbYWtLzgZ0pEvQfgReV63Zj4P6B5fnu7i5rOusDZwCv7t0gaW1JX1fRNPloWeYI9T9CaVmf/W0Uyf6vKpo2V6gDv8me6x130Yftv0q6k+IP4919Nt/P4qv+3tEiYyhrDbbvpWiaQdJuwK8kXWN7DiundYrbecBTwEblVW9f9wCbtCyP6bP9cWDtluW+J8Lv2n7PSsa4XCRtCnwDeA3FyfUZSbMokmp/x1/e8uYBU23vNcA+Ax7T9h2S7gaOBv5m+7Fy0w3lunUpmheHjO2nJH0EuF3Sm23/GPgA8ApgJ9v3StoWuInF31ffzzHgZ7c9HZgkaThwHEVtZZN2+0Z7qRGsmt4NvNr2460ry6GAPwA+I2m98gT2fsp+BEkH9HbaAQ9R/EH2Dh/8O0W/wkqxfQ9FP8T/SFq/bEN+qaTepoEfACdIGl1epZ7c5xCzgIMlDZfUtw/hAmA/Sa9T0em8poqhjKNZtvuAZ1mxz7gOxXd1H4CKoZJbLeM9fwdGS1p9kGX8DHi5pHeUn324pB0kbb6csU6j+D+f1rLu2nLdjGU0W62Qss/hf4BPlKvWo2gyeljSC4BP9nlL39+1fj+7pNUlHSppg7ID/1EW/87GICURrIJs/8X2jH42H09xVX0HxQngQuDcctsOwG8kPQZcDpxo+85y26nA+WXV/EBWzuEUTVS3USScH7K4+eYbwBXAzcDvgMv6vPfjwEvL9/1nGT8AtudRdEx/lOKkPA/4EIP4Pbf9T4q26uv69G8sk+3bKE50N1CcxP4VuG4Zb/s/ilE790q6fxBlzKfoVD8YuJuimeZzwBqDjbM0laIZrrX/Z1q5biiGjfbnXGCMpP2AL1MMa76fogbyiz77fgXYvxxRdMYgPvs7gLllM9MxFH1FsRyUB9NEN1NxI9ydwPB+mpIiYiWlRhAR0XBJBBERDZemoYiIhkuNICKi4ZIIIiIa7jl3Q9lGG23ksWPHdjqMiIjnlJkzZ95ve2S7bc+5RDB27FhmzOhviHxERLQjqd/pWtI0FBHRcEkEERENl0QQEdFwz7k+gohohgULFtDT08OTT7Z7tEL0Z80112T06NEMHz580O9JIoiIrtTT08N6663H2LFj0fI9FrqxbPPAAw/Q09PDuHHjBv2+NA1FRFd68skn2XDDDZMEloMkNtxww+WuRSURRETXShJYfivynSURREQ0XPoIImo09uSfr/Qx5n72DUMQyXPPUHx3rYbie9x333258MILGTFixMoH1MbVV1/N6quvzq677lrJ8XulRhARsYKmTJmy0klg4cL+n7d09dVXc/3116/U8QcjiSAioh+nn346Z5xxBgAnnXQSr371qwG46qqrOOywwxg7diz3338/c+fOZfPNN+c973kPW265JXvvvTdPPNH/45/32GMPPvrRj7L77rvzla98hZ/+9KfstNNOvOpVr+K1r30tf//735k7dy6TJ0/mS1/6Ettuuy3Tpk3jvvvu421vexs77LADO+ywA9ddt6wnog5OEkFERD8mTpzItGnTAJgxYwaPPfYYCxYs4Nprr2XChAlL7PvnP/+ZY489ltmzZzNixAguvfTSAY/98MMPM3XqVD7wgQ+w2267ceONN3LTTTdx8MEHc/rppzN27FiOOeYYTjrpJGbNmsWECRM48cQTOemkk5g+fTqXXnop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
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>The above graph shows my win rates with the current "meta" ADCs that I have to partner up with. As you can see, my win rate is the highest when I play with Ezreal, but that's only across 11 games! My most common partner is Miss Fortune, with a 13 percent appearance rate, but with a sub-50 percent win rate, which is considered bad by the community at large. As such, I have placed a line at y=0.5 in order to clarify which win rates are considered good and which are considered subpar. The second highest partner in my match history is Jhin, and with an astounding win rate of nearly 69 percent, it's no surprise as to why he has one of the highest pick rates for the role, at 17.3% in Silver and 16.4% in Platinum+ (considered the highest echelon of non-pro play). These stats were found on <a href="https://u.gg/lol/champions/jhin/build?rank=silver">U.GG</a>.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Data-Analysis-2:-...And-Your-Enemies-Closer">Data Analysis 2: ...And Your Enemies Closer<a class="anchor-link" href="#Data-Analysis-2:-...And-Your-Enemies-Closer">&#182;</a></h2><p>Matchups and synergies play a huge role in the League of Legends. Good players know all of the best and worst matchups for their champion, and especially who to ban during the champion selection phase. However, each player only gets one ban, so if your champion has many counters, you might have to take the risk, depending on who picks their champion first. The next questions I want to answer are "Who am I the best against?" and "Who am I worst against?" When someone asks me these questions I have some instinctual answers based on my personal experiences, but let's see what the numbers have to say.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We can answer both of these questions at the same time. Using a similar methodology as above we can find the enemy supports, as they are always listed as the last row for their team, unless someone swapped in champion select. Like above, we can pretty easily find out in which games that took place.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[22]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Essentially the same code as above, but with less error cases (index 92) and different var names.</span>
<span class="n">supp_dict</span> <span class="o">=</span> <span class="p">{}</span>
<span class="n">i</span> <span class="o">=</span> <span class="mi">0</span>
<span class="k">while</span> <span class="n">i</span> <span class="o">&lt;</span> <span class="mi">267</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">i</span> <span class="o">==</span> <span class="mi">92</span><span class="p">:</span> <span class="c1"># Special case: Jhin and Swain swapped. I believe they were a duo.</span>
        <span class="nb">id</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">][</span><span class="s1">&#39;summonerName&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;OG Zoidberg&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">+</span><span class="mi">4</span>
        <span class="n">supp_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="p">]]</span>
        <span class="n">supp_name</span> <span class="o">=</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">4</span><span class="p">]</span>
        <span class="k">if</span> <span class="n">supp_name</span> <span class="ow">in</span> <span class="n">supp_dict</span><span class="p">:</span>
            <span class="n">tup</span> <span class="o">=</span> <span class="n">supp_dict</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">supp_name</span><span class="p">)</span>
            <span class="k">if</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">84</span><span class="p">]:</span>
                <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">,</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">)</span>
            
        <span class="k">else</span><span class="p">:</span>
            <span class="k">if</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">84</span><span class="p">]:</span>
                <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
            <span class="k">else</span><span class="p">:</span>
                <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
    <span class="k">else</span><span class="p">:</span>
        
        <span class="nb">id</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">][</span><span class="s1">&#39;summonerName&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;OG Zoidberg&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
        <span class="n">supp_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="p">]]</span>
        <span class="n">supp_name</span> <span class="o">=</span> <span class="s2">&quot;&quot;</span>
        <span class="k">if</span> <span class="nb">id</span> <span class="o">==</span> <span class="mi">4</span><span class="p">:</span>
            <span class="n">supp_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="o">+</span><span class="mi">5</span><span class="p">]]</span>
            <span class="n">supp_name</span> <span class="o">=</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">4</span><span class="p">]</span>
        
        <span class="k">else</span><span class="p">:</span>
            <span class="n">supp_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="o">-</span><span class="mi">5</span><span class="p">]]</span>
            <span class="n">supp_name</span> <span class="o">=</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">4</span><span class="p">]</span>
        
        
        <span class="k">if</span> <span class="n">i</span> <span class="o">&lt;</span> <span class="mi">200</span><span class="p">:</span>
            <span class="k">if</span> <span class="n">supp_name</span> <span class="ow">in</span> <span class="n">supp_dict</span><span class="p">:</span>
                <span class="n">tup</span> <span class="o">=</span> <span class="n">supp_dict</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">supp_name</span><span class="p">)</span>
                <span class="k">if</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">84</span><span class="p">]:</span>
                    <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
                <span class="k">else</span><span class="p">:</span>
                    <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">,</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">)</span>
            
            <span class="k">else</span><span class="p">:</span>
                <span class="k">if</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">84</span><span class="p">]:</span>
                    <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
                <span class="k">else</span><span class="p">:</span>
                    <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
                
        <span class="k">else</span><span class="p">:</span>
            <span class="k">if</span> <span class="n">supp_name</span> <span class="ow">in</span> <span class="n">supp_dict</span><span class="p">:</span>
                <span class="n">tup</span> <span class="o">=</span> <span class="n">supp_dict</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">supp_name</span><span class="p">)</span>
                <span class="k">if</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">80</span><span class="p">]:</span>
                    <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
                <span class="k">else</span><span class="p">:</span>
                    <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">,</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">)</span>
            
            <span class="k">else</span><span class="p">:</span>
                <span class="k">if</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">iat</span><span class="p">[</span><span class="mi">0</span><span class="p">,</span><span class="mi">80</span><span class="p">]:</span>
                    <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
                <span class="k">else</span><span class="p">:</span>
                    <span class="n">supp_dict</span><span class="p">[</span><span class="n">supp_name</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
                
    <span class="n">i</span><span class="o">+=</span><span class="mi">1</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Nice, we have the data we need for the enemy supports now. First, I'd like to compare the amount of different ADCs I've played with vs the amount of supports I've played against.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[23]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">len</span><span class="p">(</span><span class="n">adc_dict</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[23]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>25</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[24]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">len</span><span class="p">(</span><span class="n">supp_dict</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[24]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>46</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>That's nearly double! There is a huge issue of diversity in the types of champions played in the bottom role, but less so for support. With that out of the way, let's see the overall win rates I have against these opponents. First let's calculate the win rates, then plot them as above.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[25]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">supp_wins</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="o">.</span><span class="n">from_dict</span><span class="p">(</span><span class="n">supp_dict</span><span class="p">,</span> <span class="n">orient</span><span class="o">=</span><span class="s1">&#39;index&#39;</span><span class="p">)</span>
<span class="n">supp_wins</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;wins_against&#39;</span><span class="p">,</span> <span class="s1">&#39;games_played_against&#39;</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[26]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">supp_wins</span><span class="p">[</span><span class="s1">&#39;win_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="mf">0.0</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">supp_wins</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">supp_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;win_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="nb">float</span><span class="p">(</span><span class="n">supp_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;wins_against&#39;</span><span class="p">])</span><span class="o">/</span><span class="nb">float</span><span class="p">(</span><span class="n">supp_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;games_played_against&#39;</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[27]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plot</span> <span class="o">=</span> <span class="n">supp_wins</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;win_rate&#39;</span><span class="p">,</span> <span class="n">xlabel</span><span class="o">=</span><span class="s1">&#39;Lane Opponent&#39;</span><span class="p">,</span> <span class="n">ylabel</span><span class="o">=</span><span class="s1">&#39;Win Rate&#39;</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s2">&quot;Support Opponent Win Rates Across All Games&quot;</span><span class="p">)</span>
<span class="n">plot</span><span class="o">.</span><span class="n">axhline</span><span class="p">(</span><span class="n">y</span> <span class="o">=</span> <span class="mf">0.5</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;g&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[27]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;matplotlib.lines.Line2D at 0x7f55c85cbaf0&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>This graph is too visually noisy to be useful. We can clean it up by using appearance rate again.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[28]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">supp_wins</span><span class="p">[</span><span class="s1">&#39;appearance_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="mf">0.0</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">supp_wins</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">supp_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;appearance_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="nb">float</span><span class="p">(</span><span class="n">supp_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;games_played_against&#39;</span><span class="p">])</span><span class="o">/</span><span class="nb">float</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="n">df_list2</span><span class="p">))</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>For this, let's say anything below 2.5 percent can be dropped. I chose this number because one of the champions with the lowest appearance rates in the below DataFrame is Lulu, who is very much a "meta" champion, especially in higher ranks. I thought it would be best to use this percentage as to incorporate some of the more popular champions in this role.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[29]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">champs_to_drop</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">supp_wins</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="k">if</span> <span class="n">supp_wins</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;appearance_rate&#39;</span><span class="p">]</span> <span class="o">&lt;</span> <span class="mf">0.025</span><span class="p">:</span>
        <span class="n">champs_to_drop</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">index</span><span class="p">)</span>
        
<span class="n">new_supp_list</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="o">.</span><span class="n">copy</span><span class="p">(</span><span class="n">supp_wins</span><span class="p">)</span>
<span class="k">for</span> <span class="n">champ</span> <span class="ow">in</span> <span class="n">champs_to_drop</span><span class="p">:</span>
    <span class="n">new_supp_list</span> <span class="o">=</span> <span class="n">new_supp_list</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">champ</span><span class="p">)</span>
    
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[30]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plot3</span> <span class="o">=</span> <span class="n">new_supp_list</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;bar&#39;</span><span class="p">,</span> <span class="n">y</span><span class="o">=</span><span class="s1">&#39;win_rate&#39;</span><span class="p">,</span> <span class="n">xlabel</span><span class="o">=</span><span class="s1">&#39;Lane Opponent&#39;</span><span class="p">,</span> <span class="n">ylabel</span><span class="o">=</span><span class="s1">&#39;Win Rate&#39;</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s2">&quot;Support Opponent Win Rates Across All Games for Popular Supports&quot;</span><span class="p">)</span>
<span class="n">plot3</span><span class="o">.</span><span class="n">axhline</span><span class="p">(</span><span class="n">y</span> <span class="o">=</span> <span class="mf">0.5</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;g&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[30]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;matplotlib.lines.Line2D at 0x7f5562cece50&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>According to this graph, I'm best against Sona and worst against Lulu. Sona is considered to be very weak right now, so the fact that she typically loses games is not surprising. However, according to U.GG, <a href="https://u.gg/lol/champions/sona/build?rank=silver&amp;opp=tahmkench">she has a win rate of 57.75 against Tahm Kench across 213 games</a>, so perhaps I am the exception, not the rule. I consider Lulu, Senna, and Brand to be my worst matchups, and given my match history this is corraborated. Lulu is the lowest at 1 win across 7 games, followed by Brand at 2 wins across 9 games, and finally Senna at 6 wins across 15 games. As a result of playing against Senna, who is much more common compared to the former two, I started banning her in nearly all of my games. Some surprises here are my above-50% win rates against high-damage mages like Swain, Lux, and Seraphine, as well as my low win rates against Pyke and Nautilus, which are both matchups I typically consider even and/or in my favor, at least when I play Tahm Kench. With this information I can play safer in future games in matchups like these.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Data-Anaylsis-3:-Participation-is-Important">Data Anaylsis 3: Participation is Important<a class="anchor-link" href="#Data-Anaylsis-3:-Participation-is-Important">&#182;</a></h2><p>Okay, well those are pretty simple representations of exploratory data analysis. Let's look at something that requires some hypothesis testing and machine learning. Let's take a look at something that many supports consider to be an important metric of performance: Kill Participation (KP). It's a simple metric, being only the sum of kills and assists, with the latter being more important due to the fact that supports typically want to give their carries the kills, because of gold rewards.</p>
<h3 id="Getting-the-data-Together">Getting the data Together<a class="anchor-link" href="#Getting-the-data-Together">&#182;</a></h3><p>We need to figure out how to get a list of win rates per KP number. To find the range though, we can just find the lowest KP and the highest KP and display them.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[31]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">kp_dict</span> <span class="o">=</span> <span class="p">{}</span>
<span class="c1"># Looping through the games and recording my Kill Participation and if I won the game. Stored in a dict.</span>
<span class="k">for</span> <span class="n">game</span> <span class="ow">in</span> <span class="n">df_list2</span><span class="p">:</span>
    <span class="nb">id</span> <span class="o">=</span> <span class="n">game</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">game</span><span class="p">[</span><span class="s1">&#39;summonerName&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;OG Zoidberg&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
    <span class="n">assists</span> <span class="o">=</span> <span class="n">game</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="p">,</span> <span class="s1">&#39;assists&#39;</span><span class="p">]</span>
    <span class="n">kills</span> <span class="o">=</span> <span class="n">game</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="p">,</span> <span class="s1">&#39;kills&#39;</span><span class="p">]</span>
    <span class="n">kp</span> <span class="o">=</span> <span class="n">kills</span><span class="o">+</span><span class="n">assists</span>
    <span class="k">if</span> <span class="n">game</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="p">,</span> <span class="s1">&#39;win&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="kc">True</span><span class="p">:</span>
        <span class="k">if</span> <span class="n">kp</span> <span class="ow">in</span> <span class="n">kp_dict</span><span class="p">:</span>
            <span class="n">tup</span> <span class="o">=</span> <span class="n">kp_dict</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">kp</span><span class="p">)</span>
            <span class="n">kp_dict</span><span class="p">[</span><span class="n">kp</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">+</span><span class="mi">1</span><span class="p">,</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span> <span class="c1"># Using the tuple method as before</span>
        <span class="k">else</span><span class="p">:</span>
            <span class="n">kp_dict</span><span class="p">[</span><span class="n">kp</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">1</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
            
    <span class="k">elif</span> <span class="n">game</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="p">,</span> <span class="s1">&#39;win&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="kc">False</span><span class="p">:</span>
        <span class="k">if</span> <span class="n">kp</span> <span class="ow">in</span> <span class="n">kp_dict</span><span class="p">:</span>
            <span class="n">tup</span> <span class="o">=</span> <span class="n">kp_dict</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">kp</span><span class="p">)</span>
            <span class="n">kp_dict</span><span class="p">[</span><span class="n">kp</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="n">tup</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">tup</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">+</span> <span class="mi">1</span><span class="p">)</span>
        <span class="k">else</span><span class="p">:</span>
            <span class="n">kp_dict</span><span class="p">[</span><span class="n">kp</span><span class="p">]</span> <span class="o">=</span> <span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="mi">1</span><span class="p">)</span>
            
<span class="n">kp_df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="o">.</span><span class="n">from_dict</span><span class="p">(</span><span class="n">kp_dict</span><span class="p">,</span> <span class="n">orient</span><span class="o">=</span><span class="s1">&#39;index&#39;</span><span class="p">)</span>
<span class="n">kp_df</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;game_won&#39;</span><span class="p">,</span> <span class="s1">&#39;games_ocurred&#39;</span><span class="p">]</span>
<span class="n">kp_df</span> <span class="o">=</span> <span class="n">kp_df</span><span class="o">.</span><span class="n">sort_index</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>This was just one way to do it. You could also just loop through all of the games and change the numbers in a pre-made DataFrame. I chose to do it this way since it makes sense to me. If you think of a better way of finding the same information, by all means, pursue that approach.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[32]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">kp_df2</span> <span class="o">=</span> <span class="n">kp_df</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">kp_df2</span><span class="p">[</span><span class="s1">&#39;win_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="mf">0.0</span>
<span class="n">kp_df2</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;kill_participation&#39;</span><span class="p">,</span><span class="s1">&#39;game_won&#39;</span><span class="p">,</span><span class="s1">&#39;games_ocurred&#39;</span><span class="p">,</span><span class="s1">&#39;win_rate&#39;</span><span class="p">]</span>
<span class="c1"># Calculating win rate for each KP number.</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">kp_df2</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">kp_df2</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;win_rate&#39;</span><span class="p">]</span> <span class="o">=</span> <span class="nb">float</span><span class="p">(</span><span class="n">kp_df2</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;game_won&#39;</span><span class="p">])</span><span class="o">/</span><span class="nb">float</span><span class="p">(</span><span class="n">kp_df2</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;games_ocurred&#39;</span><span class="p">])</span>
    
<span class="n">kp_df2</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;scatter&#39;</span><span class="p">,</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;kill_participation&#39;</span><span class="p">,</span><span class="n">y</span><span class="o">=</span><span class="s1">&#39;win_rate&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[32]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;AxesSubplot:xlabel=&#39;kill_participation&#39;, ylabel=&#39;win_rate&#39;&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Excellent, we have a plot of win rate against KP now. You may notice a few outliers, like the 33 KP with 0 percent win rate, or the 50% win rate for 0 KP. For the former, it was an unusually long game that was even for both teams. For the latter, I did some research into those games and found out those were both remakes. A Remake is when someone on either team disconnects, allowing the team with the disconnecting player to surrender as soon as the game starts, preventing a loss in rank. However, the games are still recorded in the database as win or loss. Both 0 KP games were remakes, one of which had a teammate of mine disconnect. Anyways, let's fit a line to this graph. Let's first try linear regression to see how well it fits. Let's use Numpy's polyfit feature alongside <a href="https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html">matplotlib's pyplot</a>.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[34]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">kp_df2</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">kind</span><span class="o">=</span><span class="s1">&#39;scatter&#39;</span><span class="p">,</span><span class="n">x</span><span class="o">=</span><span class="s1">&#39;kill_participation&#39;</span><span class="p">,</span><span class="n">y</span><span class="o">=</span><span class="s1">&#39;win_rate&#39;</span><span class="p">)</span>
<span class="n">X</span><span class="o">=</span><span class="n">kp_df2</span><span class="p">[</span><span class="s1">&#39;kill_participation&#39;</span><span class="p">]</span>
<span class="n">y</span><span class="o">=</span><span class="n">kp_df2</span><span class="p">[</span><span class="s1">&#39;win_rate&#39;</span><span class="p">]</span>
<span class="n">m</span><span class="p">,</span> <span class="n">b</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">polyfit</span><span class="p">(</span><span class="n">X</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span> <span class="c1"># Coefficients 0.01916738 and 0.22667317</span>

<span class="n">mpl</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">X</span><span class="p">,</span> <span class="n">m</span><span class="o">*</span><span class="n">X</span> <span class="o">+</span> <span class="n">b</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;g&#39;</span><span class="p">)</span> <span class="c1"># plots the line, making it green</span>
<span class="c1"># Let&#39;s make the graph a bit prettier.</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">&quot;Kill Participation&quot;</span><span class="p">)</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">&quot;Win Rate&quot;</span><span class="p">)</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;Kill Participation (kills + assists) Against Win Rate&quot;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[34]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>Text(0.5, 1.0, &#39;Kill Participation (kills + assists) Against Win Rate&#39;)</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAYIAAAEWCAYAAABrDZDcAAAAOXRFWHRTb2Z0d2FyZQBNYXRwbG90bGliIHZlcnNpb24zLjMuMywgaHR0cHM6Ly9tYXRwbG90bGliLm9yZy/Il7ecAAAACXBIWXMAAAsTAAALEwEAmpwYAAA270lEQVR4nO3dd3wUdfrA8c+TEIqAdJUqKIgKAmoEpdkVG2D5ifU8vLN3DynGO/UMXVEQEVEUC4gF23l6eqenhCYEhEhTiiABEQihBEhIeX5/zMRbwibZJDuZ3ezzfr3ySnbKd575Znefme98Z76iqhhjjIldcX4HYIwxxl+WCIwxJsZZIjDGmBhnicAYY2KcJQJjjIlxlgiMMSbGWSIohoi0EpEsEYl3X38jIn92//6jiMzxKa5eIvJjCMvdKCJfehTDIXXjQflvi0h/9+9i67roPoqIikhb9+9pIpLsRXyVQURWiMg5YSyvhoisFpGjwlVmGbfv6XumvETkURF5xe84/BbTiUBENojIBQGvrxORTBE5W1V/UdU6qppfxjJbu19IWe7PBhEZWoEYf/9yA1DVFFVtX9p6qjpdVS8q73aLxHBIPZW3bkLcViegM/BxacuGcx8jjap2UNVvSlom4L1WLYTycoBXgSGlLesmXxWRa0MOuPTth+U9E3hAVsz8L0RkcMDr5u6+BJt2jKqOUNViyysllmkictD9nO8UkX+LyIkhrhvy/64yxHQiCCQitwAvAJep6rdhKLK+qtYBrgf+JiJ9yhhPRLxBfHAHMF0j4E5H94P+R7/jCKMZwC0iUqOU5W4Bdrq/o81s4OyA172B1UGmrVHVrWHY3hj3c94c2AxMDUOZlc4SASAitwPPABer6jx3WlgytqrOB1YAHUWkq4jMF5FdIvKriEwUkeoBcaiI3CMia4A1IjLbnbXMPeoYICLniEh6wDotReQDEdkuIhkiMtGdfkiTilv2/SKyXkR2iMhYEYlz5x0vIl+76+8QkekiUt+d9ybQCviHG8PgonUjIs1E5BP3qGitiNwWsN0nRORdEXlDRPa6TR6JJVTZJUCxidiNe46I1Cup2ajIOo1F5FO33neKSErhvoeLiLwnIltFZLeIzBaRDgHzLhWRle7+bxaRQaXFFXgW5r5vUkVkj4j8JiLj3KIL3x+73P/NWSLSVkS+dePYISLvFMahqulAJnBmCftxLM6X5u3AxSJydJH5g9337hYR+bMc2hx3mYh878a5SUSeCFiv6HvmGxF5SkTmuvXypYg0dufVFJG33PfjLhFZJCJHi8hwoBcw0d3fiUF2YTbQI+D/2wt4DkgsMm22u60nROStIjHeIiK/uPWXVFxdBVLVA8C7QJeAfS62Pgjyv3PXuVVEVonTMvGF+//wnCUCuAt4CjhfVVPDWbA4egAdgO+BfOAhoDFwFnA+cHeR1foD3YCTVbW3O62ze1r9TuCC4rS3fgpsBFrjHJXMLCGkK4FE4DSgH3BrYVHASKAZcBLQEngCQFVvBn4BrnBjGBOk3LeBdHf9a4ARInJ+wPy+blz1gU+AYB9gRKQ20AY47BqIiMSJyMtAJ+AiVd1dwn4W9Rc3vibA0cCjQLjPOD4H2gFHAUuA6QHzpgJ3qGpdoCPwdRnjGg+MV9UjgeNxvnDAObIF9+zTPeh4CvgSaAC0AJ4vUtYqnKa34vwBSFXVWe6yNxbOEOes9mHgAqAthx5lA+xz168PXAbcJe61nmLcAAzEqbPqwCB3+i1APZz3YSPgTuCAqiYBKcC97v7eG6TMhUCNgH3sDfwbWFtk2uzDV/1dT6A9zufzbyJyUgnLAr+/d693t1OopPo47H/nznsUuArnPZGC89nynCUCuBBYAPwQ5nJ34JxevwIMVdWvVHWxqi5Q1TxV3QC8xOEfppGqutM9wihNV5wv30dUdZ+qZqtqSUfIo92yf8E5SroeQFXXquq/VTVHVbcD44LEFZSItMT54Axxt7/U3eebAxabo6qfue3Db1L8F1F99/feItMTcD4QDXES0v5QYguQCzQFjlXVXPc6S1gTgaq+qqp73bb4J4DOIlIvYPsni8iRqpqpqkvKGFcu0FZEGqtqlqouKCGUXOBYoFkx74e9/K+eg/kDThMS7u/A5qFrgddUdYX7P3gycEVV/UZVf1DVAlVNw/mflfQ+ek1VfwpyNJ2LkwDaqmq++7nZU0I5gTHkAN8BvUWkIc4X7XqcL9XCaSdTwlkn8KSqHlDVZcAySk6cg0RkF0699iTgfV+O+rgD5/O/SlXzgBFAl8o4K7BE4BxtnAC8IiISxnIbq2oDVT1JVScAiMgJblPAVhHZg/OPblxkvU1l2EZLYKP7pglFYNkbcZIIInKUiMx0my32AG8Fias4zYCdqhr45b0R5+ykUGBb7H6gpgRvctvl/q5bZHpbnDOYJ1X1YIhxBRqLc6T2pThNY8VevBeRNLc5YhfOEeukwtciMqmYdeJFZJSIrHPrb4M7q7AOrwYuBTa6zTZnlTGuP+G8R1e7zSSXl7Cvg3HO8BaK0wx3a5H5dflfPRfdjx44Z2SFZ5UzgFNEpIv7uhmHvocOea+KSDcR+a84zZS7cT5bJb2Pir4v6rh/vwl8Acx0m6DGiEhCCeUUNRvniLsXUJgI5wRM26SqG8sRVzBPq2p9nDPyAzhnEkC56uNYYHzA+28nzv+yeQnrhIUlAtiGcwrYCwj6QQ+jF3EuXLVzT/MfxflHByrLkeomoFUxX6rBtAz4uxWwxf17pLvdTm5cNxWJq6SYtgANRSTwy7sVzoWzMlHVfcA6nC+9QKtwmhA+F5FSe0wFKXevqv5FVY8DrgAeLtJ0FbhsJ1Wt7364ZwB3F75W1aLNeIVuwElUF+A0abR2p4tb5iJV7YfTBPIRbtNOqHGp6hpVvd5dfzTwvtsUcdj/RVW3quptqtoM5whzkgT0OsNp+ltWzH7c4sa8VES24hxZg3OWAPArTnNTocD3Ezj19QnQUlXrAZM5/P1dKvfs6ElVPRnoDlweEEMon4/ZOJ/n3jhnAgBzgR6U3ixULu5Z9gM4X+S13Mkl1Uew/diE04RYP+CnVuF1Sy9ZIgBUdQtwHtBHRJ71cFN1gT1AljjdzO4KYZ3fgOOKmbcQ58M5SkRquxfZepRQ1iMi0sBtznkAKLzmUBfIwrlw1Rx4JNQYVHUTMA8Y6W6/E84R7PRgy4fgM4KcPqvq2ziJ8z8icnxZChSRy8W5iCo49Z/v/oRLXSAHyACOwDnTK9x2dXHud6inqrkB2w85LhG5SUSaqGoB/zuazwe2AwUE/G9E5P9EpPDLOhPnC6dwe81xmtcOa1oSkZo4TT+34zTRFP7cB9zoHmy8CwwUkZNE5Ajgb0HqYaeqZotIV5wEWWYicq6InOJeA9uD01RUWC8lfR4KzcNp/roJNxGoaiZOfd2EB4nA3ca/cQ6MbncnlVQfh/3vcBLFMHE7GojTIeL/vIi1KEsELvcL7TzgGhEZ6dFmBuG8GfYCL/O/L+KSPAG87p4uHtKv221zvwKn6eQXnAuPA0oo62NgMbAU+Cf/6+r2JM4F5N3u9A+KrDcSeMyNYRCHux7nKHgL8CHwuPuhKI8pOF88hx1JqurrwN+Br0WkdRnKbAf8ByfZzQcmaSl99MvoDZzmsM3ASg7/or0Z2OA2G92J82VUlrj6ACtEJAvnwvF1bvv/fmA4MNf935wJnAF85y77CfCAqv7slnMD8Lrbjl5Uf5ymjTfcs4qt6nSvnArEA31U9XNgAvBfnCat+e66heXdDfxdRPbiJIl3KZ9jgPdxksAqnPb8t9x543E+o5kiMiHYym69LMa5aLw8YFYKzlmVJ4nANRYYLE4X3WLrI9j/TlU/xDnjm+m+V5bj9KLznIT5mpmJUCKiOE1Sa0td2GciMgN4V1U/8juWqsL9YloG9FbVbWEq8yScL6saZbhOZSKQJYIYEU2JwEQuEbkS56yxNvA6UKCq/X0NylSYNQ0ZY8riDpz27XU47fahXOcyEc7OCIwxJsbZGYExxsS4qHuwWePGjbV169Z+h2GMMVFl8eLFO1S1SbB5UZcIWrduTWpqWB8JZIwxVZ6IFHs3tTUNGWNMjLNEYIwxMc4SgTHGxDhLBMYYE+MsERhjTIzzLBGIyKsisk1ElhczX0RkgjhDG6aJyGlexWKMCV1GVg7LNu0iIyvYs+lKn+/19r3k976XxMtte9l9dBrOkIRvFDP/EpynL7bDGZrxRfe3McYnHy/dzJBZaSTExZFbUMCYqzvRt0vzkOd7vX0v+b3vFYmtojw7I1DV2Tgj7BSnH84jb9Udeq++iDT1Kh5jTMkysnIYMiuN7NwC9ubkkZ1bwOBZab8fgZY23+vte8nvfa9IbOHg5zWC5hw61F06xQzJJiK3i0iqiKRu3769UoIzJtakZx4gIe7Qr4SEuDjSMw+ENN/r7XvJ732vSGzh4GciCDaEXdAn4KnqFFVNVNXEJk2C3iFtjKmgFg1qkVtQcMi03IICWjSoFdJ8r7fvJb/3vSKxhYOfiSCdQ8c8bcH/xtA1xlSyRnVqMObqTtRMiKNujWrUTIhjzNWdaFSnRkjzvd6+l/ze94rEFg6ePobaHU7wU1XtGGTeZcC9wKU4F4knqGrX0spMTExUe9aQMd7JyMohPfMALRrUCvplU9p8r7fvJb/3vSKxlUZEFqtqYrB5nvUaEpG3gXOAxiKSDjwOJACo6mScQcovxRn7dD8w0KtYjDGha1SnRolfNKXN93r7XvJ734uTV5DH5+vfo+NRHWlUp0vYy/csEajq9aXMV+Aer7ZvjDHR7mD+Qd5c9iYj54xkXeY67j3jXp6/9PmwbyfqHkNtjDFVXXZeNlOXTGX03NFs2rOJ05uezocDPqRv+76ebM8SgTHGRIh9B/fx0uKXGDtvLFuztnJWi7N46fKX6NO2DyLBOlqGhyUCY4zx2Z6cPbyw8AXGLRjHjv07OK/Necy4agbntD7H0wRQyBKBMcb4ZOeBnYxfMJ4JCyewK3sXl7S9hMd6P0b3lt0rNQ5LBMYYU8m27dvGuPnjeGHRC2QdzOLKE68kqVcSpzc73Zd4LBEYY0wl2bxnM0/Pe5qXFr9Edl42AzoOIKlXEh2POuxWq0plicAYYzy2YdcGRs8ZzatLXyW/IJ+bO9/M0B5Dad+4vd+hAZYIjDHGM2sy1jByzkjeTHuTOIljYJeBDOkxhDYN2vgd2iEsERhjTJit2LaC4SnDeWfFO1SPr849Z9zDoO6DaHFkC79DC8oSgTHGhMmSX5cwPGU4H6z6gDrV6zDorEE8fNbDHF3naL9DK5ElAmOMqaAF6QtInp3MP9f8k3o16vG33n/j/m730+iIRn6HFhJLBMYYUw6qyrcbvyV5djJf/fwVjWo1Yvh5w7nnjHuoV7Oe3+GViSUCY4wpA1Xly3VfkpySzJxf5nBMnWN45qJnuOP0O6hdvbbf4ZWLJQJjPOLns+tN+Kkq//jpHyTPTmbRlkW0PLIlEy+ZyK2n3kqtBO9HKvOSJQJjPPDx0s0MmZVGQlwcuQUFjLm6E327BB2S20S4/IJ8Zq2axfCU4aT9lsZxDY7j5Ste5g+d/0D1+Op+hxcWlgiMCbOMrByGzEojO7eAbJyxZgfPSqNH28Z2ZhBF8gryePuHtxkxZwSrd6zmxMYn8kb/N7j+lOupFle1vjqr1t4YEwHSMw+QEBf3exIASIiLIz3zgCWCKHAw/yCvL32dUXNHsT5zPZ2O7sS717zLVSddRXxcvN/hecISgTFh1qJBLXILCg6ZlltQQIsG0d2OXNUdyD3A1O+dwWDS96RzRrMzePbiZ7n8hMuJkzi/w/OUJQJjwqxRnRqMuboTg4tcI7CzgciUdTCLl1Jf4un5T7M1ays9W/Vkat+pXHjchZUyFkAksERgjAf6dmlOj7aNrddQmIWzJ9bu7N1MXDiRZxc8S8aBDC447gJmXj2Ts1ufHaZoo4clAmM80qhODUsAYRSunlgZ+zMY/914Jnw3gd05u7n8hMtJ6pXEmS3O9CDq6GCJwBgT8cLRE2tr1lbGzR/HpEWT2Je7j6tPupqkXkmc2vRUL0OPCpYIjDERryI9sdL3pDN27limLJnCwfyDDOjgDAbT4agOXocdNSwRGGMiXnl6Yv2c+TOj5ozitaWvoSh/6PQHhvYcSrtG7bwON+pYIjDGRLyy9MT6ccePjJwzkrfS3iI+Lp4/n/ZnhvQYwrH1j/Uh8uhgicAYExVK64n1w28/MGLOCN5Z/g41q9Xk/m73M6j7IJrVbeZTxNHDEoExJmoE64m1eMtiklOS+Wj1R9SpXochPYbw0FkPcVTto3yKMvpYIjDGRKV5m+aRPDuZz9d+Tv2a9Xni7Ce4r9t9NKzV0O/Qoo4lAmNM1FBV/rvhvyTPTua/G/5L4yMaM/L8kdx9xt0cWeNIv8OLWpYIjDERT1X519p/kZySzLxN82hapynjLhrH7affHrWDwUQSSwTGmIhVoAV8vPpjklOSWfLrElrVa8WkSycx8NSB1KxW0+/wqgxPH6knIn1E5EcRWSsiQ4PMryci/xCRZSKyQkQGehmPMcZ/GVk5LNu0i4ysnGKXyS/IZ+bymXSe3Jmr3r2K3dm7mdp3KmvuW8NdZ9xlSSDMPDsjEJF44AXgQiAdWCQin6jqyoDF7gFWquoVItIE+FFEpqvqQa/iMsb4p7TnBeXm5zLjhxmMmDOCnzJ+4qTGJ/HWlW8xoOOAKjcYTCTxsma7AmtVdT2AiMwE+gGBiUCBuuI867UOsBPI8zAmY4xPSnpeUJ2aMG3pNEbNHcWGXRvockwX3v+/97nypCur/FgAkcDLRNAc2BTwOh3oVmSZicAnwBagLjBAVQuKLIOI3A7cDtCqVStPgjXGeCvY84Li4w4yZs5zTF/5PJv3bqZr8648f8nzXNbuspgZCyASeJkIgv0Xtcjri4GlwHnA8cC/RSRFVfccspLqFGAKQGJiYtEyjAkqnM+uNxUX+LygAvazt9rnpMuHrPxuF72P7c2r/V6NqcFgIomXiSAdaBnwugXOkX+ggcAoVVVgrYj8DJwILPQwLhMDwvXsehM+jerU4G99j+WBf4wiM+4j8mUvXZqczfjL/k7vY3v7HV5M8zIRLALaiUgbYDNwHXBDkWV+Ac4HUkTkaKA9sN7DmEwMCMez60147di/g+cWPMfzC59nT/weere8mKReSVzUrpffoRk8TASqmici9wJfAPHAq6q6QkTudOdPBp4CponIDzhNSUNUdYdXMZnYUJFn15vw2pq1lafnPc2LqS9yIPcA15x8DY/2epQux3TxOzQTwNP+WKr6GfBZkWmTA/7eAlzkZQwm9pTn2fUmvDbt3sSYuWN4ecnL5BbkcsMpNzCs5zBObnKy36GZIKxjrqlyyvLsehNe6zPXM2rOKKYtnYai3NL5Fob2HErbhm39Ds2UwBKBqZJKe3Z9VVfZPaZW71jNiJQRzPhhBtXiqnH76bczuMdgWtWz7t7RwBKBqbKCPbs+FlRmj6m039IYnjKc91a8R62EWjzQ7QEGdR9E07pNPdme8YYlAmOqkMrqMbVo8yKSU5L55MdPqFu9LsN6DuPBMx+kSe0mYduGqTyWCIypQrzuMTXnlzkkz07mi3Vf0KBmA54850nu63ofDWo1qHDZxj+WCIypQrzoMaWqfP3z1zw1+ym+3fgtTY5owqjzR3H3GXdTt0bdioZsIoAlAmOqkHD2mFJVPlvzGckpySxIX0Czus147uLnuO302zgi4QgPojd+sURgTBVT0R5TBVrAR6s/Inl2Mt9v/Z5j6x3Li5e9yMAuA6lRLfYuvscCSwTGVEHl6TGVV5DHuyveZXjKcFZuX0m7hu14rd9r3HjKjSTEJ3gUqYkElgiMiXG5+bm8lfYWI+aMYO3OtXRo0oHpV01nQIcBxMfF+x2eqQSWCIyJUdl52bz2/WuMnjuajbs3cuoxp/LBtR/Q78R+NhhMjLFEYEyM2Z+7nymLpzB23li27N3CmS3OZNJlk7ik7SU2FkCMskRgTIzYk7OHSYsmMW7+OLbv3845rc/hzSvf5NzW51oCiHGWCIyp4jIPZDLhuwmM/248mdmZ9Gnbh6ReSfRs1dPv0EyEsERgTBW1fd92nl3wLBMXTmTvwb30a9+PpF5JnNH8DL9DMxHGEoExVcyWvVt4et7TTE6dTHZeNtd2uJZHez1Kp6M7+R2aiVCWCIypIjbu2siYuWOY+v1U8gryuLHTjQzrOYwTG5/od2gmwlkiMBGtsp+rXxZexlaWstfuXMvIlJG8kfYGgvDHLn9kaM+hHNfgOF9ij1XRXKeWCEzEqszn6peVl7GFWvbK7SsZkTKCt5e/TfX46tyVeBePdH+ElvVa+hZ7rIr2OhVV9TuGMklMTNTU1FS/wzAey8jKocfor8nO/d+TNGsmxDF3yHm+H215GVsoZX//6/cMTxnOrFWzqJ1Qm7sS7+Iv3f/CMXWO8TX2WBUtdSoii1U1Mdg8OyMwEcnr5+pXhJexlVT2ml1OAvj0p085ssaRJPVK4sEzH6TxEY0jIvZYVRXq1BKBiUhePFc/XLyMLVjZuwuW8cB/xvDtL1/TsFZDnjr3Ke7tei/1a9YPS/mRUq/RqirUqT1QxESkwufq10yIo26NatRMiCv3c/WjKbbCsmskCNRYxraaQ9hUbQirM1Yw9sKxbHxwI4/1fqxcScDr2GNVVahTu0ZgIlok98TwIjZV5dOfPuWJb55iydZFNK3TnGE9h/Dn0/5MrYTwHWFGcr1Gq0ivU7tGYKJWeZ6rX1nCGVuBFjBr5SyGpwxn2W/LaF2/NS9d/hK3dL7Fk8FgIrleo1U016klAmN8lFeQx8zlMxmRMoJVO1bRvlF7Xu//Otd3vL7EwWAi/ejTRBdLBMb44GD+Qd5c9iYj54xkXeY6Oh7VkZlXz+Sak68pdTCYaO+zbiKPJQJjKlF2XjZTl0xl9NzRbNqzidObns5HAz7iivZXhDQYTEZWDkNmpZGdW/B7d8XBs9Lo0baxnRmYcrNEYEwl2HdwHy8tfomx88ayNWsr3Vt256XLX6JP2z5lGgugKvRZN5HHEoExHtqdvZsXFr3AuPnjyDiQwXltzmPGVTM4p/U55RoMpir0WTeRx9P7CESkj4j8KCJrRWRoMcucIyJLRWSFiHzrZTzGVJadB3by+H8fp/X41iR9nUS3Ft2Ye+tcvvrDV5zbpvwjglWFPusm8nh2RiAi8cALwIVAOrBIRD5R1ZUBy9QHJgF9VPUXETnKq3iMqQzb9m3jmXnPMCl1ElkHs7jyxCtJ6pXE6c1OD9s2+nZpTo+2ja3XkAmbkBKBiNQCWqnqj2UouyuwVlXXu2XMBPoBKwOWuQH4QFV/AVDVbWUo35iIsXnPZsbOG8uUxVPIzstmQMcBJPVKouNRHT3ZXjT3WTeRp9REICJXAE8D1YE2ItIF+Luq9i1l1ebApoDX6UC3IsucACSIyDdAXWC8qr4RJIbbgdsBWrVqVVrIxlSaDbs2MGrOKF5b+hr5Bfnc1OkmhvUcRvvG7f0OzZiQhXJG8ATO0f03AKq6VERah7BesEbQos+zqAacDpwP1ALmi8gCVf3pkJVUpwBTwHnERAjbNqZUFbkp66eMnxg5ZyRvLnuT+Lh4BnYZyJAeQ2jToI1H0RrjnVASQZ6q7i7Hxa10IHCEjBbAliDL7FDVfcA+EZkNdAZ+whgPlfemrOXbljMiZQTvrHiH6vHVubfrvQzqPogWR7aohKiN8UYoiWC5iNwAxItIO+B+YF4I6y0C2olIG2AzcB3ONYFAHwMTRaQaTtNTN+DZUIM3pjxCvSkr8Ixhw57lDE8ZzoerP6R2Qm0GnTWIh896mKPrHO3XbhgTNqEkgvuAJCAHmAF8ATxV2kqqmici97rLxwOvquoKEbnTnT9ZVVeJyL+ANKAAeEVVl5dvV4wJTSg3ZRWeMeTGreY33mZf3CLq1ajHX3v/lQe6PUCjIxr5Fb4xYRdKIrhMVZNwkgEAIvJ/wHulraiqnwGfFZk2ucjrscDYkKI1JgxKuylrx95s7vvgLbbLDLLj0ojTI2mcfwsLbxtDm0bWw9lUPaHcUDYsxGnGRIXibspqWLs6/1r7Ly586xw2xQ/lYNwv1M+9lebZUzlGrmfP/up+h26MJ4o9IxCRS4BLgeYiMiFg1pFAnteBGeOlwJuymtWvwbzNX9L1lWRSt6TSvG4Ljsq/ixoHLyAOp6nIHuNgqrKSzgi2AKlANrA44OcT4GLvQzPGW/WPqMbq3V9w/lvd6P9Of3Ye2MnLV7zM+gfW8fJVSRyRUMse42BiQrFnBKq6DFgmIjNUNbcSYzJVSCQOoJKbn8vby99mRMoIfsz4kRMbn8ibV77JdR2vo1qc85GwxziYWBLKxeLWIjISOBmoWThRVY/zLCpTJUTaACo5eTm8vux1Rs0Zxc+7fqbT0Z1495p3ueqkq4IOBmOPcTCxIpRE8BrwOE7//nOBgQS/a9iY30XSACoHcg/wypJXGDNvDOl70jmj2RmM7zOey0+4vNxPATWmKgklEdRS1a9ERFR1I/CEiKTgJAdjgoqEAVSyDmYxOXUyT897mt/2/UbPVj2Z2ncqFx53oSUAYwKEkgiyRSQOWOPeILYZsM7UpkR+DqCyK3sXExdO5NkFz7LzwE4uPO5CHuv9GL2P7e35to2JRqEkggeBI3AeLfEUcB7wBw9jMlVAYV/9wUWuEXh5NrBj/w7GLxjPhIUT2JOzh8tPuJykXkmc2eJMz7ZpTFVQaiJQ1UXun1nAQPe5QAOA77wMzES/yup5szVrK8/Me4YXU19kf+5+rj75ah7t+SinNj3Vk+0ZU9WUdEPZkcA9OOMKfAL82309CFgGTK+MAE1087Lnzabdmxg7bywvL3mZg/kHub7j9Tza61FObnKyJ9szpqoq6YzgTSATmA/8GXgE5wmh/VV1qfehhZfX/dkjsb98OJS2XxXd7/Ksvz5zPaPmjGLa0mmoKgM63MgT5z5G24Zty7x9v1TV94uJTiUlguNU9RQAEXkF2IEzXOXeSoksjLzuzx5p/eXDpbT9quh+l3X91TtWM3LOSKanTSdOqlE77yKO4lpSlzZh5fG1aNuwQrtbaarq+8VEr5IeMfH73cSqmg/8HI1JILA/+96cPLJzCxg8K42MrJyoKN8vpe1XRfe7LOun/ZbGde9fx8kvnMx7K97jttPuodXBV6iXcxc5OY2iqs6r6vvFRLeSEkFnEdnj/uwFOhX+LSJ7KivAiirszx6osD97NJTvl9L2q6L7Hcr6qVtS6T+zP50nd+azNZ8xtOdQNj64kTs7P0mtuCbl3rafqur7xUS3kp41dPg991HI6/7sfvaX91Jp+1XR/S5p/bm/zCU5JZl/rf0XDWo24PGzH+f+bvfTsJbT9hOnOVFb51X1/WKiWyjjEUS14p49H64LdF6X75fS9qui+110/RoJwk2993LNrD70fK0ni7csZtT5o9jw4AaeOOeJ35NAOLbtp2iO3VRdoqp+x1AmiYmJmpqaWub1rNdQ+Xjda2jH3mxm/vAJbyx/lkW/LqBpnaYM7jGY2067jdrVa1cotkgWzbGb6CQii1U1Mei8WEkEJrIUaAEfr/6Y5JRklvy6hFb1WjG0x1AGnjqQmtVqll6AMaZMSkoEoTxiwpiwyS/I572V7zE8ZTjLty2nbcO2TO07lZs73UxCfILf4RkTk0pNBCJyFTAa50Fz4v6oqh7pcWymCsnNz2X6D9MZOWckP2X8xMlNTmb6VdO5tsO1vw8GY4zxRyifwDHAFaq6yutgTNWTk5fDtKXTGDV3FBt2beDUY05l1rWz6H9if+KkyvdVMCYqhJIIfrMkYMpqf+5+ZzCYuWPYvHcz3Zp3Y+IlE7m03aU2FoAxESaURJAqIu8AHwG/3/6oqh94FZSJXntz9vJi6os8M/8Ztu3bxtnHns20/tM4v835lgCMiVChJIIjgf3ARQHTFLBEYH63K3sXE76bwHMLniMzO5OLj7+YpF5J9Dq2l9+hGWNKEcp4BAMrIxATnXbs38Gz859l4qKJ7MnZQ9/2fUnqlUTX5l39Ds0YE6KSxiMYrKpjROR5nDOAQ6jq/Z5GZiLar3t/5Zn5zmAwB3IPcM3J15DUK4nOx3T2OzRjTBmVdEZQeIHY7t4yv/tl9y+MmTuGV5a8Ql5BHjeccgPDeg7jpCYn+R2aMaacSkoEx4vIGcB0Vc2rrIBMZFq3cx2j5ozi9WWvA3BL51sY2nMoxzc83ufIjDEVVVIiaAGMB04UkTRgHjAXmK+qOysjOOO/VdtXMXLOSGb8MINqcdW44/Q7eKTHI7Sq18rv0IwxYVLSY6gHAYhIdSAR6A7cCrwsIrtU1QaGrcKWbV3G8JThvL/yfWol1OLBMx/kL2f9haZ1m/odmjEmzELpPloLpwtpPfdnC/BDKIWLSB+cs4p44BVVHVXMcmcAC4ABqvp+KGUbbyzcvJDhKcP55MdPqFu9LsN6DuOhsx6i8RGN/Q7NGOORknoNTQE6AHuB73CahsapamYoBYtIPPACcCGQDiwSkU9UdWWQ5UYDX5RrD0xYzPllDk/Nfoov131Jw1oN+fs5f+fervfSoFYDv0MzxnispDOCVkANYA2wGefLfFcZyu4KrFXV9QAiMhPoB6wsstx9wCzgjDKUbcJAVfnq569Inp3Mtxu/5ajaRzH6gtHclXgXdWvU9Ts8Y0wlKekaQR9xngnQAef6wF+AjiKyE+eC8eOllN0c2BTwOh3oFriAiDQHrgTOo4REICK3A7cDtGplFykrSlX5bM1nPDX7Kb7b/B3N6jbjuYuf47bTb+OIhCP8Ds8YU8lKvEagzqg1y0VkF7Db/bkc52i/tEQQ7MEyRW9Mew4Yoqr5JT2HRlWnAFPAGZimlO2aYhRoAR+u+pDklGSWbl1K6/qtmXzZZP7Y5Y/UqGajZBkTq0q6RnA/zplADyAXt+so8CqhXSxOB1oGvG6Bc6E5UCIw000CjYFLRSRPVT8KMX4TgryCPN5d8S7DU4azcvtKTmh0AtP6TeOGU26wwWCMMSWeEbQG3gceUtVfy1H2IqCdiLTBucZwHXBD4AKq2qbwbxGZBnxqSSB8cvNzeTPtTUbOGcnanWvp0KQDM66awbUdriU+Lt7v8IwxEaKkawQPV6RgVc0TkXtxegPFA6+q6goRudOdP7ki5ZviZedl89r3rzF67mg27t7IaU1P44NrP6Dfif1sMBhjzGE8HSNQVT8DPisyLWgCUNU/ehlLLNh3cB9TFk9h7Lyx/Jr1K2e1OIsXL3uRPm372FgAxphi2WCxVcCenD1MWjSJcfPHsX3/ds5tfS5vXfUW57Y+1xKAMaZUlgiiWOaBTCZ8N4Hx340nMzuTPm378Fivx+jRqkeZysnIyiE98wAtGtSiUR3rPWRMrLFEEIW279vOuPnjeGHRC+w9uJf+J/YnqVcSic0Sy1zWx0s3M2RWGglxceQWFDDm6k707dLcg6iNMZHKEkEU2bJ3C0/Pe5rJqZPJzsvm2g7XktQriVOOPqVc5WVk5TBkVhrZuQVkUwDA4Flp9Gjb2M4MjIkhlghC5GfzycZdGxk9dzRTv59KfkE+N3W6iWE9h9G+cfsKlZueeYCEuLjfkwBAQlwc6ZkHLBEYE0MsEYTAr+aTNRlrGDVnFG+kvYEgDOwykCE9h3Bcg+PCUn6LBrXILSg4ZFpuQQEtGtQKS/nGmOhgiaAUfjSfrNi2ghFzRjBz+Uyqx1fn7sS7GdR9EC3rtSx95TJoVKcGY67uxOAiSc7OBoyJLZYISlGZzSff//o9w1OGM2vVLGon1OYvZ/2Fh896mGPqHBPW7QTq26U5Pdo2tl5DxsQwSwSlqIzmkwXpC0iencw/1/yTejXq8dfef+WBbg/Q6IhGYdtGSRrVqWEJwJgYZomgFF41n6gqszfOJjklmf+s/w8NazUk+dxk7ul6D/Vr1g9P8MYYEwJLBCEIZ/OJqvLlui9JTklmzi9zOLr20Yy9cCx3Jt5Jnep1whi1McaExhJBiCrafKKq/OOnf5A8O5lFWxbR4sgWPH/J8/zp1D9RK8F66Rhj/GOJwGP5Bfl8sOoDhqcMZ9lvy2hTvw1TLp/CLV1uoXp8db/DM8YYSwReySvI4+0f3mbEnBGs3rGa9o3a83r/17nhlBuoFmfVboyJHPaNFGYH8w/yxrI3GDlnJOsz13PKUafwzjXvcPVJV9tgMMaYiGSJIEwO5B5g6vdTGTN3DJv2bCKxWSLjLhrHFe2vsMFgjDERzRJBBWUdzOKl1Jd4ev7TbM3aSveW3ZlyxRQuPv5iGwvAGBMVLBGU0+7s3UxcOJFnFzxLxoEMzmtzHjOumsE5rc+xBGCMiSqWCMooY38G478bz4TvJrA7ZzeXtruUpF5JdG/Z3e/QjDGmXCwRhOi3rN8YN38ck1InkXUwiytPvJLHej/GaU1P8zs0Y4ypEEsEpUjfk87YuWOZsmQKB/MPMqDDAB7t9Sgdj+rod2ghs6EojTElsURQjJ8zf2b03NG8tvQ18gvyubnzzQzrOYwTGp3gd2hlYkNRGmNKY4mgiJ8yfmJEygjeSnuL+Lh4bu1yK0N6DqF1/dZ+h1ZmNhSlMSYUlghcy7ctZ3jKcN5d8S414mtwX9f7GNR9EM2PjN6jZxuK0hgTiphPBIu3LGZ4ynA+XP0hdarX4ZHuj/DQmQ9xdJ2j/Q6twmwoSmNMKGI2EczbNI/k2cl8vvZz6tesz+NnP8793e6nYa2GfocWNjYUpTEmFDGVCFSVbzZ8Q3JKMl///DWNj2jMiPNGcPcZd1OvZj2/w/OEDUVpjClNzCSChZsX8tAXDzFv0zyOqXMMz1z0DHecfge1q9f2OzTP2VCUxpiSxEwiyM3PZdPuTUy8ZCJ/Ou1P1KxW0++QjDEmIsRMIujRqgfr7l9HQnyC36EYY0xE8fT5yCLSR0R+FJG1IjI0yPwbRSTN/ZknIp29jCdSk0BGVg7LNu0iIyvH71CMMTHIszMCEYkHXgAuBNKBRSLyiaquDFjsZ+BsVc0UkUuAKUA3r2KKRHbnrzHGb16eEXQF1qrqelU9CMwE+gUuoKrzVDXTfbkAaOFhPBEn8M7fvTl5ZOcWMHhWmp0ZGGMqlZeJoDmwKeB1ujutOH8CPg82Q0RuF5FUEUndvn17GEP0V+Gdv4EK7/w1xpjK4mUiCDY6iwZdUORcnEQwJNh8VZ2iqomqmtikSZMwhugvu/PXGBMJvEwE6UDLgNctgC1FFxKRTsArQD9VzfAwnohTeOdvzYQ46taoRs2EOLvz1xhT6bzsProIaCcibYDNwHXADYELiEgr4APgZlX9ycNYIpbd+WuM8ZtniUBV80TkXuALIB54VVVXiMid7vzJwN+ARsAkd5zfPFVN9ComP5U0OIzd+WuM8ZOoBm22j1iJiYmamprqdxhlYl1EjTF+E5HFxR1oe3pDmbEuosaYyGeJwGPWRdQYE+ksEXjMuogaYyKdJQKPWRdRY0yki5mnj/rJuogaYyKZJYJKYl1EjTGRypqGjDEmxlkiMMaYGGeJwBhjYpwlAmOMiXGWCIwxJsZZIjDGmBhnicAYY2KcJQJjjIlxlgiMMSbGWSIwxpgYZ4nAGGNinCUCY4yJcZYIjDEmxlkiMMaYGGeJwBhjYpwlAmOMiXGWCIwxJsZZIjDGmBhnicAYY2KcJQJjjIlxlgiMMSbGWSIwxpgYZ4nAGGNinCUCY4yJcZYIjDEmxnmaCESkj4j8KCJrRWRokPkiIhPc+WkicpqX8ZQkIyuHZZt2kZGV41cIxSottkiO3ZhIYp+V4Kp5VbCIxAMvABcC6cAiEflEVVcGLHYJ0M796Qa86P6uVB8v3cyQWWkkxMWRW1DAmKs70bdL88oOI6jSYovk2I2JJPZZKZ6XZwRdgbWqul5VDwIzgX5FlukHvKGOBUB9EWnqYUyHycjKYcisNLJzC9ibk0d2bgGDZ6VFxBFDabFFcuzGRBL7rJTMy0TQHNgU8DrdnVbWZRCR20UkVURSt2/fHtYg0zMPkBB3aDUkxMWRnnkgrNspj9Jii+TYjYkk9lkpmZeJQIJM03Isg6pOUdVEVU1s0qRJWIIr1KJBLXILCg6ZlltQQIsGtcK6nfIoLbZIjt2YSGKflZJ5mQjSgZYBr1sAW8qxjKca1anBmKs7UTMhjro1qlEzIY4xV3eiUZ0alRlGuWKL5NiNiST2WSmZqB52AB6egkWqAT8B5wObgUXADaq6ImCZy4B7gUtxLhJPUNWuJZWbmJioqampYY83IyuH9MwDtGhQK+LeHKXFFsmxGxNJYvmzIiKLVTUx2DzPeg2pap6I3At8AcQDr6rqChG5050/GfgMJwmsBfYDA72KpzSN6tSI2DdGabFFcuzGRBL7rATnWSIAUNXPcL7sA6dNDvhbgXu8jMEYY0zJ7M5iY4yJcZYIjDEmxlkiMMaYGGeJwBhjYpxn3Ue9IiLbgY3lXL0xsCOM4YSTxVY+kRwbRHZ8Flv5RGtsx6pq0Dtyoy4RVISIpBbXj9ZvFlv5RHJsENnxWWzlUxVjs6YhY4yJcZYIjDEmxsVaIpjidwAlsNjKJ5Jjg8iOz2IrnyoXW0xdIzDGGHO4WDsjMMYYU4QlAmOMiXExkwhEpI+I/Cgia0VkqN/xBBKRDSLyg4gsFZHwP2O7bLG8KiLbRGR5wLSGIvJvEVnj/m4QQbE9ISKb3bpbKiKX+hRbSxH5r4isEpEVIvKAO933uishNt/rTkRqishCEVnmxvakOz0S6q242Hyvt4AY40XkexH51H1drnqLiWsEIhKPMzbChTiD4SwCrlfVlb4G5hKRDUCiqvp+k4qI9AaycMaS7uhOGwPsVNVRbhJtoKpDIiS2J4AsVX26suMpEltToKmqLhGRusBioD/wR3yuuxJiuxaf605EBKitqlkikgDMAR4ArsL/eisutj5EwHsOQEQeBhKBI1X18vJ+VmPljKArsFZV16vqQWAm0M/nmCKSqs4GdhaZ3A943f37dZwvkUpXTGwRQVV/VdUl7t97gVU442/7XnclxOY7dWS5LxPcHyUy6q242CKCiLQALgNeCZhcrnqLlUTQHNgU8DqdCPkguBT4UkQWi8jtfgcTxNGq+is4XyrAUT7HU9S9IpLmNh350mwVSERaA6cC3xFhdVckNoiAunObN5YC24B/q2rE1FsxsUEE1BvwHDAYCByMuVz1FiuJQIJMi5jMDvRQ1dOAS4B73CYQE5oXgeOBLsCvwDN+BiMidYBZwIOqusfPWIoKEltE1J2q5qtqF5wxy7uKSEc/4gimmNh8rzcRuRzYpqqLw1FerCSCdKBlwOsWwBafYjmMqm5xf28DPsRpyookv7ntzIXtzdt8jud3qvqb+2EtAF7Gx7pz25FnAdNV9QN3ckTUXbDYIqnu3Hh2Ad/gtMFHRL0VCowtQuqtB9DXvb44EzhPRN6inPUWK4lgEdBORNqISHXgOuATn2MCQERquxfwEJHawEXA8pLXqnSfALe4f98CfOxjLIcofNO7rsSnunMvLE4FVqnquIBZvtddcbFFQt2JSBMRqe/+XQu4AFhNZNRb0Ngiod5UdZiqtlDV1jjfZ1+r6k2Ut95UNSZ+gEtxeg6tA5L8jicgruOAZe7PCr9jA97GOd3NxTmT+hPQCPgKWOP+bhhBsb0J/ACkuR+Cpj7F1hOnuTENWOr+XBoJdVdCbL7XHdAJ+N6NYTnwN3d6JNRbcbH5Xm9F4jwH+LQi9RYT3UeNMcYUL1aahowxxhTDEoExxsQ4SwTGGBPjLBEYY0yMs0RgjDExzhKBiSoikhXw96XuUxZbicidIvIHd/o0EbnG/fsbETlsMG93+o/ukyXnikj7MsRQX0TuDnjdTETeL2WdV0Tk5FC3UWTd/oHrisjfReSC8pRlTDCWCExUEpHzgedx7vT8RVUnq+obZSzmRlXtjPNwrrEhbjceqA/8nghUdYuqXlPSeqr6Zy3/0277A78nAlX9m6r+p5xlGXMYSwQm6ohIL5xb+y9T1XXutCdEZFA5i5wNtBWR1iKSIiJL3J/ubtnniPM8/xk4NxKNAo53n0U/1l1vubtsvIg8Lc74Emkicp87/fczExHJEpFn3G18JSJN3Om3icgi9yxllogc4cbQFxjrbu/4Imc854vzPPof3Aeg1XCnbxCRJ91t/CAiJ5azbkwMsERgok0NnNvm+6vq6jCVeQXOF/w24EJ1HgA4AJgQsExXnLu+TwaGAutUtYuqPlKkrNuBNsCpqtoJmB5ke7WBJe52vgUed6d/oKpnuGcpq4A/qeo8nLtXH3G3t66wEBGpCUwDBqjqKUA14K6A7exwt/EiUN4kaWKAJQITbXKBeTiPl6io6e4jhnvgfFEmAC+LyA/AewQ0xwALVfXnEMq8AJisqnkAqhps/IQC4B3377dwHgEB0NE9I/kBuBHoUMq22gM/q+pP7uvXgcAn1xY++G4x0DqE2E2MskRgok0BzshaZ4jIoxUs60b3KLu/qm4CHgJ+AzrjjPpUPWDZfSGWKZT9EeeFy08D7nWP7p8EaoawrZLkuL/zcc4WjAnKEoGJOqq6H7gcuFFEwnFmUKge8Ks6jxe+GYgvZrm9QN1i5n0J3Cki1cAZQzbIMnFA4cXlG3CGQMQt81f3kdE3hrC91UBrEWnrvr4Zp6nJmDKxRGCiktvk0gd4TETCNezoJOAWEVkAnEAxZwGqmgHMFZHlIlK0t9ErwC9Amogsw/miL2of0EFEFgPnAX93p/8VZ+Swf+N8yReaCTziXhQ+PiCObGAg8J7bnFQATC7LDhsDMTJ4vTGRRESyVLWO33EYU8jOCIwxJsbZGYExxsQ4OyMwxpgYZ4nAGGNinCUCY4yJcZYIjDEmxlkiMMaYGPf/fKGCXgl4K0UAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>This fit isn't too great. Let's take a look at the residuals though.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[35]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">resid_calc</span><span class="p">(</span><span class="n">kp</span><span class="p">,</span> <span class="n">winrate</span><span class="p">):</span>
    <span class="n">ax</span> <span class="o">=</span> <span class="mf">0.01916738</span><span class="o">*</span><span class="n">kp</span>
    <span class="n">y</span> <span class="o">=</span> <span class="p">(</span><span class="n">ax</span><span class="p">)</span> <span class="o">+</span> <span class="mf">0.22667317</span>
    <span class="k">return</span> <span class="n">winrate</span> <span class="o">-</span> <span class="n">y</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[36]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">resids_list</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">index</span><span class="p">,</span> <span class="n">row</span> <span class="ow">in</span> <span class="n">kp_df2</span><span class="o">.</span><span class="n">iterrows</span><span class="p">():</span>
    <span class="n">resids_list</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">resid_calc</span><span class="p">(</span><span class="n">kp_df2</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;kill_participation&#39;</span><span class="p">],</span> <span class="n">kp_df2</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="n">index</span><span class="p">,</span> <span class="s1">&#39;win_rate&#39;</span><span class="p">]))</span>
    
<span class="n">mpl</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">kp_df2</span><span class="p">[</span><span class="s1">&#39;kill_participation&#39;</span><span class="p">],</span><span class="n">resids_list</span><span class="p">)</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">axhline</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;r&#39;</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[36]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;matplotlib.lines.Line2D at 0x7f555ea21760&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We can see that there is a sort of pattern to the residuals. There are very few values under the residual line after around 15 KP. This might suggest that there might be a better model to fit this data. However, for our purposes it does not matter that much, since we can generally see that higher win rate correlates with more kill participation. But why is that? There are a few possible explanations.</p>
<h3 id="How-does-one-even-get-KP-that-high?">How does one even get KP that high?<a class="anchor-link" href="#How-does-one-even-get-KP-that-high?">&#182;</a></h3><p>In order for a player to hit numbers like 40 KP, the game typically has to last a long amount of time. My longest match ever was around 55 minutes long, for instance. According to LeagueofGraphs, <a href="https://www.leagueofgraphs.com/rankings/game-durations">games in my rank last about 30 minutes</a>. Games that run over that benchmark tend to be very even, as both teams have specific win conditions, and neither team is so far ahead as to end the game quickly. As a result, the games can be bloodbaths, with a huge number of kills on each side. These games can really go either way, and with a low sample size of these games from my own data set, it can be hard to get a good idea of what's going on. Anyways, let's go back to the linear regression, and discuss what the numbers actually mean.</p>
<h3 id="Understanding-the-Model">Understanding the Model<a class="anchor-link" href="#Understanding-the-Model">&#182;</a></h3><p>As written in the comment in the function above, the linear function given by the regression is roughly y = 0.226 + 0.019x. This means that for an increase of 1 KP, my win rate will rise by roughly 2 percent. It starts at 22.6 percent, because of the two remakes in the data. We can't apply this model to anything outside the dataset because it would yield us values above 1.0, which is simply impossible. You cannot win more games than the amount of games you play.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="Data-Anaylsis-4:-Eyes-Everywhere">Data Anaylsis 4: Eyes Everywhere<a class="anchor-link" href="#Data-Anaylsis-4:-Eyes-Everywhere">&#182;</a></h2><p>Another extremely important aspect of Support I want to touch on is Vision Score (also referred to simply as Vision). Vision is an extremely underrated part of the game in lower ranks (such my rank, Silver), as it allows you to know where the enemy is if they are not in lane (if an enemy is in lane, you don't need to worry about buying or using vision wards on them). There are several types of vision wards that can help you locate missing enemies, as well as secure vision on objectives like the Baron or the dragons, or even to allow a teammate using the Teleport spell to assist you. Thankfully, Riot uses a metric called Vision Score to display how well a player gave more vision to their team. The calculation for Vision Score is a bit messy (as seen <a href="https://leagueoflegends.fandom.com/wiki/Vision_score">here</a>), so it's nice to have a neat little metric to use in our analysis. Before we get into said analysis though, I'll explain a little bit more about Vision Score to give you a better idea of what it means.</p>
<h3 id="Vision-Score-in-a-nutshell">Vision Score in a nutshell<a class="anchor-link" href="#Vision-Score-in-a-nutshell">&#182;</a></h3><p>Every player has access to Trinkets of various types, but mostly people just use the standard Vision Ward (supports use Oracle Lens typically, since they get an item that provides extra Vision Wards). You place wards down around the map to reveal areas that would otherwise be obscured by the Fog of War. Your score goes up in varying degrees based on ward redundancy, placement, uselessness, and more based on how well it does its job. There are also optional "Pink" wards that cost 75 gold and have an indefinite lifespan, provided that an enemy doesn't destroy it. Essentially, players with a higher vision score tend to reveal more of the map for their teammates and deny the enemy from getting Vision of their own. With that out of the way, let's see if there is a relationship between an increase in Vision Score and an increase in win rate.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Since Vision Score varies widely, let's compare my Vision Score with the enemy Support across all games.</p>

</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[88]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">VS_list</span> <span class="o">=</span> <span class="p">[]</span> <span class="c1"># List of tuples, containing Vision Score and a boolean denoting a win (true) or loss (false)</span>
<span class="c1"># First let&#39;s loop through the matches and record my Vision Score. We&#39;re reusing code above but repurposing it.</span>
<span class="n">i</span> <span class="o">=</span> <span class="mi">0</span>
<span class="k">while</span> <span class="n">i</span> <span class="o">&lt;</span> <span class="mi">267</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">i</span> <span class="o">==</span> <span class="mi">92</span><span class="p">:</span> <span class="c1"># Special case: Jhin and Swain swapped.</span>
        <span class="nb">id</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">][</span><span class="s1">&#39;summonerName&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;OG Zoidberg&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span><span class="o">+</span><span class="mi">4</span>
        <span class="n">supp_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="p">]]</span>
        <span class="n">supp_VS</span> <span class="o">=</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="p">,</span><span class="s1">&#39;visionScore&#39;</span><span class="p">]</span>
        <span class="n">my_VS</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="o">-</span><span class="mi">4</span><span class="p">]]</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="o">-</span><span class="mi">4</span><span class="p">,</span> <span class="s1">&#39;visionScore&#39;</span><span class="p">]</span>
        
        <span class="n">VS_list</span><span class="o">.</span><span class="n">append</span><span class="p">(((</span><span class="n">my_VS</span><span class="o">-</span><span class="n">supp_VS</span><span class="p">),</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="o">-</span><span class="mi">4</span><span class="p">,</span> <span class="s1">&#39;win&#39;</span><span class="p">]))</span>
        
    <span class="k">else</span><span class="p">:</span>
        
        <span class="nb">id</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">loc</span><span class="p">[</span><span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">][</span><span class="s1">&#39;summonerName&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;OG Zoidberg&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">index</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
        <span class="n">supp_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="p">]]</span>
        <span class="n">supp_VS</span> <span class="o">=</span> <span class="s2">&quot;&quot;</span>
        <span class="k">if</span> <span class="nb">id</span> <span class="o">==</span> <span class="mi">4</span><span class="p">:</span>
            <span class="n">supp_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="o">+</span><span class="mi">5</span><span class="p">]]</span>
            <span class="n">supp_VS</span> <span class="o">=</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="o">+</span><span class="mi">5</span><span class="p">,</span><span class="s1">&#39;visionScore&#39;</span><span class="p">]</span>
            <span class="n">my_VS</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="p">,</span> <span class="s1">&#39;visionScore&#39;</span><span class="p">]</span>
            <span class="n">VS_list</span><span class="o">.</span><span class="n">append</span><span class="p">(((</span><span class="n">my_VS</span><span class="o">-</span><span class="n">supp_VS</span><span class="p">),</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="p">,</span> <span class="s1">&#39;win&#39;</span><span class="p">]))</span>
        
        <span class="k">else</span><span class="p">:</span>
            <span class="n">supp_row</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">iloc</span><span class="p">[[</span><span class="nb">id</span><span class="o">-</span><span class="mi">5</span><span class="p">]]</span>
            <span class="n">supp_VS</span> <span class="o">=</span> <span class="n">supp_row</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="o">-</span><span class="mi">5</span><span class="p">,</span> <span class="s1">&#39;visionScore&#39;</span><span class="p">]</span>
            <span class="n">my_VS</span> <span class="o">=</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="p">,</span> <span class="s1">&#39;visionScore&#39;</span><span class="p">]</span>
            <span class="n">VS_list</span><span class="o">.</span><span class="n">append</span><span class="p">(((</span><span class="n">my_VS</span><span class="o">-</span><span class="n">supp_VS</span><span class="p">),</span> <span class="n">df_list2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">at</span><span class="p">[</span><span class="nb">id</span><span class="p">,</span> <span class="s1">&#39;win&#39;</span><span class="p">]))</span>
        
    <span class="n">i</span><span class="o">+=</span><span class="mi">1</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[111]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">win_list</span> <span class="o">=</span> <span class="p">[]</span>
<span class="n">loss_list</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">point</span> <span class="ow">in</span> <span class="n">VS_list</span><span class="p">:</span>
    <span class="k">if</span> <span class="n">point</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span> <span class="o">==</span> <span class="kc">True</span><span class="p">:</span>
        <span class="n">win_list</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">point</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="n">loss_list</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">point</span><span class="p">[</span><span class="mi">0</span><span class="p">])</span>
        
<span class="n">total_list</span> <span class="o">=</span> <span class="p">[</span><span class="n">win_list</span><span class="p">,</span> <span class="n">loss_list</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[112]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ids</span> <span class="o">=</span> <span class="p">[</span><span class="mi">0</span><span class="p">,</span> <span class="mi">5</span><span class="p">]</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">violinplot</span><span class="p">(</span><span class="n">total_list</span><span class="p">,</span><span class="n">ids</span><span class="p">,</span><span class="n">widths</span><span class="o">=</span><span class="mi">4</span><span class="p">,</span><span class="n">showmeans</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">axhline</span><span class="p">(</span><span class="n">y</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s1">&#39;g&#39;</span><span class="p">)</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">&quot;Arbitrary&quot;</span><span class="p">)</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">&quot;Vision Score Difference&quot;</span><span class="p">)</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;Violin Plot Displaying Difference in Vision Score&quot;</span><span class="p">)</span>
<span class="n">mpl</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">

    
    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Understanding-the-Model">Understanding the Model<a class="anchor-link" href="#Understanding-the-Model">&#182;</a></h3><p>The left Violin represents the games in which I won, and the right those I lost. You can see here that my average Vision Score was above zero (which is to say, I had more impact on the game's vision overall), and in games I lost, my Vision Score is below zero. They are both quite close to zero, but the winning plot on the left shows that the difference when I win is higher than when I lose, possibly suggesting I win more games if I have a bigger impact on my team's vision. In addition, the spread of the losses is much wider than the wins, meaning that more of my wins are close to or above 0, whereas in the losses they are spread out much more normally.</p>

</div>
</div>
<div class="jp-Cell-inputWrapper"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="Conclusion:-The-More-You-Know">Conclusion: The More You Know<a class="anchor-link" href="#Conclusion:-The-More-You-Know">&#182;</a></h1><p>Thank you for reading this tutorial, and I hope you understand more about not only League of Legends, but the Data Science process as well. Thankfully, due to the wealth of statistics at my disposal, I was able to show a variety of different areas to focus on. In working on this project I learned a lot about how I play the game, my strong suits, and more! Hopefully I can take some of this information to mind going forward, and bump those win numbers up. Based purely on my win rate with Tahm Kench, I am overperforming compared to other players in the same rank.</p>
<p>This analysis could include more such as statistics across every game (non-ranked included) or every champion, but I believe my support statistics gave a good enough idea about the Data Science Pipeline. I would like to thank <a href="https://www.riotgames.com/en">Riot Games</a> for allowing humble users such as myself to access their data, as well as the staff of CMSC320 for adequately preparing me to undertake such a project. I hope you learned a bunch, and take care!</p>

</div>
</div>
</body>







</html>
