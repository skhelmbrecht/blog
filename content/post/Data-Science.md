---
title: "Data Science Final"
date: 2023-12-20T02:35:32-05:00
draft: false
---

<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>MusicAnalysis</title><script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>




<style type="text/css">
    pre { line-height: 125%; }
td.linenos .normal { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
span.linenos { color: inherit; background-color: transparent; padding-left: 5px; padding-right: 5px; }
td.linenos .special { color: #000000; background-color: #ffffc0; padding-left: 5px; padding-right: 5px; }
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
.highlight .pm { color: var(--jp-mirror-editor-punctuation-color) } /* Punctuation.Marker */
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

/* tiny scrollbar */

.jp-scrollbar-tiny {
  scrollbar-color: rgba(var(--jp-scrollbar-thumb-color), 0.5) transparent;
  scrollbar-width: thin;
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

/* tiny scrollbar */

.jp-scrollbar-tiny::-webkit-scrollbar,
.jp-scrollbar-tiny::-webkit-scrollbar-corner {
  background-color: transparent;
  height: 4px;
  width: 4px;
}

.jp-scrollbar-tiny::-webkit-scrollbar-thumb {
  background: rgba(var(--jp-scrollbar-thumb-color), 0.5);
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:horizontal {
  border-left: 0px solid transparent;
  border-right: 0px solid transparent;
}

.jp-scrollbar-tiny::-webkit-scrollbar-track:vertical {
  border-top: 0px solid transparent;
  border-bottom: 0px solid transparent;
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

.lm-close-icon {
	border:1px solid transparent;
  background-color: transparent;
  position: absolute;
	z-index:1;
	right:3%;
	top: 0;
	bottom: 0;
	margin: auto;
	padding: 7px 0;
	display: none;
	vertical-align: middle;
  outline: 0;
  cursor: pointer;
}
.lm-close-icon:after {
	content: "X";
	display: block;
	width: 15px;
	height: 15px;
	text-align: center;
	color:#000;
	font-weight: normal;
	font-size: 12px;
	cursor: pointer;
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
  align-items: flex-end;
}


/* <DEPRECATED> */ .p-TabBar[data-orientation='vertical'], /* </DEPRECATED> */
.lm-TabBar[data-orientation='vertical'] {
  flex-direction: column;
  align-items: flex-end;
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


.lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing : border-box;
}


/* <DEPRECATED> */ .p-TabBar-tab.p-mod-hidden, /* </DEPRECATED> */
.lm-TabBar-tab.lm-mod-hidden {
  display: none !important;
}


.lm-TabBar-addButton.lm-mod-hidden {
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
.p-TabBar.p-mod-dragging .p-TabBar-tab.p-mod-dragging,
/* </DEPRECATED> */
.lm-TabBar.lm-mod-dragging .lm-TabBar-tab.lm-mod-dragging {
  transition: none;
}

.lm-TabBar-tabLabel .lm-TabBar-tabInput {
  user-select: all;
  width: 100%;
  box-sizing : border-box;
  background: inherit;
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
html{
  -webkit-box-sizing:border-box;
          box-sizing:border-box; }

*,
*::before,
*::after{
  -webkit-box-sizing:inherit;
          box-sizing:inherit; }

body{
  font-size:14px;
  font-weight:400;
  letter-spacing:0;
  line-height:1.28581;
  text-transform:none;
  color:#182026;
  font-family:-apple-system, "BlinkMacSystemFont", "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Open Sans", "Helvetica Neue", "Icons16", sans-serif; }

p{
  margin-bottom:10px;
  margin-top:0; }

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
  font-size:36px;
  line-height:40px; }

h2.bp3-heading, .bp3-running-text h2{
  font-size:28px;
  line-height:32px; }

h3.bp3-heading, .bp3-running-text h3{
  font-size:22px;
  line-height:25px; }

h4.bp3-heading, .bp3-running-text h4{
  font-size:18px;
  line-height:21px; }

h5.bp3-heading, .bp3-running-text h5{
  font-size:16px;
  line-height:19px; }

h6.bp3-heading, .bp3-running-text h6{
  font-size:14px;
  line-height:16px; }
.bp3-ui-text{
  font-size:14px;
  font-weight:400;
  letter-spacing:0;
  line-height:1.28581;
  text-transform:none; }

.bp3-monospace-text{
  font-family:monospace;
  text-transform:none; }

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
  font-size:14px;
  line-height:1.5; }
  .bp3-running-text h1{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h1{
      color:#f5f8fa; }
  .bp3-running-text h2{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h2{
      color:#f5f8fa; }
  .bp3-running-text h3{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h3{
      color:#f5f8fa; }
  .bp3-running-text h4{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h4{
      color:#f5f8fa; }
  .bp3-running-text h5{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h5{
      color:#f5f8fa; }
  .bp3-running-text h6{
    color:#182026;
    font-weight:600;
    margin-bottom:20px;
    margin-top:40px; }
    .bp3-dark .bp3-running-text h6{
      color:#f5f8fa; }
  .bp3-running-text hr{
    border:none;
    border-bottom:1px solid rgba(16, 22, 26, 0.15);
    margin:20px 0; }
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
  color:#106ba3;
  text-decoration:none; }
  a:hover{
    color:#106ba3;
    cursor:pointer;
    text-decoration:underline; }
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
  font-family:monospace;
  text-transform:none;
  background:rgba(255, 255, 255, 0.7);
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2);
  color:#5c7080;
  font-size:smaller;
  padding:2px 5px; }
  .bp3-dark .bp3-running-text code, .bp3-running-text .bp3-dark code, .bp3-dark .bp3-code{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#a7b6c2; }
  .bp3-running-text a > code, a > .bp3-code{
    color:#137cbd; }
    .bp3-dark .bp3-running-text a > code, .bp3-running-text .bp3-dark a > code, .bp3-dark a > .bp3-code{
      color:inherit; }

.bp3-running-text pre, .bp3-code-block{
  font-family:monospace;
  text-transform:none;
  background:rgba(255, 255, 255, 0.7);
  border-radius:3px;
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.15);
  color:#182026;
  display:block;
  font-size:13px;
  line-height:1.4;
  margin:10px 0;
  padding:13px 15px 12px;
  word-break:break-all;
  word-wrap:break-word; }
  .bp3-dark .bp3-running-text pre, .bp3-running-text .bp3-dark pre, .bp3-dark .bp3-code-block{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
  .bp3-running-text pre > code, .bp3-code-block > code{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:inherit;
    font-size:inherit;
    padding:0; }

.bp3-running-text kbd, .bp3-key{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  color:#5c7080;
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  font-family:inherit;
  font-size:12px;
  height:24px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  line-height:24px;
  min-width:24px;
  padding:3px 6px;
  vertical-align:middle; }
  .bp3-running-text kbd .bp3-icon, .bp3-key .bp3-icon, .bp3-running-text kbd .bp3-icon-standard, .bp3-key .bp3-icon-standard, .bp3-running-text kbd .bp3-icon-large, .bp3-key .bp3-icon-large{
    margin-right:5px; }
  .bp3-dark .bp3-running-text kbd, .bp3-running-text .bp3-dark kbd, .bp3-dark .bp3-key{
    background:#394b59;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.4);
    color:#a7b6c2; }
.bp3-running-text blockquote, .bp3-blockquote{
  border-left:solid 4px rgba(167, 182, 194, 0.5);
  margin:0 0 10px;
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
  list-style:none;
  margin:0;
  padding:0; }
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
    font-size:40px;
    margin-right:20px;
    margin-top:0; }

.bp3-alert-contents{
  word-break:break-word; }

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
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  cursor:default;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-wrap:wrap;
      flex-wrap:wrap;
  height:30px;
  list-style:none;
  margin:0;
  padding:0; }
  .bp3-breadcrumbs > li{
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex; }
    .bp3-breadcrumbs > li::after{
      background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M10.71 7.29l-4-4a1.003 1.003 0 00-1.42 1.42L8.59 8 5.3 11.29c-.19.18-.3.43-.3.71a1.003 1.003 0 001.71.71l4-4c.18-.18.29-.43.29-.71 0-.28-.11-.53-.29-.71z' fill='%235C7080'/%3e%3c/svg%3e");
      content:"";
      display:block;
      height:16px;
      margin:0 5px;
      width:16px; }
    .bp3-breadcrumbs > li:last-of-type::after{
      display:none; }

.bp3-breadcrumb,
.bp3-breadcrumb-current,
.bp3-breadcrumbs-collapsed{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-inline-box;
  display:-ms-inline-flexbox;
  display:inline-flex;
  font-size:16px; }

.bp3-breadcrumb,
.bp3-breadcrumbs-collapsed{
  color:#5c7080; }

.bp3-breadcrumb:hover{
  text-decoration:none; }

.bp3-breadcrumb.bp3-disabled{
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-breadcrumb .bp3-icon{
  margin-right:5px; }

.bp3-breadcrumb-current{
  color:inherit;
  font-weight:600; }
  .bp3-breadcrumb-current .bp3-input{
    font-size:inherit;
    font-weight:inherit;
    vertical-align:baseline; }

.bp3-breadcrumbs-collapsed{
  background:#ced9e0;
  border:none;
  border-radius:3px;
  cursor:pointer;
  margin-right:2px;
  padding:1px 5px;
  vertical-align:text-bottom; }
  .bp3-breadcrumbs-collapsed::before{
    background:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cg fill='%235C7080'%3e%3ccircle cx='2' cy='8.03' r='2'/%3e%3ccircle cx='14' cy='8.03' r='2'/%3e%3ccircle cx='8' cy='8.03' r='2'/%3e%3c/g%3e%3c/svg%3e") center no-repeat;
    content:"";
    display:block;
    height:16px;
    width:16px; }
  .bp3-breadcrumbs-collapsed:hover{
    background:#bfccd6;
    color:#182026;
    text-decoration:none; }

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
  border:none;
  border-radius:3px;
  cursor:pointer;
  font-size:14px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  padding:5px 10px;
  text-align:left;
  vertical-align:middle;
  min-height:30px;
  min-width:30px; }
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
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    color:#182026; }
    .bp3-button:not([class*="bp3-intent-"]):hover{
      background-clip:padding-box;
      background-color:#ebf1f5;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
    .bp3-button:not([class*="bp3-intent-"]):active, .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      background-color:#d8e1e8;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed;
      outline:none; }
      .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]):disabled.bp3-active:hover, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active, .bp3-button:not([class*="bp3-intent-"]).bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-button.bp3-intent-primary{
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover, .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-primary:hover{
      background-color:#106ba3;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-primary:active, .bp3-button.bp3-intent-primary.bp3-active{
      background-color:#0e5a8a;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-primary:disabled, .bp3-button.bp3-intent-primary.bp3-disabled{
      background-color:rgba(19, 124, 189, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-success{
    background-color:#0f9960;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-success:hover, .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-success:hover{
      background-color:#0d8050;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-success:active, .bp3-button.bp3-intent-success.bp3-active{
      background-color:#0a6640;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-success:disabled, .bp3-button.bp3-intent-success.bp3-disabled{
      background-color:rgba(15, 153, 96, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-warning{
    background-color:#d9822b;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover, .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-warning:hover{
      background-color:#bf7326;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-warning:active, .bp3-button.bp3-intent-warning.bp3-active{
      background-color:#a66321;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-warning:disabled, .bp3-button.bp3-intent-warning.bp3-disabled{
      background-color:rgba(217, 130, 43, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button.bp3-intent-danger{
    background-color:#db3737;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover, .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      color:#ffffff; }
    .bp3-button.bp3-intent-danger:hover{
      background-color:#c23030;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-danger:active, .bp3-button.bp3-intent-danger.bp3-active{
      background-color:#a82a2a;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-button.bp3-intent-danger:disabled, .bp3-button.bp3-intent-danger.bp3-disabled{
      background-color:rgba(219, 55, 55, 0.5);
      background-image:none;
      border-color:transparent;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.6); }
  .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
    stroke:#ffffff; }
  .bp3-button.bp3-large,
  .bp3-large .bp3-button{
    min-height:40px;
    min-width:40px;
    font-size:16px;
    padding:5px 15px; }
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
    min-height:24px;
    min-width:24px;
    padding:0 7px; }
  .bp3-button.bp3-loading{
    position:relative; }
    .bp3-button.bp3-loading[class*="bp3-icon-"]::before{
      visibility:hidden; }
    .bp3-button.bp3-loading .bp3-button-spinner{
      margin:0;
      position:absolute; }
    .bp3-button.bp3-loading > :not(.bp3-button-spinner){
      visibility:hidden; }
  .bp3-button[class*="bp3-icon-"]::before{
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-style:normal;
    font-weight:400;
    line-height:1;
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
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover, .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):hover{
      background-color:#30404d;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):active, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-active{
      background-color:#202b33;
      background-image:none;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-button:not([class*="bp3-intent-"]):disabled, .bp3-dark .bp3-button:not([class*="bp3-intent-"]).bp3-disabled{
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
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
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(255, 255, 255, 0.3); }
    .bp3-dark .bp3-button[class*="bp3-intent-"] .bp3-button-spinner .bp3-spinner-head{
      stroke:#8a9ba8; }
  .bp3-button:disabled::before,
  .bp3-button:disabled .bp3-icon, .bp3-button:disabled .bp3-icon-standard, .bp3-button:disabled .bp3-icon-large, .bp3-button.bp3-disabled::before,
  .bp3-button.bp3-disabled .bp3-icon, .bp3-button.bp3-disabled .bp3-icon-standard, .bp3-button.bp3-disabled .bp3-icon-large, .bp3-button[class*="bp3-intent-"]::before,
  .bp3-button[class*="bp3-intent-"] .bp3-icon, .bp3-button[class*="bp3-intent-"] .bp3-icon-standard, .bp3-button[class*="bp3-intent-"] .bp3-icon-large{
    color:inherit !important; }
  .bp3-button.bp3-minimal{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-button.bp3-minimal:hover{
      background:rgba(167, 182, 194, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026;
      text-decoration:none; }
    .bp3-button.bp3-minimal:active, .bp3-button.bp3-minimal.bp3-active{
      background:rgba(115, 134, 148, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026; }
    .bp3-button.bp3-minimal:disabled, .bp3-button.bp3-minimal:disabled:hover, .bp3-button.bp3-minimal.bp3-disabled, .bp3-button.bp3-minimal.bp3-disabled:hover{
      background:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed; }
      .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-minimal{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-minimal:hover, .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none; }
      .bp3-dark .bp3-button.bp3-minimal:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-minimal:active, .bp3-dark .bp3-button.bp3-minimal.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-minimal:disabled, .bp3-dark .bp3-button.bp3-minimal:disabled:hover, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover{
        background:none;
        color:rgba(167, 182, 194, 0.6);
        cursor:not-allowed; }
        .bp3-dark .bp3-button.bp3-minimal:disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-minimal.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-minimal.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-minimal.bp3-intent-primary:hover, .bp3-button.bp3-minimal.bp3-intent-primary:active, .bp3-button.bp3-minimal.bp3-intent-primary.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
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
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
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
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
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
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
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
  .bp3-button.bp3-outlined{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    border:1px solid rgba(24, 32, 38, 0.2);
    -webkit-box-sizing:border-box;
            box-sizing:border-box; }
    .bp3-button.bp3-outlined:hover{
      background:rgba(167, 182, 194, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026;
      text-decoration:none; }
    .bp3-button.bp3-outlined:active, .bp3-button.bp3-outlined.bp3-active{
      background:rgba(115, 134, 148, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026; }
    .bp3-button.bp3-outlined:disabled, .bp3-button.bp3-outlined:disabled:hover, .bp3-button.bp3-outlined.bp3-disabled, .bp3-button.bp3-outlined.bp3-disabled:hover{
      background:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed; }
      .bp3-button.bp3-outlined:disabled.bp3-active, .bp3-button.bp3-outlined:disabled:hover.bp3-active, .bp3-button.bp3-outlined.bp3-disabled.bp3-active, .bp3-button.bp3-outlined.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button.bp3-outlined{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:inherit; }
      .bp3-dark .bp3-button.bp3-outlined:hover, .bp3-dark .bp3-button.bp3-outlined:active, .bp3-dark .bp3-button.bp3-outlined.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none; }
      .bp3-dark .bp3-button.bp3-outlined:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button.bp3-outlined:active, .bp3-dark .bp3-button.bp3-outlined.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button.bp3-outlined:disabled, .bp3-dark .bp3-button.bp3-outlined:disabled:hover, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled:hover{
        background:none;
        color:rgba(167, 182, 194, 0.6);
        cursor:not-allowed; }
        .bp3-dark .bp3-button.bp3-outlined:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined:disabled:hover.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:hover, .bp3-button.bp3-outlined.bp3-intent-primary:active, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:hover{
        background:rgba(19, 124, 189, 0.15);
        color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:active, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-active{
        background:rgba(19, 124, 189, 0.3);
        color:#106ba3; }
      .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
        background:none;
        color:rgba(16, 107, 163, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-primary:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled.bp3-active{
          background:rgba(19, 124, 189, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-primary .bp3-button-spinner .bp3-spinner-head{
        stroke:#106ba3; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary{
        color:#48aff0; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:hover{
          background:rgba(19, 124, 189, 0.2);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-active{
          background:rgba(19, 124, 189, 0.3);
          color:#48aff0; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
          background:none;
          color:rgba(72, 175, 240, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled.bp3-active{
            background:rgba(19, 124, 189, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-success{
      color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:hover, .bp3-button.bp3-outlined.bp3-intent-success:active, .bp3-button.bp3-outlined.bp3-intent-success.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:hover{
        background:rgba(15, 153, 96, 0.15);
        color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:active, .bp3-button.bp3-outlined.bp3-intent-success.bp3-active{
        background:rgba(15, 153, 96, 0.3);
        color:#0d8050; }
      .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
        background:none;
        color:rgba(13, 128, 80, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-success:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled.bp3-active{
          background:rgba(15, 153, 96, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-success .bp3-button-spinner .bp3-spinner-head{
        stroke:#0d8050; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success{
        color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:hover{
          background:rgba(15, 153, 96, 0.2);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-active{
          background:rgba(15, 153, 96, 0.3);
          color:#3dcc91; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
          background:none;
          color:rgba(61, 204, 145, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled.bp3-active{
            background:rgba(15, 153, 96, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-warning{
      color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:hover, .bp3-button.bp3-outlined.bp3-intent-warning:active, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:hover{
        background:rgba(217, 130, 43, 0.15);
        color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:active, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-active{
        background:rgba(217, 130, 43, 0.3);
        color:#bf7326; }
      .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
        background:none;
        color:rgba(191, 115, 38, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-warning:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled.bp3-active{
          background:rgba(217, 130, 43, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-warning .bp3-button-spinner .bp3-spinner-head{
        stroke:#bf7326; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning{
        color:#ffb366; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:hover{
          background:rgba(217, 130, 43, 0.2);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-active{
          background:rgba(217, 130, 43, 0.3);
          color:#ffb366; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
          background:none;
          color:rgba(255, 179, 102, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled.bp3-active{
            background:rgba(217, 130, 43, 0.3); }
    .bp3-button.bp3-outlined.bp3-intent-danger{
      color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:hover, .bp3-button.bp3-outlined.bp3-intent-danger:active, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:hover{
        background:rgba(219, 55, 55, 0.15);
        color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:active, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-active{
        background:rgba(219, 55, 55, 0.3);
        color:#c23030; }
      .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
        background:none;
        color:rgba(194, 48, 48, 0.5); }
        .bp3-button.bp3-outlined.bp3-intent-danger:disabled.bp3-active, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled.bp3-active{
          background:rgba(219, 55, 55, 0.3); }
      .bp3-button.bp3-outlined.bp3-intent-danger .bp3-button-spinner .bp3-spinner-head{
        stroke:#c23030; }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger{
        color:#ff7373; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:hover{
          background:rgba(219, 55, 55, 0.2);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-active{
          background:rgba(219, 55, 55, 0.3);
          color:#ff7373; }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
          background:none;
          color:rgba(255, 115, 115, 0.5); }
          .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:disabled.bp3-active, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled.bp3-active{
            background:rgba(219, 55, 55, 0.3); }
    .bp3-button.bp3-outlined:disabled, .bp3-button.bp3-outlined.bp3-disabled, .bp3-button.bp3-outlined:disabled:hover, .bp3-button.bp3-outlined.bp3-disabled:hover{
      border-color:rgba(92, 112, 128, 0.1); }
    .bp3-dark .bp3-button.bp3-outlined{
      border-color:rgba(255, 255, 255, 0.4); }
      .bp3-dark .bp3-button.bp3-outlined:disabled, .bp3-dark .bp3-button.bp3-outlined:disabled:hover, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-disabled:hover{
        border-color:rgba(255, 255, 255, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-primary{
      border-color:rgba(16, 107, 163, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
        border-color:rgba(16, 107, 163, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary{
        border-color:rgba(72, 175, 240, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-primary.bp3-disabled{
          border-color:rgba(72, 175, 240, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-success{
      border-color:rgba(13, 128, 80, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
        border-color:rgba(13, 128, 80, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success{
        border-color:rgba(61, 204, 145, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-success.bp3-disabled{
          border-color:rgba(61, 204, 145, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-warning{
      border-color:rgba(191, 115, 38, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
        border-color:rgba(191, 115, 38, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning{
        border-color:rgba(255, 179, 102, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-warning.bp3-disabled{
          border-color:rgba(255, 179, 102, 0.2); }
    .bp3-button.bp3-outlined.bp3-intent-danger{
      border-color:rgba(194, 48, 48, 0.6); }
      .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
        border-color:rgba(194, 48, 48, 0.2); }
      .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger{
        border-color:rgba(255, 115, 115, 0.6); }
        .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger:disabled, .bp3-dark .bp3-button.bp3-outlined.bp3-intent-danger.bp3-disabled{
          border-color:rgba(255, 115, 115, 0.2); }

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
    border-bottom-left-radius:0;
    border-top-left-radius:0; }
  .bp3-button-group:not(.bp3-minimal) > .bp3-popover-wrapper:not(:last-child) .bp3-button,
  .bp3-button-group:not(.bp3-minimal) > .bp3-button:not(:last-child){
    border-bottom-right-radius:0;
    border-top-right-radius:0;
    margin-right:-1px; }
  .bp3-button-group.bp3-minimal .bp3-button{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none; }
    .bp3-button-group.bp3-minimal .bp3-button:hover{
      background:rgba(167, 182, 194, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026;
      text-decoration:none; }
    .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
      background:rgba(115, 134, 148, 0.3);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:#182026; }
    .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
      background:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed; }
      .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
        background:rgba(115, 134, 148, 0.3); }
    .bp3-dark .bp3-button-group.bp3-minimal .bp3-button{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:inherit; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:hover{
        background:rgba(138, 155, 168, 0.15); }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-active{
        background:rgba(138, 155, 168, 0.3);
        color:#f5f8fa; }
      .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover{
        background:none;
        color:rgba(167, 182, 194, 0.6);
        cursor:not-allowed; }
        .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button:disabled:hover.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled.bp3-active, .bp3-dark .bp3-button-group.bp3-minimal .bp3-button.bp3-disabled:hover.bp3-active{
          background:rgba(138, 155, 168, 0.3); }
    .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary{
      color:#106ba3; }
      .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:hover, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary:active, .bp3-button-group.bp3-minimal .bp3-button.bp3-intent-primary.bp3-active{
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
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
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
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
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
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
        background:none;
        -webkit-box-shadow:none;
                box-shadow:none;
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
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column;
    vertical-align:top; }
    .bp3-button-group.bp3-vertical.bp3-fill{
      height:100%;
      width:unset; }
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
  font-size:14px;
  line-height:1.5;
  background-color:rgba(138, 155, 168, 0.15);
  border-radius:3px;
  padding:10px 12px 9px;
  position:relative;
  width:100%; }
  .bp3-callout[class*="bp3-icon-"]{
    padding-left:40px; }
    .bp3-callout[class*="bp3-icon-"]::before{
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-style:normal;
      font-weight:400;
      line-height:1;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      color:#5c7080;
      left:10px;
      position:absolute;
      top:10px; }
  .bp3-callout.bp3-callout-icon{
    padding-left:40px; }
    .bp3-callout.bp3-callout-icon > .bp3-icon:first-child{
      color:#5c7080;
      left:10px;
      position:absolute;
      top:10px; }
  .bp3-callout .bp3-heading{
    line-height:20px;
    margin-bottom:5px;
    margin-top:0; }
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
  background-color:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.15), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
  padding:20px;
  -webkit-transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-transform 200ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-card.bp3-dark,
  .bp3-dark .bp3-card{
    background-color:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), 0 0 0 rgba(16, 22, 26, 0), 0 0 0 rgba(16, 22, 26, 0); }

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
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  opacity:0.9;
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
  border-bottom:1px solid rgba(16, 22, 26, 0.15);
  border-right:1px solid rgba(16, 22, 26, 0.15);
  margin:5px; }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
.bp3-dialog-container{
  opacity:1;
  -webkit-transform:scale(1);
          transform:scale(1);
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  min-height:100%;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none;
  width:100%; }
  .bp3-dialog-container.bp3-overlay-enter > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5); }
  .bp3-dialog-container.bp3-overlay-enter-active > .bp3-dialog, .bp3-dialog-container.bp3-overlay-appear-active > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-dialog-container.bp3-overlay-exit > .bp3-dialog{
    opacity:1;
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-dialog-container.bp3-overlay-exit-active > .bp3-dialog{
    opacity:0;
    -webkit-transform:scale(0.5);
            transform:scale(0.5);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:opacity, -webkit-transform;
    transition-property:opacity, -webkit-transform;
    transition-property:opacity, transform;
    transition-property:opacity, transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }

.bp3-dialog{
  background:#ebf1f5;
  border-radius:6px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:30px 0;
  padding-bottom:20px;
  pointer-events:all;
  -webkit-user-select:text;
     -moz-user-select:text;
      -ms-user-select:text;
          user-select:text;
  width:500px; }
  .bp3-dialog:focus{
    outline:0; }
  .bp3-dialog.bp3-dark,
  .bp3-dark .bp3-dialog{
    background:#293742;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }

.bp3-dialog-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background:#ffffff;
  border-radius:6px 6px 0 0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  min-height:40px;
  padding-left:20px;
  padding-right:5px;
  z-index:30; }
  .bp3-dialog-header .bp3-icon-large,
  .bp3-dialog-header .bp3-icon{
    color:#5c7080;
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px; }
  .bp3-dialog-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    line-height:inherit;
    margin:0; }
    .bp3-dialog-header .bp3-heading:last-child{
      margin-right:20px; }
  .bp3-dark .bp3-dialog-header{
    background:#30404d;
    -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:0 1px 0 rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-dialog-header .bp3-icon-large,
    .bp3-dark .bp3-dialog-header .bp3-icon{
      color:#a7b6c2; }

.bp3-dialog-body{
  -webkit-box-flex:1;
      -ms-flex:1 1 auto;
          flex:1 1 auto;
  line-height:18px;
  margin:20px; }

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
.bp3-multistep-dialog-panels{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex; }

.bp3-multistep-dialog-left-panel{
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:1;
      -ms-flex:1;
          flex:1;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column; }
  .bp3-dark .bp3-multistep-dialog-left-panel{
    background:#202b33; }

.bp3-multistep-dialog-right-panel{
  background-color:#f5f8fa;
  border-left:1px solid rgba(16, 22, 26, 0.15);
  border-radius:0 0 6px 0;
  -webkit-box-flex:3;
      -ms-flex:3;
          flex:3;
  min-width:0; }
  .bp3-dark .bp3-multistep-dialog-right-panel{
    background-color:#293742;
    border-left:1px solid rgba(16, 22, 26, 0.4); }

.bp3-multistep-dialog-footer{
  background-color:#ffffff;
  border-radius:0 0 6px 0;
  border-top:1px solid rgba(16, 22, 26, 0.15);
  padding:10px; }
  .bp3-dark .bp3-multistep-dialog-footer{
    background:#30404d;
    border-top:1px solid rgba(16, 22, 26, 0.4); }

.bp3-dialog-step-container{
  background-color:#f5f8fa;
  border-bottom:1px solid rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-dialog-step-container{
    background:#293742;
    border-bottom:1px solid rgba(16, 22, 26, 0.4); }
  .bp3-dialog-step-container.bp3-dialog-step-viewed{
    background-color:#ffffff; }
    .bp3-dark .bp3-dialog-step-container.bp3-dialog-step-viewed{
      background:#30404d; }

.bp3-dialog-step{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background-color:#f5f8fa;
  border-radius:6px;
  cursor:not-allowed;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  margin:4px;
  padding:6px 14px; }
  .bp3-dark .bp3-dialog-step{
    background:#293742; }
  .bp3-dialog-step-viewed .bp3-dialog-step{
    background-color:#ffffff;
    cursor:pointer; }
    .bp3-dark .bp3-dialog-step-viewed .bp3-dialog-step{
      background:#30404d; }
  .bp3-dialog-step:hover{
    background-color:#f5f8fa; }
    .bp3-dark .bp3-dialog-step:hover{
      background:#293742; }

.bp3-dialog-step-icon{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  background-color:rgba(92, 112, 128, 0.6);
  border-radius:50%;
  color:#ffffff;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  height:25px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  width:25px; }
  .bp3-dark .bp3-dialog-step-icon{
    background-color:rgba(167, 182, 194, 0.6); }
  .bp3-active.bp3-dialog-step-viewed .bp3-dialog-step-icon{
    background-color:#2b95d6; }
  .bp3-dialog-step-viewed .bp3-dialog-step-icon{
    background-color:#8a9ba8; }

.bp3-dialog-step-title{
  color:rgba(92, 112, 128, 0.6);
  -webkit-box-flex:1;
      -ms-flex:1;
          flex:1;
  padding-left:10px; }
  .bp3-dark .bp3-dialog-step-title{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-active.bp3-dialog-step-viewed .bp3-dialog-step-title{
    color:#2b95d6; }
  .bp3-dialog-step-viewed:not(.bp3-active) .bp3-dialog-step-title{
    color:#182026; }
    .bp3-dark .bp3-dialog-step-viewed:not(.bp3-active) .bp3-dialog-step-title{
      color:#f5f8fa; }
.bp3-drawer{
  background:#ffffff;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin:0;
  padding:0; }
  .bp3-drawer:focus{
    outline:0; }
  .bp3-drawer.bp3-position-top{
    height:50%;
    left:0;
    right:0;
    top:0; }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter, .bp3-drawer.bp3-position-top.bp3-overlay-appear{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%); }
    .bp3-drawer.bp3-position-top.bp3-overlay-enter-active, .bp3-drawer.bp3-position-top.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-top.bp3-overlay-exit-active{
      -webkit-transform:translateY(-100%);
              transform:translateY(-100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-position-bottom{
    bottom:0;
    height:50%;
    left:0;
    right:0; }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear{
      -webkit-transform:translateY(100%);
              transform:translateY(100%); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-enter-active, .bp3-drawer.bp3-position-bottom.bp3-overlay-appear-active{
      -webkit-transform:translateY(0);
              transform:translateY(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer.bp3-position-bottom.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-position-left{
    bottom:0;
    left:0;
    top:0;
    width:50%; }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter, .bp3-drawer.bp3-position-left.bp3-overlay-appear{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%); }
    .bp3-drawer.bp3-position-left.bp3-overlay-enter-active, .bp3-drawer.bp3-position-left.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-left.bp3-overlay-exit-active{
      -webkit-transform:translateX(-100%);
              transform:translateX(-100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-position-right{
    bottom:0;
    right:0;
    top:0;
    width:50%; }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter, .bp3-drawer.bp3-position-right.bp3-overlay-appear{
      -webkit-transform:translateX(100%);
              transform:translateX(100%); }
    .bp3-drawer.bp3-position-right.bp3-overlay-enter-active, .bp3-drawer.bp3-position-right.bp3-overlay-appear-active{
      -webkit-transform:translateX(0);
              transform:translateX(0);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer.bp3-position-right.bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right):not(.bp3-vertical){
    bottom:0;
    right:0;
    top:0;
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
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit{
      -webkit-transform:translateX(0);
              transform:translateX(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right):not(.bp3-vertical).bp3-overlay-exit-active{
      -webkit-transform:translateX(100%);
              transform:translateX(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
  .bp3-position-right).bp3-vertical{
    bottom:0;
    height:50%;
    left:0;
    right:0; }
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
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:200ms;
              transition-duration:200ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit{
      -webkit-transform:translateY(0);
              transform:translateY(0); }
    .bp3-drawer:not(.bp3-position-top):not(.bp3-position-bottom):not(.bp3-position-left):not(
    .bp3-position-right).bp3-vertical.bp3-overlay-exit-active{
      -webkit-transform:translateY(100%);
              transform:translateY(100%);
      -webkit-transition-delay:0;
              transition-delay:0;
      -webkit-transition-duration:100ms;
              transition-duration:100ms;
      -webkit-transition-property:-webkit-transform;
      transition-property:-webkit-transform;
      transition-property:transform;
      transition-property:transform, -webkit-transform;
      -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
              transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-drawer.bp3-dark,
  .bp3-dark .bp3-drawer{
    background:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }

.bp3-drawer-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  border-radius:0;
  -webkit-box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:0 1px 0 rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  min-height:40px;
  padding:5px;
  padding-left:20px;
  position:relative; }
  .bp3-drawer-header .bp3-icon-large,
  .bp3-drawer-header .bp3-icon{
    color:#5c7080;
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    margin-right:10px; }
  .bp3-drawer-header .bp3-heading{
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    line-height:inherit;
    margin:0; }
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
  line-height:18px;
  overflow:auto; }

.bp3-drawer-footer{
  -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  padding:10px 20px;
  position:relative; }
  .bp3-dark .bp3-drawer-footer{
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.4); }
.bp3-editable-text{
  cursor:text;
  display:inline-block;
  max-width:100%;
  position:relative;
  vertical-align:top;
  white-space:nowrap; }
  .bp3-editable-text::before{
    bottom:-3px;
    left:-3px;
    position:absolute;
    right:-3px;
    top:-3px;
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
    background-color:#ffffff;
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
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
    background-color:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
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
  color:inherit;
  display:inherit;
  font:inherit;
  letter-spacing:inherit;
  max-width:inherit;
  min-width:inherit;
  position:relative;
  resize:none;
  text-transform:inherit;
  vertical-align:top; }

.bp3-editable-text-input{
  background:none;
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0;
  white-space:pre-wrap;
  width:100%; }
  .bp3-editable-text-input::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-editable-text-input::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
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
    left:0;
    position:absolute;
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
.bp3-divider{
  border-bottom:1px solid rgba(16, 22, 26, 0.15);
  border-right:1px solid rgba(16, 22, 26, 0.15);
  margin:5px; }
  .bp3-dark .bp3-divider{
    border-color:rgba(16, 22, 26, 0.4); }
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
    border-radius:inherit;
    z-index:2; }
    .bp3-control-group .bp3-input:focus{
      border-radius:3px;
      z-index:14; }
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
    border-radius:inherit;
    z-index:4; }
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
  .bp3-control-group .bp3-input-group > .bp3-input-left-container,
  .bp3-control-group .bp3-input-group > .bp3-input-action{
    z-index:16; }
  .bp3-control-group .bp3-select::after,
  .bp3-control-group .bp3-html-select::after,
  .bp3-control-group .bp3-select > .bp3-icon,
  .bp3-control-group .bp3-html-select > .bp3-icon{
    z-index:17; }
  .bp3-control-group .bp3-select:focus-within{
    z-index:5; }
  .bp3-control-group:not(.bp3-vertical) > *:not(.bp3-divider){
    margin-right:-1px; }
  .bp3-control-group:not(.bp3-vertical) > .bp3-divider:not(:first-child){
    margin-left:6px; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > *:not(.bp3-divider){
    margin-right:0; }
  .bp3-dark .bp3-control-group:not(.bp3-vertical) > .bp3-button + .bp3-button{
    margin-left:1px; }
  .bp3-control-group .bp3-popover-wrapper,
  .bp3-control-group .bp3-popover-target{
    border-radius:inherit; }
  .bp3-control-group > :first-child{
    border-radius:3px 0 0 3px; }
  .bp3-control-group > :last-child{
    border-radius:0 3px 3px 0;
    margin-right:0; }
  .bp3-control-group > :only-child{
    border-radius:3px;
    margin-right:0; }
  .bp3-control-group .bp3-input-group .bp3-button{
    border-radius:3px; }
  .bp3-control-group .bp3-numeric-input:not(:first-child) .bp3-input-group{
    border-bottom-left-radius:0;
    border-top-left-radius:0; }
  .bp3-control-group.bp3-fill{
    width:100%; }
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
      border-radius:3px 3px 0 0;
      margin-top:0; }
    .bp3-control-group.bp3-vertical > :last-child{
      border-radius:0 0 3px 3px; }
.bp3-control{
  cursor:pointer;
  display:block;
  margin-bottom:10px;
  position:relative;
  text-transform:none; }
  .bp3-control input:checked ~ .bp3-control-indicator{
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
  .bp3-control:hover input:checked ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
  .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    background:#0e5a8a;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-control input:checked ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control:hover input:checked ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control input:not(:disabled):active:checked ~ .bp3-control-indicator{
    background-color:#0e5a8a;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-control input:disabled:checked ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-control:not(.bp3-align-right){
    padding-left:26px; }
    .bp3-control:not(.bp3-align-right) .bp3-control-indicator{
      margin-left:-26px; }
  .bp3-control.bp3-align-right{
    padding-right:26px; }
    .bp3-control.bp3-align-right .bp3-control-indicator{
      margin-right:-26px; }
  .bp3-control.bp3-disabled{
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
  .bp3-control.bp3-inline{
    display:inline-block;
    margin-right:20px; }
  .bp3-control input{
    left:0;
    opacity:0;
    position:absolute;
    top:0;
    z-index:-1; }
  .bp3-control .bp3-control-indicator{
    background-clip:padding-box;
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    border:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    cursor:pointer;
    display:inline-block;
    font-size:16px;
    height:1em;
    margin-right:10px;
    margin-top:-3px;
    position:relative;
    -webkit-user-select:none;
       -moz-user-select:none;
        -ms-user-select:none;
            user-select:none;
    vertical-align:middle;
    width:1em; }
    .bp3-control .bp3-control-indicator::before{
      content:"";
      display:block;
      height:1em;
      width:1em; }
  .bp3-control:hover .bp3-control-indicator{
    background-color:#ebf1f5; }
  .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
    background:#d8e1e8;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-control input:disabled ~ .bp3-control-indicator{
    background:rgba(206, 217, 224, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none;
    cursor:not-allowed; }
  .bp3-control input:focus ~ .bp3-control-indicator{
    outline:rgba(19, 124, 189, 0.6) auto 2px;
    outline-offset:2px;
    -moz-outline-radius:6px; }
  .bp3-control.bp3-align-right .bp3-control-indicator{
    float:right;
    margin-left:10px;
    margin-top:1px; }
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
    background-color:#137cbd;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.1)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
    color:#ffffff; }
  .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 -1px 0 rgba(16, 22, 26, 0.2); }
  .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    background:#0e5a8a;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    background:rgba(19, 124, 189, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-dark .bp3-control.bp3-checkbox input:indeterminate ~ .bp3-control-indicator{
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox:hover input:indeterminate ~ .bp3-control-indicator{
    background-color:#106ba3;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-checkbox input:not(:disabled):active:indeterminate ~ .bp3-control-indicator{
    background-color:#0e5a8a;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
    background:rgba(14, 90, 138, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-control.bp3-checkbox .bp3-control-indicator{
    border-radius:3px; }
  .bp3-control.bp3-checkbox input:checked ~ .bp3-control-indicator::before{
    background-image:url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 16 16'%3e%3cpath fill-rule='evenodd' clip-rule='evenodd' d='M12 5c-.28 0-.53.11-.71.29L7 9.59l-2.29-2.3a1.003 1.003 0 00-1.42 1.42l3 3c.18.18.43.29.71.29s.53-.11.71-.29l5-5A1.003 1.003 0 0012 5z' fill='white'/%3e%3c/svg%3e"); }
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
    min-width:1.75em;
    -webkit-transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:background-color 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
    width:auto; }
    .bp3-control.bp3-switch .bp3-control-indicator::before{
      background:#ffffff;
      border-radius:50%;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
      height:calc(1em - 4px);
      left:0;
      margin:2px;
      position:absolute;
      -webkit-transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      transition:left 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
      width:calc(1em - 4px); }
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
    background:#394b59;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator::before{
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-control.bp3-switch .bp3-switch-inner-text{
    font-size:0.7em;
    text-align:center; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:first-child{
    line-height:0;
    margin-left:0.5em;
    margin-right:1.2em;
    visibility:hidden; }
  .bp3-control.bp3-switch .bp3-control-indicator-child:last-child{
    line-height:1em;
    margin-left:1.2em;
    margin-right:0.5em;
    visibility:visible; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:first-child{
    line-height:1em;
    visibility:visible; }
  .bp3-control.bp3-switch input:checked ~ .bp3-control-indicator .bp3-control-indicator-child:last-child{
    line-height:0;
    visibility:hidden; }
  .bp3-dark .bp3-control{
    color:#f5f8fa; }
    .bp3-dark .bp3-control.bp3-disabled{
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-control .bp3-control-indicator{
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-control:hover .bp3-control-indicator{
      background-color:#30404d; }
    .bp3-dark .bp3-control input:not(:disabled):active ~ .bp3-control-indicator{
      background:#202b33;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-control input:disabled ~ .bp3-control-indicator{
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      cursor:not-allowed; }
    .bp3-dark .bp3-control.bp3-checkbox input:disabled:checked ~ .bp3-control-indicator, .bp3-dark .bp3-control.bp3-checkbox input:disabled:indeterminate ~ .bp3-control-indicator{
      color:rgba(167, 182, 194, 0.6); }
.bp3-file-input{
  cursor:pointer;
  display:inline-block;
  height:30px;
  position:relative; }
  .bp3-file-input input{
    margin:0;
    min-width:200px;
    opacity:0; }
    .bp3-file-input input:disabled + .bp3-file-upload-input,
    .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
      background:rgba(206, 217, 224, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed;
      resize:none; }
      .bp3-file-input input:disabled + .bp3-file-upload-input::after,
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
        background-color:rgba(206, 217, 224, 0.5);
        background-image:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:rgba(92, 112, 128, 0.6);
        cursor:not-allowed;
        outline:none; }
        .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active, .bp3-file-input input:disabled + .bp3-file-upload-input::after.bp3-active:hover,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active,
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after.bp3-active:hover{
          background:rgba(206, 217, 224, 0.7); }
      .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input, .bp3-dark
      .bp3-file-input input.bp3-disabled + .bp3-file-upload-input{
        background:rgba(57, 75, 89, 0.5);
        -webkit-box-shadow:none;
                box-shadow:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-input input:disabled + .bp3-file-upload-input::after, .bp3-dark
        .bp3-file-input input.bp3-disabled + .bp3-file-upload-input::after{
          background-color:rgba(57, 75, 89, 0.5);
          background-image:none;
          -webkit-box-shadow:none;
                  box-shadow:none;
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
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  background:#ffffff;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  color:#182026;
  font-size:14px;
  font-weight:400;
  height:30px;
  line-height:30px;
  outline:none;
  padding:0 10px;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  vertical-align:middle;
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  color:rgba(92, 112, 128, 0.6);
  left:0;
  padding-right:80px;
  position:absolute;
  right:0;
  top:0;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-file-upload-input::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-file-upload-input::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
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
    background:rgba(206, 217, 224, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    resize:none; }
  .bp3-file-upload-input::after{
    background-color:#f5f8fa;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    color:#182026;
    min-height:24px;
    min-width:24px;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
    word-wrap:normal;
    border-radius:3px;
    content:"Browse";
    line-height:24px;
    margin:3px;
    position:absolute;
    right:0;
    text-align:center;
    top:0;
    width:70px; }
    .bp3-file-upload-input::after:hover{
      background-clip:padding-box;
      background-color:#ebf1f5;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
    .bp3-file-upload-input::after:active, .bp3-file-upload-input::after.bp3-active{
      background-color:#d8e1e8;
      background-image:none;
      -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-file-upload-input::after:disabled, .bp3-file-upload-input::after.bp3-disabled{
      background-color:rgba(206, 217, 224, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(92, 112, 128, 0.6);
      cursor:not-allowed;
      outline:none; }
      .bp3-file-upload-input::after:disabled.bp3-active, .bp3-file-upload-input::after:disabled.bp3-active:hover, .bp3-file-upload-input::after.bp3-disabled.bp3-active, .bp3-file-upload-input::after.bp3-disabled.bp3-active:hover{
        background:rgba(206, 217, 224, 0.7); }
  .bp3-file-upload-input:hover::after{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
  .bp3-file-upload-input:active::after{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-large .bp3-file-upload-input{
    font-size:16px;
    height:40px;
    line-height:40px;
    padding-right:95px; }
    .bp3-large .bp3-file-upload-input[type="search"], .bp3-large .bp3-file-upload-input.bp3-round{
      padding:0 15px; }
    .bp3-large .bp3-file-upload-input::after{
      min-height:30px;
      min-width:30px;
      line-height:30px;
      margin:5px;
      width:85px; }
  .bp3-dark .bp3-file-upload-input{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
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
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-file-upload-input::after{
      background-color:#394b59;
      background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
      background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
      color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover, .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        color:#f5f8fa; }
      .bp3-dark .bp3-file-upload-input::after:hover{
        background-color:#30404d;
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
      .bp3-dark .bp3-file-upload-input::after:active, .bp3-dark .bp3-file-upload-input::after.bp3-active{
        background-color:#202b33;
        background-image:none;
        -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
                box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
      .bp3-dark .bp3-file-upload-input::after:disabled, .bp3-dark .bp3-file-upload-input::after.bp3-disabled{
        background-color:rgba(57, 75, 89, 0.5);
        background-image:none;
        -webkit-box-shadow:none;
                box-shadow:none;
        color:rgba(167, 182, 194, 0.6); }
        .bp3-dark .bp3-file-upload-input::after:disabled.bp3-active, .bp3-dark .bp3-file-upload-input::after.bp3-disabled.bp3-active{
          background:rgba(57, 75, 89, 0.7); }
      .bp3-dark .bp3-file-upload-input::after .bp3-button-spinner .bp3-spinner-head{
        background:rgba(16, 22, 26, 0.5);
        stroke:#8a9ba8; }
    .bp3-dark .bp3-file-upload-input:hover::after{
      background-color:#30404d;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-file-upload-input:active::after{
      background-color:#202b33;
      background-image:none;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
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
    color:#5c7080;
    font-size:12px;
    margin-top:5px; }
  .bp3-form-group.bp3-intent-primary .bp3-form-helper-text{
    color:#106ba3; }
  .bp3-form-group.bp3-intent-success .bp3-form-helper-text{
    color:#0d8050; }
  .bp3-form-group.bp3-intent-warning .bp3-form-helper-text{
    color:#bf7326; }
  .bp3-form-group.bp3-intent-danger .bp3-form-helper-text{
    color:#c23030; }
  .bp3-form-group.bp3-inline{
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row; }
    .bp3-form-group.bp3-inline.bp3-large label.bp3-label{
      line-height:40px;
      margin:0 10px 0 0; }
    .bp3-form-group.bp3-inline label.bp3-label{
      line-height:30px;
      margin:0 10px 0 0; }
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
  .bp3-input-group > .bp3-input-left-container,
  .bp3-input-group > .bp3-button,
  .bp3-input-group > .bp3-icon{
    position:absolute;
    top:0; }
    .bp3-input-group .bp3-input-action:first-child,
    .bp3-input-group > .bp3-input-left-container:first-child,
    .bp3-input-group > .bp3-button:first-child,
    .bp3-input-group > .bp3-icon:first-child{
      left:0; }
    .bp3-input-group .bp3-input-action:last-child,
    .bp3-input-group > .bp3-input-left-container:last-child,
    .bp3-input-group > .bp3-button:last-child,
    .bp3-input-group > .bp3-icon:last-child{
      right:0; }
  .bp3-input-group .bp3-button{
    min-height:24px;
    min-width:24px;
    margin:3px;
    padding:0 7px; }
    .bp3-input-group .bp3-button:empty{
      padding:0; }
  .bp3-input-group > .bp3-input-left-container,
  .bp3-input-group > .bp3-icon{
    z-index:1; }
  .bp3-input-group > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group > .bp3-icon{
    color:#5c7080; }
    .bp3-input-group > .bp3-input-left-container > .bp3-icon:empty,
    .bp3-input-group > .bp3-icon:empty{
      font-family:"Icons16", sans-serif;
      font-size:16px;
      font-style:normal;
      font-weight:400;
      line-height:1;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased; }
  .bp3-input-group > .bp3-input-left-container > .bp3-icon,
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
    min-height:30px;
    min-width:30px;
    margin:5px; }
  .bp3-input-group.bp3-large > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group.bp3-large > .bp3-icon,
  .bp3-input-group.bp3-large .bp3-input-action > .bp3-spinner{
    margin:12px; }
  .bp3-input-group.bp3-large .bp3-input{
    font-size:16px;
    height:40px;
    line-height:40px; }
    .bp3-input-group.bp3-large .bp3-input[type="search"], .bp3-input-group.bp3-large .bp3-input.bp3-round{
      padding:0 15px; }
    .bp3-input-group.bp3-large .bp3-input:not(:first-child){
      padding-left:40px; }
    .bp3-input-group.bp3-large .bp3-input:not(:last-child){
      padding-right:40px; }
  .bp3-input-group.bp3-small .bp3-button{
    min-height:20px;
    min-width:20px;
    margin:2px; }
  .bp3-input-group.bp3-small .bp3-tag{
    min-height:20px;
    min-width:20px;
    margin:2px; }
  .bp3-input-group.bp3-small > .bp3-input-left-container > .bp3-icon,
  .bp3-input-group.bp3-small > .bp3-icon,
  .bp3-input-group.bp3-small .bp3-input-action > .bp3-spinner{
    margin:4px; }
  .bp3-input-group.bp3-small .bp3-input{
    font-size:12px;
    height:24px;
    line-height:24px;
    padding-left:8px;
    padding-right:8px; }
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
  -webkit-appearance:none;
     -moz-appearance:none;
          appearance:none;
  background:#ffffff;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.15), inset 0 1px 1px rgba(16, 22, 26, 0.2);
  color:#182026;
  font-size:14px;
  font-weight:400;
  height:30px;
  line-height:30px;
  outline:none;
  padding:0 10px;
  -webkit-transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:-webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  transition:box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9), -webkit-box-shadow 100ms cubic-bezier(0.4, 1, 0.75, 0.9);
  vertical-align:middle; }
  .bp3-input::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
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
    background:rgba(206, 217, 224, 0.5);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    resize:none; }
  .bp3-input.bp3-large{
    font-size:16px;
    height:40px;
    line-height:40px; }
    .bp3-input.bp3-large[type="search"], .bp3-input.bp3-large.bp3-round{
      padding:0 15px; }
  .bp3-input.bp3-small{
    font-size:12px;
    height:24px;
    line-height:24px;
    padding-left:8px;
    padding-right:8px; }
    .bp3-input.bp3-small[type="search"], .bp3-input.bp3-small.bp3-round{
      padding:0 12px; }
  .bp3-input.bp3-fill{
    -webkit-box-flex:1;
        -ms-flex:1 1 auto;
            flex:1 1 auto;
    width:100%; }
  .bp3-dark .bp3-input{
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
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
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
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
    background:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), 0 0 0 0 rgba(19, 124, 189, 0), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
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
      background:rgba(57, 75, 89, 0.5);
      -webkit-box-shadow:none;
              box-shadow:none;
      color:rgba(167, 182, 194, 0.6); }
label.bp3-label{
  display:block;
  margin-bottom:15px;
  margin-top:0; }
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
    font-weight:400;
    vertical-align:top;
    width:100%; }
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
  min-height:0;
  padding:0;
  width:30px; }
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
  border:none;
  border-radius:3px;
  cursor:pointer;
  font-size:14px;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  padding:5px 10px;
  text-align:left;
  vertical-align:middle;
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  color:#182026;
  -moz-appearance:none;
  -webkit-appearance:none;
  border-radius:3px;
  height:30px;
  padding:0 25px 0 10px;
  width:100%; }
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
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
  .bp3-html-select select:active,
  .bp3-select select:active, .bp3-html-select select.bp3-active,
  .bp3-select select.bp3-active{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-html-select select:disabled,
  .bp3-select select:disabled, .bp3-html-select select.bp3-disabled,
  .bp3-select select.bp3-disabled{
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    outline:none; }
    .bp3-html-select select:disabled.bp3-active,
    .bp3-select select:disabled.bp3-active, .bp3-html-select select:disabled.bp3-active:hover,
    .bp3-select select:disabled.bp3-active:hover, .bp3-html-select select.bp3-disabled.bp3-active,
    .bp3-select select.bp3-disabled.bp3-active, .bp3-html-select select.bp3-disabled.bp3-active:hover,
    .bp3-select select.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }

.bp3-html-select.bp3-minimal select,
.bp3-select.bp3-minimal select{
  background:none;
  -webkit-box-shadow:none;
          box-shadow:none; }
  .bp3-html-select.bp3-minimal select:hover,
  .bp3-select.bp3-minimal select:hover{
    background:rgba(167, 182, 194, 0.3);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:#182026;
    text-decoration:none; }
  .bp3-html-select.bp3-minimal select:active,
  .bp3-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal select.bp3-active,
  .bp3-select.bp3-minimal select.bp3-active{
    background:rgba(115, 134, 148, 0.3);
    -webkit-box-shadow:none;
            box-shadow:none;
    color:#182026; }
  .bp3-html-select.bp3-minimal select:disabled,
  .bp3-select.bp3-minimal select:disabled, .bp3-html-select.bp3-minimal select:disabled:hover,
  .bp3-select.bp3-minimal select:disabled:hover, .bp3-html-select.bp3-minimal select.bp3-disabled,
  .bp3-select.bp3-minimal select.bp3-disabled, .bp3-html-select.bp3-minimal select.bp3-disabled:hover,
  .bp3-select.bp3-minimal select.bp3-disabled:hover{
    background:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
    .bp3-html-select.bp3-minimal select:disabled.bp3-active,
    .bp3-select.bp3-minimal select:disabled.bp3-active, .bp3-html-select.bp3-minimal select:disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select:disabled:hover.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled.bp3-active, .bp3-html-select.bp3-minimal select.bp3-disabled:hover.bp3-active,
    .bp3-select.bp3-minimal select.bp3-disabled:hover.bp3-active{
      background:rgba(115, 134, 148, 0.3); }
  .bp3-dark .bp3-html-select.bp3-minimal select, .bp3-html-select.bp3-minimal .bp3-dark select,
  .bp3-dark .bp3-select.bp3-minimal select, .bp3-select.bp3-minimal .bp3-dark select{
    background:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:inherit; }
    .bp3-dark .bp3-html-select.bp3-minimal select:hover, .bp3-html-select.bp3-minimal .bp3-dark select:hover,
    .bp3-dark .bp3-select.bp3-minimal select:hover, .bp3-select.bp3-minimal .bp3-dark select:hover, .bp3-dark .bp3-html-select.bp3-minimal select:active, .bp3-html-select.bp3-minimal .bp3-dark select:active,
    .bp3-dark .bp3-select.bp3-minimal select:active, .bp3-select.bp3-minimal .bp3-dark select:active, .bp3-dark .bp3-html-select.bp3-minimal select.bp3-active, .bp3-html-select.bp3-minimal .bp3-dark select.bp3-active,
    .bp3-dark .bp3-select.bp3-minimal select.bp3-active, .bp3-select.bp3-minimal .bp3-dark select.bp3-active{
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none; }
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
      color:rgba(167, 182, 194, 0.6);
      cursor:not-allowed; }
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
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
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
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
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
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
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
      background:none;
      -webkit-box-shadow:none;
              box-shadow:none;
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
  font-size:16px;
  height:40px;
  padding-right:35px; }

.bp3-dark .bp3-html-select select, .bp3-dark .bp3-select select{
  background-color:#394b59;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
  color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover, .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select select:hover, .bp3-dark .bp3-select select:hover{
    background-color:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
  .bp3-dark .bp3-html-select select:active, .bp3-dark .bp3-select select:active, .bp3-dark .bp3-html-select select.bp3-active, .bp3-dark .bp3-select select.bp3-active{
    background-color:#202b33;
    background-image:none;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-dark .bp3-html-select select:disabled, .bp3-dark .bp3-select select:disabled, .bp3-dark .bp3-html-select select.bp3-disabled, .bp3-dark .bp3-select select.bp3-disabled{
    background-color:rgba(57, 75, 89, 0.5);
    background-image:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(167, 182, 194, 0.6); }
    .bp3-dark .bp3-html-select select:disabled.bp3-active, .bp3-dark .bp3-select select:disabled.bp3-active, .bp3-dark .bp3-html-select select.bp3-disabled.bp3-active, .bp3-dark .bp3-select select.bp3-disabled.bp3-active{
      background:rgba(57, 75, 89, 0.7); }
  .bp3-dark .bp3-html-select select .bp3-button-spinner .bp3-spinner-head, .bp3-dark .bp3-select select .bp3-button-spinner .bp3-spinner-head{
    background:rgba(16, 22, 26, 0.5);
    stroke:#8a9ba8; }

.bp3-html-select select:disabled,
.bp3-select select:disabled{
  background-color:rgba(206, 217, 224, 0.5);
  -webkit-box-shadow:none;
          box-shadow:none;
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-html-select .bp3-icon,
.bp3-select .bp3-icon, .bp3-select::after{
  color:#5c7080;
  pointer-events:none;
  position:absolute;
  right:7px;
  top:7px; }
  .bp3-html-select .bp3-disabled.bp3-icon,
  .bp3-select .bp3-disabled.bp3-icon, .bp3-disabled.bp3-select::after{
    color:rgba(92, 112, 128, 0.6); }
.bp3-html-select,
.bp3-select{
  display:inline-block;
  letter-spacing:normal;
  position:relative;
  vertical-align:middle; }
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
    right:12px;
    top:12px; }
  .bp3-html-select.bp3-fill,
  .bp3-html-select.bp3-fill select,
  .bp3-select.bp3-fill,
  .bp3-select.bp3-fill select{
    width:100%; }
  .bp3-dark .bp3-html-select option, .bp3-dark
  .bp3-select option{
    background-color:#30404d;
    color:#f5f8fa; }
  .bp3-dark .bp3-html-select option:disabled, .bp3-dark
  .bp3-select option:disabled{
    color:rgba(167, 182, 194, 0.6); }
  .bp3-dark .bp3-html-select::after, .bp3-dark
  .bp3-select::after{
    color:#a7b6c2; }

.bp3-select::after{
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-style:normal;
  font-weight:400;
  line-height:1;
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
    text-align:left;
    vertical-align:top; }
  .bp3-running-text table th, table.bp3-html-table th{
    color:#182026;
    font-weight:600; }

  .bp3-running-text table td,
  table.bp3-html-table td{
    color:#182026; }
  .bp3-running-text table tbody tr:first-child th, table.bp3-html-table tbody tr:first-child th,
  .bp3-running-text table tbody tr:first-child td,
  table.bp3-html-table tbody tr:first-child td,
  .bp3-running-text table tfoot tr:first-child th,
  table.bp3-html-table tfoot tr:first-child th,
  .bp3-running-text table tfoot tr:first-child td,
  table.bp3-html-table tfoot tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  .bp3-dark .bp3-running-text table th, .bp3-running-text .bp3-dark table th, .bp3-dark table.bp3-html-table th{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table td, .bp3-running-text .bp3-dark table td, .bp3-dark table.bp3-html-table td{
    color:#f5f8fa; }
  .bp3-dark .bp3-running-text table tbody tr:first-child th, .bp3-running-text .bp3-dark table tbody tr:first-child th, .bp3-dark table.bp3-html-table tbody tr:first-child th,
  .bp3-dark .bp3-running-text table tbody tr:first-child td,
  .bp3-running-text .bp3-dark table tbody tr:first-child td,
  .bp3-dark table.bp3-html-table tbody tr:first-child td,
  .bp3-dark .bp3-running-text table tfoot tr:first-child th,
  .bp3-running-text .bp3-dark table tfoot tr:first-child th,
  .bp3-dark table.bp3-html-table tfoot tr:first-child th,
  .bp3-dark .bp3-running-text table tfoot tr:first-child td,
  .bp3-running-text .bp3-dark table tfoot tr:first-child td,
  .bp3-dark table.bp3-html-table tfoot tr:first-child td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }

table.bp3-html-table.bp3-html-table-condensed th,
table.bp3-html-table.bp3-html-table-condensed td, table.bp3-html-table.bp3-small th,
table.bp3-html-table.bp3-small td{
  padding-bottom:6px;
  padding-top:6px; }

table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
  background:rgba(191, 204, 214, 0.15); }

table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
  -webkit-box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 1px 0 0 0 rgba(16, 22, 26, 0.15); }

table.bp3-html-table.bp3-html-table-bordered tbody tr td,
table.bp3-html-table.bp3-html-table-bordered tfoot tr td{
  -webkit-box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15);
          box-shadow:inset 0 1px 0 0 rgba(16, 22, 26, 0.15); }
  table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child),
  table.bp3-html-table.bp3-html-table-bordered tfoot tr td:not(:first-child){
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

.bp3-dark table.bp3-html-table{ }
  .bp3-dark table.bp3-html-table.bp3-html-table-striped tbody tr:nth-child(odd) td{
    background:rgba(92, 112, 128, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered th:not(:first-child){
    -webkit-box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 1px 0 0 0 rgba(255, 255, 255, 0.15); }
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td,
  .bp3-dark table.bp3-html-table.bp3-html-table-bordered tfoot tr td{
    -webkit-box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15);
            box-shadow:inset 0 1px 0 0 rgba(255, 255, 255, 0.15); }
    .bp3-dark table.bp3-html-table.bp3-html-table-bordered tbody tr td:not(:first-child),
    .bp3-dark table.bp3-html-table.bp3-html-table-bordered tfoot tr td:not(:first-child){
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
  padding-bottom:0;
  top:40px; }
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
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-pack:justify;
      -ms-flex-pack:justify;
          justify-content:space-between;
  margin-left:0;
  margin-right:0; }
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
  font-family:"Icons16", sans-serif;
  font-size:16px;
  font-style:normal;
  font-weight:400;
  line-height:1;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon-large{
  font-family:"Icons20", sans-serif;
  font-size:20px;
  font-style:normal;
  font-weight:400;
  line-height:1;
  -moz-osx-font-smoothing:grayscale;
  -webkit-font-smoothing:antialiased;
  display:inline-block; }

span.bp3-icon:empty{
  font-family:"Icons20";
  font-size:inherit;
  font-style:normal;
  font-weight:400;
  line-height:1; }
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

.bp3-icon-diagnosis::before{
  content:""; }

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

.bp3-icon-lab-test::before{
  content:""; }

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
  .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{ }

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
  background:#ffffff;
  border-radius:3px;
  color:#182026;
  list-style:none;
  margin:0;
  min-width:180px;
  padding:5px;
  text-align:left; }

.bp3-menu-divider{
  border-top:1px solid rgba(16, 22, 26, 0.15);
  display:block;
  margin:5px; }
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
  color:inherit;
  line-height:20px;
  padding:5px 7px;
  text-decoration:none;
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
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
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
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-style:normal;
    font-weight:400;
    line-height:1;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    margin-right:7px; }
  .bp3-menu-item::before,
  .bp3-menu-item > .bp3-icon{
    color:#5c7080;
    margin-top:2px; }
  .bp3-menu-item .bp3-menu-item-label{
    color:#5c7080; }
  .bp3-menu-item:hover, .bp3-submenu .bp3-popover-target.bp3-popover-open > .bp3-menu-item{
    color:inherit; }
  .bp3-menu-item.bp3-active, .bp3-menu-item:active{
    background-color:rgba(115, 134, 148, 0.3); }
  .bp3-menu-item.bp3-disabled{
    background-color:inherit !important;
    color:rgba(92, 112, 128, 0.6) !important;
    cursor:not-allowed !important;
    outline:none !important; }
    .bp3-menu-item.bp3-disabled::before,
    .bp3-menu-item.bp3-disabled > .bp3-icon,
    .bp3-menu-item.bp3-disabled .bp3-menu-item-label{
      color:rgba(92, 112, 128, 0.6) !important; }
  .bp3-large .bp3-menu-item{
    font-size:16px;
    line-height:22px;
    padding:9px 7px; }
    .bp3-large .bp3-menu-item .bp3-icon{
      margin-top:3px; }
    .bp3-large .bp3-menu-item::before{
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-style:normal;
      font-weight:400;
      line-height:1;
      -moz-osx-font-smoothing:grayscale;
      -webkit-font-smoothing:antialiased;
      margin-right:10px;
      margin-top:1px; }

button.bp3-menu-item{
  background:none;
  border:none;
  text-align:left;
  width:100%; }
.bp3-menu-header{
  border-top:1px solid rgba(16, 22, 26, 0.15);
  display:block;
  margin:5px;
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
    line-height:17px;
    margin:0;
    padding:10px 7px 0 1px; }
    .bp3-dark .bp3-menu-header > h6{
      color:#f5f8fa; }
  .bp3-menu-header:first-of-type > h6{
    padding-top:0; }
  .bp3-large .bp3-menu-header > h6{
    font-size:18px;
    padding-bottom:5px;
    padding-top:15px; }
  .bp3-large .bp3-menu-header:first-of-type > h6{
    padding-top:0; }

.bp3-dark .bp3-menu{
  background:#30404d;
  color:#f5f8fa; }

.bp3-dark .bp3-menu-item{ }
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
  background-color:#ffffff;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 0 0 rgba(16, 22, 26, 0), 0 1px 1px rgba(16, 22, 26, 0.2);
  height:50px;
  padding:0 15px;
  position:relative;
  width:100%;
  z-index:10; }
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
    left:0;
    position:fixed;
    right:0;
    top:0; }

.bp3-navbar-heading{
  font-size:16px;
  margin-right:15px; }

.bp3-navbar-group{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  height:50px; }
  .bp3-navbar-group.bp3-align-left{
    float:left; }
  .bp3-navbar-group.bp3-align-right{
    float:right; }

.bp3-navbar-divider{
  border-left:1px solid rgba(16, 22, 26, 0.15);
  height:20px;
  margin:0 10px; }
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
  height:100%;
  -webkit-box-pack:center;
      -ms-flex-pack:center;
          justify-content:center;
  text-align:center;
  width:100%; }
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
  bottom:0;
  left:0;
  position:static;
  right:0;
  top:0;
  z-index:20; }
  .bp3-overlay:not(.bp3-overlay-open){
    pointer-events:none; }
  .bp3-overlay.bp3-overlay-container{
    overflow:hidden;
    position:fixed; }
    .bp3-overlay.bp3-overlay-container.bp3-overlay-inline{
      position:absolute; }
  .bp3-overlay.bp3-overlay-scroll-container{
    overflow:auto;
    position:fixed; }
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
  bottom:0;
  left:0;
  position:fixed;
  right:0;
  top:0;
  opacity:1;
  background-color:rgba(16, 22, 26, 0.7);
  overflow:auto;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none;
  z-index:20; }
  .bp3-overlay-backdrop.bp3-overlay-enter, .bp3-overlay-backdrop.bp3-overlay-appear{
    opacity:0; }
  .bp3-overlay-backdrop.bp3-overlay-enter-active, .bp3-overlay-backdrop.bp3-overlay-appear-active{
    opacity:1;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-overlay-backdrop.bp3-overlay-exit{
    opacity:1; }
  .bp3-overlay-backdrop.bp3-overlay-exit-active{
    opacity:0;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-overlay-backdrop:focus{
    outline:none; }
  .bp3-overlay-inline .bp3-overlay-backdrop{
    position:absolute; }
.bp3-panel-stack{
  overflow:hidden;
  position:relative; }

.bp3-panel-stack-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  height:30px;
  z-index:1; }
  .bp3-dark .bp3-panel-stack-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack-header > span{
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1; }
  .bp3-panel-stack-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack-view{
  bottom:0;
  left:0;
  position:absolute;
  right:0;
  top:0;
  background-color:#ffffff;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  overflow-y:auto;
  z-index:1; }
  .bp3-dark .bp3-panel-stack-view{
    background-color:#30404d; }
  .bp3-panel-stack-view:nth-last-child(n + 4){
    display:none; }

.bp3-panel-stack-push .bp3-panel-stack-enter, .bp3-panel-stack-push .bp3-panel-stack-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack-push .bp3-panel-stack-enter-active, .bp3-panel-stack-push .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack-push .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-push .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack-pop .bp3-panel-stack-enter, .bp3-panel-stack-pop .bp3-panel-stack-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack-pop .bp3-panel-stack-enter-active, .bp3-panel-stack-pop .bp3-panel-stack-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack-pop .bp3-panel-stack-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack-pop .bp3-panel-stack-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }
.bp3-panel-stack2{
  overflow:hidden;
  position:relative; }

.bp3-panel-stack2-header{
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  -webkit-box-shadow:0 1px rgba(16, 22, 26, 0.15);
          box-shadow:0 1px rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -ms-flex-negative:0;
      flex-shrink:0;
  height:30px;
  z-index:1; }
  .bp3-dark .bp3-panel-stack2-header{
    -webkit-box-shadow:0 1px rgba(255, 255, 255, 0.15);
            box-shadow:0 1px rgba(255, 255, 255, 0.15); }
  .bp3-panel-stack2-header > span{
    -webkit-box-align:stretch;
        -ms-flex-align:stretch;
            align-items:stretch;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-flex:1;
        -ms-flex:1;
            flex:1; }
  .bp3-panel-stack2-header .bp3-heading{
    margin:0 5px; }

.bp3-button.bp3-panel-stack2-header-back{
  margin-left:5px;
  padding-left:0;
  white-space:nowrap; }
  .bp3-button.bp3-panel-stack2-header-back .bp3-icon{
    margin:0 2px; }

.bp3-panel-stack2-view{
  bottom:0;
  left:0;
  position:absolute;
  right:0;
  top:0;
  background-color:#ffffff;
  border-right:1px solid rgba(16, 22, 26, 0.15);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  margin-right:-1px;
  overflow-y:auto;
  z-index:1; }
  .bp3-dark .bp3-panel-stack2-view{
    background-color:#30404d; }
  .bp3-panel-stack2-view:nth-last-child(n + 4){
    display:none; }

.bp3-panel-stack2-push .bp3-panel-stack2-enter, .bp3-panel-stack2-push .bp3-panel-stack2-appear{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0; }

.bp3-panel-stack2-push .bp3-panel-stack2-enter-active, .bp3-panel-stack2-push .bp3-panel-stack2-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack2-push .bp3-panel-stack2-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack2-push .bp3-panel-stack2-exit-active{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack2-pop .bp3-panel-stack2-enter, .bp3-panel-stack2-pop .bp3-panel-stack2-appear{
  -webkit-transform:translateX(-50%);
          transform:translateX(-50%);
  opacity:0; }

.bp3-panel-stack2-pop .bp3-panel-stack2-enter-active, .bp3-panel-stack2-pop .bp3-panel-stack2-appear-active{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }

.bp3-panel-stack2-pop .bp3-panel-stack2-exit{
  -webkit-transform:translate(0%);
          transform:translate(0%);
  opacity:1; }

.bp3-panel-stack2-pop .bp3-panel-stack2-exit-active{
  -webkit-transform:translateX(100%);
          transform:translateX(100%);
  opacity:0;
  -webkit-transition-delay:0;
          transition-delay:0;
  -webkit-transition-duration:400ms;
          transition-duration:400ms;
  -webkit-transition-property:opacity, -webkit-transform;
  transition-property:opacity, -webkit-transform;
  transition-property:transform, opacity;
  transition-property:transform, opacity, -webkit-transform;
  -webkit-transition-timing-function:ease;
          transition-timing-function:ease; }
.bp3-popover{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1);
  border-radius:3px;
  display:inline-block;
  z-index:20; }
  .bp3-popover .bp3-popover-arrow{
    height:30px;
    position:absolute;
    width:30px; }
    .bp3-popover .bp3-popover-arrow::before{
      height:20px;
      margin:5px;
      width:20px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-popover{
    margin-bottom:17px;
    margin-top:-17px; }
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
    margin-left:-17px;
    margin-right:17px; }
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
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-popover-exit > .bp3-popover{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-popover{
    -webkit-transform:scale(0.3);
            transform:scale(0.3);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-popover .bp3-popover-content{
    border-radius:3px;
    position:relative; }
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
        -webkit-transition-delay:0;
                transition-delay:0;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
      .bp3-popover-exit > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1); }
      .bp3-popover-exit-active > .bp3-popover.bp3-minimal.bp3-popover{
        -webkit-transform:scale(1);
                transform:scale(1);
        -webkit-transition-delay:0;
                transition-delay:0;
        -webkit-transition-duration:100ms;
                transition-duration:100ms;
        -webkit-transition-property:-webkit-transform;
        transition-property:-webkit-transform;
        transition-property:transform;
        transition-property:transform, -webkit-transform;
        -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
                transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
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
  border-radius:2px;
  content:"";
  display:block;
  position:absolute;
  -webkit-transform:rotate(45deg);
          transform:rotate(45deg); }

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
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-transition-container.bp3-popover-exit{
    opacity:1; }
  .bp3-transition-container.bp3-popover-exit-active{
    opacity:0;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:opacity;
    transition-property:opacity;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
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
  left:0;
  position:absolute;
  right:0;
  top:0; }
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
  background:rgba(92, 112, 128, 0.2);
  border-radius:40px;
  display:block;
  height:8px;
  overflow:hidden;
  position:relative;
  width:100%; }
  .bp3-progress-bar .bp3-progress-meter{
    background:linear-gradient(-45deg, rgba(255, 255, 255, 0.2) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.2) 50%, rgba(255, 255, 255, 0.2) 75%, transparent 75%);
    background-color:rgba(92, 112, 128, 0.8);
    background-size:30px 30px;
    border-radius:40px;
    height:100%;
    position:absolute;
    -webkit-transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:width 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    width:100%; }
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
    background:rgba(206, 217, 224, 0.2);
    border-color:rgba(206, 217, 224, 0.2); }
  to{
    background:rgba(92, 112, 128, 0.2);
    border-color:rgba(92, 112, 128, 0.2); } }
@keyframes skeleton-glow{
  from{
    background:rgba(206, 217, 224, 0.2);
    border-color:rgba(206, 217, 224, 0.2); }
  to{
    background:rgba(92, 112, 128, 0.2);
    border-color:rgba(92, 112, 128, 0.2); } }
.bp3-skeleton{
  -webkit-animation:1000ms linear infinite alternate skeleton-glow;
          animation:1000ms linear infinite alternate skeleton-glow;
  background:rgba(206, 217, 224, 0.2);
  background-clip:padding-box !important;
  border-color:rgba(206, 217, 224, 0.2) !important;
  border-radius:2px;
  -webkit-box-shadow:none !important;
          box-shadow:none !important;
  color:transparent !important;
  cursor:default;
  pointer-events:none;
  -webkit-user-select:none;
     -moz-user-select:none;
      -ms-user-select:none;
          user-select:none; }
  .bp3-skeleton::before, .bp3-skeleton::after,
  .bp3-skeleton *{
    visibility:hidden !important; }
.bp3-slider{
  height:40px;
  min-width:150px;
  width:100%;
  cursor:default;
  outline:none;
  position:relative;
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
    cursor:not-allowed;
    opacity:0.5; }
  .bp3-slider.bp3-slider-unlabeled{
    height:16px; }

.bp3-slider-track,
.bp3-slider-progress{
  height:6px;
  left:0;
  right:0;
  top:5px;
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
  background-color:#f5f8fa;
  background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.8)), to(rgba(255, 255, 255, 0)));
  background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.8), rgba(255, 255, 255, 0));
  -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
          box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
  color:#182026;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
  cursor:pointer;
  height:16px;
  left:0;
  position:absolute;
  top:0;
  width:16px; }
  .bp3-slider-handle:hover{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1); }
  .bp3-slider-handle:active, .bp3-slider-handle.bp3-active{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
  .bp3-slider-handle:disabled, .bp3-slider-handle.bp3-disabled{
    background-color:rgba(206, 217, 224, 0.5);
    background-image:none;
    -webkit-box-shadow:none;
            box-shadow:none;
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed;
    outline:none; }
    .bp3-slider-handle:disabled.bp3-active, .bp3-slider-handle:disabled.bp3-active:hover, .bp3-slider-handle.bp3-disabled.bp3-active, .bp3-slider-handle.bp3-disabled.bp3-active:hover{
      background:rgba(206, 217, 224, 0.7); }
  .bp3-slider-handle:focus{
    z-index:1; }
  .bp3-slider-handle:hover{
    background-clip:padding-box;
    background-color:#ebf1f5;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 -1px 0 rgba(16, 22, 26, 0.1);
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 1px 1px rgba(16, 22, 26, 0.2);
    cursor:-webkit-grab;
    cursor:grab;
    z-index:2; }
  .bp3-slider-handle.bp3-active{
    background-color:#d8e1e8;
    background-image:none;
    -webkit-box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
            box-shadow:inset 0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 2px rgba(16, 22, 26, 0.2);
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), inset 0 1px 1px rgba(16, 22, 26, 0.1);
    cursor:-webkit-grabbing;
    cursor:grabbing; }
  .bp3-disabled .bp3-slider-handle{
    background:#bfccd6;
    -webkit-box-shadow:none;
            box-shadow:none;
    pointer-events:none; }
  .bp3-dark .bp3-slider-handle{
    background-color:#394b59;
    background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255, 255, 255, 0.05)), to(rgba(255, 255, 255, 0)));
    background-image:linear-gradient(to bottom, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0));
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
    color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover, .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      color:#f5f8fa; }
    .bp3-dark .bp3-slider-handle:hover{
      background-color:#30404d;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.4); }
    .bp3-dark .bp3-slider-handle:active, .bp3-dark .bp3-slider-handle.bp3-active{
      background-color:#202b33;
      background-image:none;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.6), inset 0 1px 2px rgba(16, 22, 26, 0.2); }
    .bp3-dark .bp3-slider-handle:disabled, .bp3-dark .bp3-slider-handle.bp3-disabled{
      background-color:rgba(57, 75, 89, 0.5);
      background-image:none;
      -webkit-box-shadow:none;
              box-shadow:none;
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
    background:#5c7080;
    border-color:#5c7080;
    -webkit-box-shadow:none;
            box-shadow:none; }
  .bp3-slider-handle .bp3-slider-label{
    background:#394b59;
    border-radius:3px;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
    color:#f5f8fa;
    margin-left:8px; }
    .bp3-dark .bp3-slider-handle .bp3-slider-label{
      background:#e1e8ed;
      -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
              box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
      color:#394b59; }
    .bp3-disabled .bp3-slider-handle .bp3-slider-label{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-slider-handle.bp3-start, .bp3-slider-handle.bp3-end{
    width:8px; }
  .bp3-slider-handle.bp3-start{
    border-bottom-right-radius:0;
    border-top-right-radius:0; }
  .bp3-slider-handle.bp3-end{
    border-bottom-left-radius:0;
    border-top-left-radius:0;
    margin-left:8px; }
    .bp3-slider-handle.bp3-end .bp3-slider-label{
      margin-left:0; }

.bp3-slider-label{
  -webkit-transform:translate(-50%, 20px);
          transform:translate(-50%, 20px);
  display:inline-block;
  font-size:12px;
  line-height:1;
  padding:2px 5px;
  position:absolute;
  vertical-align:top; }

.bp3-slider.bp3-vertical{
  height:150px;
  min-width:40px;
  width:40px; }
  .bp3-slider.bp3-vertical .bp3-slider-track,
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    bottom:0;
    height:auto;
    left:5px;
    top:0;
    width:6px; }
  .bp3-slider.bp3-vertical .bp3-slider-progress{
    top:auto; }
  .bp3-slider.bp3-vertical .bp3-slider-label{
    -webkit-transform:translate(20px, 50%);
            transform:translate(20px, 50%); }
  .bp3-slider.bp3-vertical .bp3-slider-handle{
    top:auto; }
    .bp3-slider.bp3-vertical .bp3-slider-handle .bp3-slider-label{
      margin-left:0;
      margin-top:-8px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end, .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      height:8px;
      margin-left:0;
      width:16px; }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start{
      border-bottom-right-radius:3px;
      border-top-left-radius:0; }
      .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-start .bp3-slider-label{
        -webkit-transform:translate(20px);
                transform:translate(20px); }
    .bp3-slider.bp3-vertical .bp3-slider-handle.bp3-end{
      border-bottom-left-radius:0;
      border-bottom-right-radius:0;
      border-top-left-radius:3px;
      margin-bottom:8px; }

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
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
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
    stroke:rgba(92, 112, 128, 0.8);
    stroke-linecap:round;
    -webkit-transform-origin:center;
            transform-origin:center;
    -webkit-transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9);
    transition:stroke-dashoffset 200ms cubic-bezier(0.4, 1, 0.75, 0.9); }
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
    -webkit-box-align:start;
        -ms-flex-align:start;
            align-items:flex-start;
    -webkit-box-orient:vertical;
    -webkit-box-direction:normal;
        -ms-flex-direction:column;
            flex-direction:column; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab{
      border-radius:3px;
      padding:0 10px;
      width:100%; }
      .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab[aria-selected="true"]{
        background-color:rgba(19, 124, 189, 0.2);
        -webkit-box-shadow:none;
                box-shadow:none; }
    .bp3-tabs.bp3-vertical > .bp3-tab-list .bp3-tab-indicator-wrapper .bp3-tab-indicator{
      background-color:rgba(19, 124, 189, 0.2);
      border-radius:3px;
      bottom:0;
      height:auto;
      left:0;
      right:0;
      top:0; }
  .bp3-tabs.bp3-vertical > .bp3-tab-panel{
    margin-top:0;
    padding-left:20px; }

.bp3-tab-list{
  -webkit-box-align:end;
      -ms-flex-align:end;
          align-items:flex-end;
  border:none;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  list-style:none;
  margin:0;
  padding:0;
  position:relative; }
  .bp3-tab-list > *:not(:last-child){
    margin-right:20px; }

.bp3-tab{
  overflow:hidden;
  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  color:#182026;
  cursor:pointer;
  -webkit-box-flex:0;
      -ms-flex:0 0 auto;
          flex:0 0 auto;
  font-size:14px;
  line-height:30px;
  max-width:100%;
  position:relative;
  vertical-align:top; }
  .bp3-tab a{
    color:inherit;
    display:block;
    text-decoration:none; }
  .bp3-tab-indicator-wrapper ~ .bp3-tab{
    background-color:transparent !important;
    -webkit-box-shadow:none !important;
            box-shadow:none !important; }
  .bp3-tab[aria-disabled="true"]{
    color:rgba(92, 112, 128, 0.6);
    cursor:not-allowed; }
  .bp3-tab[aria-selected="true"]{
    border-radius:0;
    -webkit-box-shadow:inset 0 -3px 0 #106ba3;
            box-shadow:inset 0 -3px 0 #106ba3; }
  .bp3-tab[aria-selected="true"], .bp3-tab:not([aria-disabled="true"]):hover{
    color:#106ba3; }
  .bp3-tab:focus{
    -moz-outline-radius:0; }
  .bp3-large > .bp3-tab{
    font-size:16px;
    line-height:40px; }

.bp3-tab-panel{
  margin-top:20px; }
  .bp3-tab-panel[aria-hidden="true"]{
    display:none; }

.bp3-tab-indicator-wrapper{
  left:0;
  pointer-events:none;
  position:absolute;
  top:0;
  -webkit-transform:translateX(0), translateY(0);
          transform:translateX(0), translateY(0);
  -webkit-transition:height, width, -webkit-transform;
  transition:height, width, -webkit-transform;
  transition:height, transform, width;
  transition:height, transform, width, -webkit-transform;
  -webkit-transition-duration:200ms;
          transition-duration:200ms;
  -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
          transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-tab-indicator-wrapper .bp3-tab-indicator{
    background-color:#106ba3;
    bottom:0;
    height:3px;
    left:0;
    position:absolute;
    right:0; }
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
  background-color:#5c7080;
  border:none;
  border-radius:3px;
  -webkit-box-shadow:none;
          box-shadow:none;
  color:#f5f8fa;
  font-size:12px;
  line-height:16px;
  max-width:100%;
  min-height:20px;
  min-width:20px;
  padding:2px 6px;
  position:relative; }
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
    padding-left:8px;
    padding-right:8px; }
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
    font-size:14px;
    line-height:20px;
    min-height:30px;
    min-width:30px;
    padding:5px 10px; }
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
      padding-left:12px;
      padding-right:12px; }
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
  background:none;
  border:none;
  color:inherit;
  cursor:pointer;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  margin-bottom:-2px;
  margin-right:-6px !important;
  margin-top:-2px;
  opacity:0.5;
  padding:2px;
  padding-left:0; }
  .bp3-tag-remove:hover{
    background:none;
    opacity:0.8;
    text-decoration:none; }
  .bp3-tag-remove:active{
    opacity:1; }
  .bp3-tag-remove:empty::before{
    font-family:"Icons16", sans-serif;
    font-size:16px;
    font-style:normal;
    font-weight:400;
    line-height:1;
    -moz-osx-font-smoothing:grayscale;
    -webkit-font-smoothing:antialiased;
    content:""; }
  .bp3-large .bp3-tag-remove{
    margin-right:-10px !important;
    padding:0 5px 0 0; }
    .bp3-large .bp3-tag-remove:empty::before{
      font-family:"Icons20", sans-serif;
      font-size:20px;
      font-style:normal;
      font-weight:400;
      line-height:1; }
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
  line-height:inherit;
  min-height:30px;
  padding-left:5px;
  padding-right:0; }
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
    color:#5c7080;
    margin-left:2px;
    margin-right:7px;
    margin-top:7px; }
  .bp3-tag-input .bp3-tag-input-values{
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex;
    -webkit-box-orient:horizontal;
    -webkit-box-direction:normal;
        -ms-flex-direction:row;
            flex-direction:row;
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    -ms-flex-item-align:stretch;
        align-self:stretch;
    -ms-flex-wrap:wrap;
        flex-wrap:wrap;
    margin-right:7px;
    margin-top:5px;
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
    line-height:20px;
    width:80px; }
    .bp3-tag-input .bp3-input-ghost:disabled, .bp3-tag-input .bp3-input-ghost.bp3-disabled{
      cursor:not-allowed; }
  .bp3-tag-input .bp3-button,
  .bp3-tag-input .bp3-spinner{
    margin:3px;
    margin-left:0; }
  .bp3-tag-input .bp3-button{
    min-height:24px;
    min-width:24px;
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
      margin-left:5px;
      margin-top:10px; }
    .bp3-tag-input.bp3-large .bp3-input-ghost{
      line-height:30px; }
    .bp3-tag-input.bp3-large .bp3-button{
      min-height:30px;
      min-width:30px;
      padding:5px 10px;
      margin:5px;
      margin-left:0; }
    .bp3-tag-input.bp3-large .bp3-spinner{
      margin:8px;
      margin-left:0; }
  .bp3-tag-input.bp3-active{
    background-color:#ffffff;
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.2); }
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
    background-color:rgba(16, 22, 26, 0.3);
    -webkit-box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px #137cbd, 0 0 0 1px #137cbd, 0 0 0 3px rgba(19, 124, 189, 0.3), inset 0 0 0 1px rgba(16, 22, 26, 0.3), inset 0 1px 1px rgba(16, 22, 26, 0.4); }
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
  background:none;
  border:none;
  -webkit-box-shadow:none;
          box-shadow:none;
  padding:0; }
  .bp3-input-ghost::-webkit-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost::-moz-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost:-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost::-ms-input-placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost::placeholder{
    color:rgba(92, 112, 128, 0.6);
    opacity:1; }
  .bp3-input-ghost:focus{
    outline:none !important; }
.bp3-toast{
  -webkit-box-align:start;
      -ms-flex-align:start;
          align-items:flex-start;
  background-color:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  margin:20px 0 0;
  max-width:500px;
  min-width:300px;
  pointer-events:all;
  position:relative !important; }
  .bp3-toast.bp3-toast-enter, .bp3-toast.bp3-toast-appear{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active, .bp3-toast.bp3-toast-appear-active{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-toast.bp3-toast-enter ~ .bp3-toast, .bp3-toast.bp3-toast-appear ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px); }
  .bp3-toast.bp3-toast-enter-active ~ .bp3-toast, .bp3-toast.bp3-toast-appear-active ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11);
            transition-timing-function:cubic-bezier(0.54, 1.12, 0.38, 1.11); }
  .bp3-toast.bp3-toast-exit{
    opacity:1;
    -webkit-filter:blur(0);
            filter:blur(0); }
  .bp3-toast.bp3-toast-exit-active{
    opacity:0;
    -webkit-filter:blur(10px);
            filter:blur(10px);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:300ms;
            transition-duration:300ms;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:opacity, filter;
    transition-property:opacity, filter, -webkit-filter;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-toast.bp3-toast-exit ~ .bp3-toast{
    -webkit-transform:translateY(0);
            transform:translateY(0); }
  .bp3-toast.bp3-toast-exit-active ~ .bp3-toast{
    -webkit-transform:translateY(-40px);
            transform:translateY(-40px);
    -webkit-transition-delay:50ms;
            transition-delay:50ms;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-toast .bp3-button-group{
    -webkit-box-flex:0;
        -ms-flex:0 0 auto;
            flex:0 0 auto;
    padding:5px;
    padding-left:0; }
  .bp3-toast > .bp3-icon{
    color:#5c7080;
    margin:12px;
    margin-right:0; }
  .bp3-toast.bp3-dark,
  .bp3-dark .bp3-toast{
    background-color:#394b59;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 2px 4px rgba(16, 22, 26, 0.4), 0 8px 24px rgba(16, 22, 26, 0.4); }
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
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box !important;
  display:-ms-flexbox !important;
  display:flex !important;
  -webkit-box-orient:vertical;
  -webkit-box-direction:normal;
      -ms-flex-direction:column;
          flex-direction:column;
  left:0;
  overflow:hidden;
  padding:0 20px 20px;
  pointer-events:none;
  right:0;
  z-index:40; }
  .bp3-toast-container.bp3-toast-container-in-portal{
    position:fixed; }
  .bp3-toast-container.bp3-toast-container-inline{
    position:absolute; }
  .bp3-toast-container.bp3-toast-container-top{
    top:0; }
  .bp3-toast-container.bp3-toast-container-bottom{
    bottom:0;
    -webkit-box-orient:vertical;
    -webkit-box-direction:reverse;
        -ms-flex-direction:column-reverse;
            flex-direction:column-reverse;
    top:auto; }
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
.bp3-toast-container-bottom .bp3-toast.bp3-toast-exit-active ~ .bp3-toast,
.bp3-toast-container-bottom .bp3-toast.bp3-toast-leave-active ~ .bp3-toast{
  -webkit-transform:translateY(60px);
          transform:translateY(60px); }
.bp3-tooltip{
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 2px 4px rgba(16, 22, 26, 0.2), 0 8px 24px rgba(16, 22, 26, 0.2);
  -webkit-transform:scale(1);
          transform:scale(1); }
  .bp3-tooltip .bp3-popover-arrow{
    height:22px;
    position:absolute;
    width:22px; }
    .bp3-tooltip .bp3-popover-arrow::before{
      height:14px;
      margin:4px;
      width:14px; }
  .bp3-tether-element-attached-bottom.bp3-tether-target-attached-top > .bp3-tooltip{
    margin-bottom:11px;
    margin-top:-11px; }
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
    margin-left:-11px;
    margin-right:11px; }
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
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-popover-exit > .bp3-tooltip{
    -webkit-transform:scale(1);
            transform:scale(1); }
  .bp3-popover-exit-active > .bp3-tooltip{
    -webkit-transform:scale(0.8);
            transform:scale(0.8);
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:100ms;
            transition-duration:100ms;
    -webkit-transition-property:-webkit-transform;
    transition-property:-webkit-transform;
    transition-property:transform;
    transition-property:transform, -webkit-transform;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
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
  list-style:none;
  margin:0;
  padding-left:0; }

.bp3-tree-root{
  background-color:transparent;
  cursor:default;
  padding-left:0;
  position:relative; }

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
  -webkit-box-align:center;
      -ms-flex-align:center;
          align-items:center;
  display:-webkit-box;
  display:-ms-flexbox;
  display:flex;
  height:30px;
  padding-right:5px;
  width:100%; }
  .bp3-tree-node-content:hover{
    background-color:rgba(191, 204, 214, 0.4); }

.bp3-tree-node-caret,
.bp3-tree-node-caret-none{
  min-width:30px; }

.bp3-tree-node-caret{
  color:#5c7080;
  cursor:pointer;
  padding:7px;
  -webkit-transform:rotate(0deg);
          transform:rotate(0deg);
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
  margin-right:7px;
  position:relative; }

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
    -webkit-box-align:center;
        -ms-flex-align:center;
            align-items:center;
    display:-webkit-box;
    display:-ms-flexbox;
    display:flex; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-content{
  background-color:inherit;
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

.bp3-tree-node.bp3-disabled .bp3-tree-node-caret,
.bp3-tree-node.bp3-disabled .bp3-tree-node-icon{
  color:rgba(92, 112, 128, 0.6);
  cursor:not-allowed; }

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
.bp3-omnibar{
  -webkit-filter:blur(0);
          filter:blur(0);
  opacity:1;
  background-color:#ffffff;
  border-radius:3px;
  -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
          box-shadow:0 0 0 1px rgba(16, 22, 26, 0.1), 0 4px 8px rgba(16, 22, 26, 0.2), 0 18px 46px 6px rgba(16, 22, 26, 0.2);
  left:calc(50% - 250px);
  top:20vh;
  width:500px;
  z-index:21; }
  .bp3-omnibar.bp3-overlay-enter, .bp3-omnibar.bp3-overlay-appear{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2; }
  .bp3-omnibar.bp3-overlay-enter-active, .bp3-omnibar.bp3-overlay-appear-active{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-omnibar.bp3-overlay-exit{
    -webkit-filter:blur(0);
            filter:blur(0);
    opacity:1; }
  .bp3-omnibar.bp3-overlay-exit-active{
    -webkit-filter:blur(20px);
            filter:blur(20px);
    opacity:0.2;
    -webkit-transition-delay:0;
            transition-delay:0;
    -webkit-transition-duration:200ms;
            transition-duration:200ms;
    -webkit-transition-property:opacity, -webkit-filter;
    transition-property:opacity, -webkit-filter;
    transition-property:filter, opacity;
    transition-property:filter, opacity, -webkit-filter;
    -webkit-transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9);
            transition-timing-function:cubic-bezier(0.4, 1, 0.75, 0.9); }
  .bp3-omnibar .bp3-input{
    background-color:transparent;
    border-radius:0; }
    .bp3-omnibar .bp3-input, .bp3-omnibar .bp3-input:focus{
      -webkit-box-shadow:none;
              box-shadow:none; }
  .bp3-omnibar .bp3-menu{
    background-color:transparent;
    border-radius:0;
    -webkit-box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
            box-shadow:inset 0 1px 0 rgba(16, 22, 26, 0.15);
    max-height:calc(60vh - 40px);
    overflow:auto; }
    .bp3-omnibar .bp3-menu:empty{
      display:none; }
  .bp3-dark .bp3-omnibar, .bp3-omnibar.bp3-dark{
    background-color:#30404d;
    -webkit-box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4);
            box-shadow:0 0 0 1px rgba(16, 22, 26, 0.2), 0 4px 8px rgba(16, 22, 26, 0.4), 0 18px 46px 6px rgba(16, 22, 26, 0.4); }

.bp3-omnibar-overlay .bp3-overlay-backdrop{
  background-color:rgba(16, 22, 26, 0.2); }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-height:300px;
  max-width:400px;
  overflow:auto;
  padding:0; }
  .bp3-select-popover .bp3-menu:not(:first-child){
    padding-top:5px; }

.bp3-multi-select{
  min-width:150px; }

.bp3-multi-select-popover .bp3-menu{
  max-height:300px;
  max-width:400px;
  overflow:auto; }

.bp3-select-popover .bp3-popover-content{
  padding:5px; }

.bp3-select-popover .bp3-input-group{
  margin-bottom:0; }

.bp3-select-popover .bp3-menu{
  max-height:300px;
  max-width:400px;
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
  --jp-icon-bug: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0yMCA4aC0yLjgxYy0uNDUtLjc4LTEuMDctMS40NS0xLjgyLTEuOTZMMTcgNC40MSAxNS41OSAzbC0yLjE3IDIuMTdDMTIuOTYgNS4wNiAxMi40OSA1IDEyIDVjLS40OSAwLS45Ni4wNi0xLjQxLjE3TDguNDEgMyA3IDQuNDFsMS42MiAxLjYzQzcuODggNi41NSA3LjI2IDcuMjIgNi44MSA4SDR2MmgyLjA5Yy0uMDUuMzMtLjA5LjY2LS4wOSAxdjFINHYyaDJ2MWMwIC4zNC4wNC42Ny4wOSAxSDR2MmgyLjgxYzEuMDQgMS43OSAyLjk3IDMgNS4xOSAzczQuMTUtMS4yMSA1LjE5LTNIMjB2LTJoLTIuMDljLjA1LS4zMy4wOS0uNjYuMDktMXYtMWgydi0yaC0ydi0xYzAtLjM0LS4wNC0uNjctLjA5LTFIMjBWOHptLTYgOGgtNHYtMmg0djJ6bTAtNGgtNHYtMmg0djJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-build: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIHZpZXdCb3g9IjAgMCAyNCAyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE0LjkgMTcuNDVDMTYuMjUgMTcuNDUgMTcuMzUgMTYuMzUgMTcuMzUgMTVDMTcuMzUgMTMuNjUgMTYuMjUgMTIuNTUgMTQuOSAxMi41NUMxMy41NCAxMi41NSAxMi40NSAxMy42NSAxMi40NSAxNUMxMi40NSAxNi4zNSAxMy41NCAxNy40NSAxNC45IDE3LjQ1Wk0yMC4xIDE1LjY4TDIxLjU4IDE2Ljg0QzIxLjcxIDE2Ljk1IDIxLjc1IDE3LjEzIDIxLjY2IDE3LjI5TDIwLjI2IDE5LjcxQzIwLjE3IDE5Ljg2IDIwIDE5LjkyIDE5LjgzIDE5Ljg2TDE4LjA5IDE5LjE2QzE3LjczIDE5LjQ0IDE3LjMzIDE5LjY3IDE2LjkxIDE5Ljg1TDE2LjY0IDIxLjdDMTYuNjIgMjEuODcgMTYuNDcgMjIgMTYuMyAyMkgxMy41QzEzLjMyIDIyIDEzLjE4IDIxLjg3IDEzLjE1IDIxLjdMMTIuODkgMTkuODVDMTIuNDYgMTkuNjcgMTIuMDcgMTkuNDQgMTEuNzEgMTkuMTZMOS45NjAwMiAxOS44NkM5LjgxMDAyIDE5LjkyIDkuNjIwMDIgMTkuODYgOS41NDAwMiAxOS43MUw4LjE0MDAyIDE3LjI5QzguMDUwMDIgMTcuMTMgOC4wOTAwMiAxNi45NSA4LjIyMDAyIDE2Ljg0TDkuNzAwMDIgMTUuNjhMOS42NTAwMSAxNUw5LjcwMDAyIDE0LjMxTDguMjIwMDIgMTMuMTZDOC4wOTAwMiAxMy4wNSA4LjA1MDAyIDEyLjg2IDguMTQwMDIgMTIuNzFMOS41NDAwMiAxMC4yOUM5LjYyMDAyIDEwLjEzIDkuODEwMDIgMTAuMDcgOS45NjAwMiAxMC4xM0wxMS43MSAxMC44NEMxMi4wNyAxMC41NiAxMi40NiAxMC4zMiAxMi44OSAxMC4xNUwxMy4xNSA4LjI4OTk4QzEzLjE4IDguMTI5OTggMTMuMzIgNy45OTk5OCAxMy41IDcuOTk5OThIMTYuM0MxNi40NyA3Ljk5OTk4IDE2LjYyIDguMTI5OTggMTYuNjQgOC4yODk5OEwxNi45MSAxMC4xNUMxNy4zMyAxMC4zMiAxNy43MyAxMC41NiAxOC4wOSAxMC44NEwxOS44MyAxMC4xM0MyMCAxMC4wNyAyMC4xNyAxMC4xMyAyMC4yNiAxMC4yOUwyMS42NiAxMi43MUMyMS43NSAxMi44NiAyMS43MSAxMy4wNSAyMS41OCAxMy4xNkwyMC4xIDE0LjMxTDIwLjE1IDE1TDIwLjEgMTUuNjhaIi8+CiAgICA8cGF0aCBkPSJNNy4zMjk2NiA3LjQ0NDU0QzguMDgzMSA3LjAwOTU0IDguMzM5MzIgNi4wNTMzMiA3LjkwNDMyIDUuMjk5ODhDNy40NjkzMiA0LjU0NjQzIDYuNTA4MSA0LjI4MTU2IDUuNzU0NjYgNC43MTY1NkM1LjM5MTc2IDQuOTI2MDggNS4xMjY5NSA1LjI3MTE4IDUuMDE4NDkgNS42NzU5NEM0LjkxMDA0IDYuMDgwNzEgNC45NjY4MiA2LjUxMTk4IDUuMTc2MzQgNi44NzQ4OEM1LjYxMTM0IDcuNjI4MzIgNi41NzYyMiA3Ljg3OTU0IDcuMzI5NjYgNy40NDQ1NFpNOS42NTcxOCA0Ljc5NTkzTDEwLjg2NzIgNC45NTE3OUMxMC45NjI4IDQuOTc3NDEgMTEuMDQwMiA1LjA3MTMzIDExLjAzODIgNS4xODc5M0wxMS4wMzg4IDYuOTg4OTNDMTEuMDQ1NSA3LjEwMDU0IDEwLjk2MTYgNy4xOTUxOCAxMC44NTUgNy4yMTA1NEw5LjY2MDAxIDcuMzgwODNMOS4yMzkxNSA4LjEzMTg4TDkuNjY5NjEgOS4yNTc0NUM5LjcwNzI5IDkuMzYyNzEgOS42NjkzNCA5LjQ3Njk5IDkuNTc0MDggOS41MzE5OUw4LjAxNTIzIDEwLjQzMkM3LjkxMTMxIDEwLjQ5MiA3Ljc5MzM3IDEwLjQ2NzcgNy43MjEwNSAxMC4zODI0TDYuOTg3NDggOS40MzE4OEw2LjEwOTMxIDkuNDMwODNMNS4zNDcwNCAxMC4zOTA1QzUuMjg5MDkgMTAuNDcwMiA1LjE3MzgzIDEwLjQ5MDUgNS4wNzE4NyAxMC40MzM5TDMuNTEyNDUgOS41MzI5M0MzLjQxMDQ5IDkuNDc2MzMgMy4zNzY0NyA5LjM1NzQxIDMuNDEwNzUgOS4yNTY3OUwzLjg2MzQ3IDguMTQwOTNMMy42MTc0OSA3Ljc3NDg4TDMuNDIzNDcgNy4zNzg4M0wyLjIzMDc1IDcuMjEyOTdDMi4xMjY0NyA3LjE5MjM1IDIuMDQwNDkgNy4xMDM0MiAyLjA0MjQ1IDYuOTg2ODJMMi4wNDE4NyA1LjE4NTgyQzIuMDQzODMgNS4wNjkyMiAyLjExOTA5IDQuOTc5NTggMi4yMTcwNCA0Ljk2OTIyTDMuNDIwNjUgNC43OTM5M0wzLjg2NzQ5IDQuMDI3ODhMMy40MTEwNSAyLjkxNzMxQzMuMzczMzcgMi44MTIwNCAzLjQxMTMxIDIuNjk3NzYgMy41MTUyMyAyLjYzNzc2TDUuMDc0MDggMS43Mzc3NkM1LjE2OTM0IDEuNjgyNzYgNS4yODcyOSAxLjcwNzA0IDUuMzU5NjEgMS43OTIzMUw2LjExOTE1IDIuNzI3ODhMNi45ODAwMSAyLjczODkzTDcuNzI0OTYgMS43ODkyMkM3Ljc5MTU2IDEuNzA0NTggNy45MTU0OCAxLjY3OTIyIDguMDA4NzkgMS43NDA4Mkw5LjU2ODIxIDIuNjQxODJDOS42NzAxNyAyLjY5ODQyIDkuNzEyODUgMi44MTIzNCA5LjY4NzIzIDIuOTA3OTdMOS4yMTcxOCA0LjAzMzgzTDkuNDYzMTYgNC4zOTk4OEw5LjY1NzE4IDQuNzk1OTNaIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iOS45LDEzLjYgMy42LDcuNCA0LjQsNi42IDkuOSwxMi4yIDE1LjQsNi43IDE2LjEsNy40ICIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNS45TDksOS43bDMuOC0zLjhsMS4yLDEuMmwtNC45LDVsLTQuOS01TDUuMiw1Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-caret-down: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik01LjIsNy41TDksMTEuMmwzLjgtMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-left: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik0xMC44LDEyLjhMNy4xLDlsMy44LTMuOGwwLDcuNkgxMC44eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-right: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiIHNoYXBlLXJlbmRlcmluZz0iZ2VvbWV0cmljUHJlY2lzaW9uIj4KICAgIDxwYXRoIGQ9Ik03LjIsNS4yTDEwLjksOWwtMy44LDMuOFY1LjJINy4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-caret-up-empty-thin: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwb2x5Z29uIGNsYXNzPSJzdDEiIHBvaW50cz0iMTUuNCwxMy4zIDkuOSw3LjcgNC40LDEzLjIgMy42LDEyLjUgOS45LDYuMyAxNi4xLDEyLjYgIi8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-caret-up: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDE4IDE4Ij4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSIgc2hhcGUtcmVuZGVyaW5nPSJnZW9tZXRyaWNQcmVjaXNpb24iPgoJCTxwYXRoIGQ9Ik01LjIsMTAuNUw5LDYuOGwzLjgsMy44SDUuMnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-case-sensitive: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwIDIwIj4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0MTQxNDEiPgogICAgPHJlY3QgeD0iMiIgeT0iMiIgd2lkdGg9IjE2IiBoZWlnaHQ9IjE2Ii8+CiAgPC9nPgogIDxnIGNsYXNzPSJqcC1pY29uLWFjY2VudDIiIGZpbGw9IiNGRkYiPgogICAgPHBhdGggZD0iTTcuNiw4aDAuOWwzLjUsOGgtMS4xTDEwLDE0SDZsLTAuOSwySDRMNy42LDh6IE04LDkuMUw2LjQsMTNoMy4yTDgsOS4xeiIvPgogICAgPHBhdGggZD0iTTE2LjYsOS44Yy0wLjIsMC4xLTAuNCwwLjEtMC43LDAuMWMtMC4yLDAtMC40LTAuMS0wLjYtMC4yYy0wLjEtMC4xLTAuMi0wLjQtMC4yLTAuNyBjLTAuMywwLjMtMC42LDAuNS0wLjksMC43Yy0wLjMsMC4xLTAuNywwLjItMS4xLDAuMmMtMC4zLDAtMC41LDAtMC43LTAuMWMtMC4yLTAuMS0wLjQtMC4yLTAuNi0wLjNjLTAuMi0wLjEtMC4zLTAuMy0wLjQtMC41IGMtMC4xLTAuMi0wLjEtMC40LTAuMS0wLjdjMC0wLjMsMC4xLTAuNiwwLjItMC44YzAuMS0wLjIsMC4zLTAuNCwwLjQtMC41QzEyLDcsMTIuMiw2LjksMTIuNSw2LjhjMC4yLTAuMSwwLjUtMC4xLDAuNy0wLjIgYzAuMy0wLjEsMC41LTAuMSwwLjctMC4xYzAuMiwwLDAuNC0wLjEsMC42LTAuMWMwLjIsMCwwLjMtMC4xLDAuNC0wLjJjMC4xLTAuMSwwLjItMC4yLDAuMi0wLjRjMC0xLTEuMS0xLTEuMy0xIGMtMC40LDAtMS40LDAtMS40LDEuMmgtMC45YzAtMC40LDAuMS0wLjcsMC4yLTFjMC4xLTAuMiwwLjMtMC40LDAuNS0wLjZjMC4yLTAuMiwwLjUtMC4zLDAuOC0wLjNDMTMuMyw0LDEzLjYsNCwxMy45LDQgYzAuMywwLDAuNSwwLDAuOCwwLjFjMC4zLDAsMC41LDAuMSwwLjcsMC4yYzAuMiwwLjEsMC40LDAuMywwLjUsMC41QzE2LDUsMTYsNS4yLDE2LDUuNnYyLjljMCwwLjIsMCwwLjQsMCwwLjUgYzAsMC4xLDAuMSwwLjIsMC4zLDAuMmMwLjEsMCwwLjIsMCwwLjMsMFY5Ljh6IE0xNS4yLDYuOWMtMS4yLDAuNi0zLjEsMC4yLTMuMSwxLjRjMCwxLjQsMy4xLDEsMy4xLTAuNVY2Ljl6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-check: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik05IDE2LjE3TDQuODMgMTJsLTEuNDIgMS40MUw5IDE5IDIxIDdsLTEuNDEtMS40MXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-circle-empty: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDJDNi40NyAyIDIgNi40NyAyIDEyczQuNDcgMTAgMTAgMTAgMTAtNC40NyAxMC0xMFMxNy41MyAyIDEyIDJ6bTAgMThjLTQuNDEgMC04LTMuNTktOC04czMuNTktOCA4LTggOCAzLjU5IDggOC0zLjU5IDgtOCA4eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-circle: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPGNpcmNsZSBjeD0iOSIgY3k9IjkiIHI9IjgiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-clear: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8bWFzayBpZD0iZG9udXRIb2xlIj4KICAgIDxyZWN0IHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgZmlsbD0id2hpdGUiIC8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSI4IiBmaWxsPSJibGFjayIvPgogIDwvbWFzaz4KCiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxyZWN0IGhlaWdodD0iMTgiIHdpZHRoPSIyIiB4PSIxMSIgeT0iMyIgdHJhbnNmb3JtPSJyb3RhdGUoMzE1LCAxMiwgMTIpIi8+CiAgICA8Y2lyY2xlIGN4PSIxMiIgY3k9IjEyIiByPSIxMCIgbWFzaz0idXJsKCNkb251dEhvbGUpIi8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-close: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1ub25lIGpwLWljb24tc2VsZWN0YWJsZS1pbnZlcnNlIGpwLWljb24zLWhvdmVyIiBmaWxsPSJub25lIj4KICAgIDxjaXJjbGUgY3g9IjEyIiBjeT0iMTIiIHI9IjExIi8+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIGpwLWljb24tYWNjZW50Mi1ob3ZlciIgZmlsbD0iIzYxNjE2MSI+CiAgICA8cGF0aCBkPSJNMTkgNi40MUwxNy41OSA1IDEyIDEwLjU5IDYuNDEgNSA1IDYuNDEgMTAuNTkgMTIgNSAxNy41OSA2LjQxIDE5IDEyIDEzLjQxIDE3LjU5IDE5IDE5IDE3LjU5IDEzLjQxIDEyeiIvPgogIDwvZz4KCiAgPGcgY2xhc3M9ImpwLWljb24tbm9uZSBqcC1pY29uLWJ1c3kiIGZpbGw9Im5vbmUiPgogICAgPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-code: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTExLjQgMTguNkw2LjggMTRMMTEuNCA5LjRMMTAgOEw0IDE0TDEwIDIwTDExLjQgMTguNlpNMTYuNiAxOC42TDIxLjIgMTRMMTYuNiA5LjRMMTggOEwyNCAxNEwxOCAyMEwxNi42IDE4LjZWMTguNloiLz4KCTwvZz4KPC9zdmc+Cg==);
  --jp-icon-console: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIwMCAyMDAiPgogIDxnIGNsYXNzPSJqcC1pY29uLWJyYW5kMSBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiMwMjg4RDEiPgogICAgPHBhdGggZD0iTTIwIDE5LjhoMTYwdjE1OS45SDIweiIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGZpbGw9IiNmZmYiPgogICAgPHBhdGggZD0iTTEwNSAxMjcuM2g0MHYxMi44aC00MHpNNTEuMSA3N0w3NCA5OS45bC0yMy4zIDIzLjMgMTAuNSAxMC41IDIzLjMtMjMuM0w5NSA5OS45IDg0LjUgODkuNCA2MS42IDY2LjV6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-copy: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMTggMTgiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTExLjksMUgzLjJDMi40LDEsMS43LDEuNywxLjcsMi41djEwLjJoMS41VjIuNWg4LjdWMXogTTE0LjEsMy45aC04Yy0wLjgsMC0xLjUsMC43LTEuNSwxLjV2MTAuMmMwLDAuOCwwLjcsMS41LDEuNSwxLjVoOCBjMC44LDAsMS41LTAuNywxLjUtMS41VjUuNEMxNS41LDQuNiwxNC45LDMuOSwxNC4xLDMuOXogTTE0LjEsMTUuNWgtOFY1LjRoOFYxNS41eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-copyright: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDI0IDI0IiBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCI+CiAgPGcgY2xhc3M9ImpwLWljb24zIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik0xMS44OCw5LjE0YzEuMjgsMC4wNiwxLjYxLDEuMTUsMS42MywxLjY2aDEuNzljLTAuMDgtMS45OC0xLjQ5LTMuMTktMy40NS0zLjE5QzkuNjQsNy42MSw4LDksOCwxMi4xNCBjMCwxLjk0LDAuOTMsNC4yNCwzLjg0LDQuMjRjMi4yMiwwLDMuNDEtMS42NSwzLjQ0LTIuOTVoLTEuNzljLTAuMDMsMC41OS0wLjQ1LDEuMzgtMS42MywxLjQ0QzEwLjU1LDE0LjgzLDEwLDEzLjgxLDEwLDEyLjE0IEMxMCw5LjI1LDExLjI4LDkuMTYsMTEuODgsOS4xNHogTTEyLDJDNi40OCwyLDIsNi40OCwyLDEyczQuNDgsMTAsMTAsMTBzMTAtNC40OCwxMC0xMFMxNy41MiwyLDEyLDJ6IE0xMiwyMGMtNC40MSwwLTgtMy41OS04LTggczMuNTktOCw4LThzOCwzLjU5LDgsOFMxNi40MSwyMCwxMiwyMHoiLz4KICA8L2c+Cjwvc3ZnPgo=);
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
  --jp-icon-julia: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDMyNSAzMDAiPgogIDxnIGNsYXNzPSJqcC1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjY2IzYzMzIj4KICAgIDxwYXRoIGQ9Ik0gMTUwLjg5ODQzOCAyMjUgQyAxNTAuODk4NDM4IDI2Ni40MjE4NzUgMTE3LjMyMDMxMiAzMDAgNzUuODk4NDM4IDMwMCBDIDM0LjQ3NjU2MiAzMDAgMC44OTg0MzggMjY2LjQyMTg3NSAwLjg5ODQzOCAyMjUgQyAwLjg5ODQzOCAxODMuNTc4MTI1IDM0LjQ3NjU2MiAxNTAgNzUuODk4NDM4IDE1MCBDIDExNy4zMjAzMTIgMTUwIDE1MC44OTg0MzggMTgzLjU3ODEyNSAxNTAuODk4NDM4IDIyNSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzM4OTgyNiI+CiAgICA8cGF0aCBkPSJNIDIzNy41IDc1IEMgMjM3LjUgMTE2LjQyMTg3NSAyMDMuOTIxODc1IDE1MCAxNjIuNSAxNTAgQyAxMjEuMDc4MTI1IDE1MCA4Ny41IDExNi40MjE4NzUgODcuNSA3NSBDIDg3LjUgMzMuNTc4MTI1IDEyMS4wNzgxMjUgMCAxNjIuNSAwIEMgMjAzLjkyMTg3NSAwIDIzNy41IDMzLjU3ODEyNSAyMzcuNSA3NSIvPgogIDwvZz4KICA8ZyBjbGFzcz0ianAtYnJhbmQwIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzk1NThiMiI+CiAgICA8cGF0aCBkPSJNIDMyNC4xMDE1NjIgMjI1IEMgMzI0LjEwMTU2MiAyNjYuNDIxODc1IDI5MC41MjM0MzggMzAwIDI0OS4xMDE1NjIgMzAwIEMgMjA3LjY3OTY4OCAzMDAgMTc0LjEwMTU2MiAyNjYuNDIxODc1IDE3NC4xMDE1NjIgMjI1IEMgMTc0LjEwMTU2MiAxODMuNTc4MTI1IDIwNy42Nzk2ODggMTUwIDI0OS4xMDE1NjIgMTUwIEMgMjkwLjUyMzQzOCAxNTAgMzI0LjEwMTU2MiAxODMuNTc4MTI1IDMyNC4xMDE1NjIgMjI1Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-jupyter-favicon: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTUyIiBoZWlnaHQ9IjE2NSIgdmlld0JveD0iMCAwIDE1MiAxNjUiIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA3ODk0NywgMTEwLjU4MjkyNykiIGQ9Ik03NS45NDIyODQyLDI5LjU4MDQ1NjEgQzQzLjMwMjM5NDcsMjkuNTgwNDU2MSAxNC43OTY3ODMyLDE3LjY1MzQ2MzQgMCwwIEM1LjUxMDgzMjExLDE1Ljg0MDY4MjkgMTUuNzgxNTM4OSwyOS41NjY3NzMyIDI5LjM5MDQ5NDcsMzkuMjc4NDE3MSBDNDIuOTk5Nyw0OC45ODk4NTM3IDU5LjI3MzcsNTQuMjA2NzgwNSA3NS45NjA1Nzg5LDU0LjIwNjc4MDUgQzkyLjY0NzQ1NzksNTQuMjA2NzgwNSAxMDguOTIxNDU4LDQ4Ljk4OTg1MzcgMTIyLjUzMDY2MywzOS4yNzg0MTcxIEMxMzYuMTM5NDUzLDI5LjU2Njc3MzIgMTQ2LjQxMDI4NCwxNS44NDA2ODI5IDE1MS45MjExNTgsMCBDMTM3LjA4Nzg2OCwxNy42NTM0NjM0IDEwOC41ODI1ODksMjkuNTgwNDU2MSA3NS45NDIyODQyLDI5LjU4MDQ1NjEgTDc1Ljk0MjI4NDIsMjkuNTgwNDU2MSBaIiAvPgogICAgPHBhdGggdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMzczNjgsIDAuNzA0ODc4KSIgZD0iTTc1Ljk3ODQ1NzksMjQuNjI2NDA3MyBDMTA4LjYxODc2MywyNC42MjY0MDczIDEzNy4xMjQ0NTgsMzYuNTUzNDQxNSAxNTEuOTIxMTU4LDU0LjIwNjc4MDUgQzE0Ni40MTAyODQsMzguMzY2MjIyIDEzNi4xMzk0NTMsMjQuNjQwMTMxNyAxMjIuNTMwNjYzLDE0LjkyODQ4NzggQzEwOC45MjE0NTgsNS4yMTY4NDM5IDkyLjY0NzQ1NzksMCA3NS45NjA1Nzg5LDAgQzU5LjI3MzcsMCA0Mi45OTk3LDUuMjE2ODQzOSAyOS4zOTA0OTQ3LDE0LjkyODQ4NzggQzE1Ljc4MTUzODksMjQuNjQwMTMxNyA1LjUxMDgzMjExLDM4LjM2NjIyMiAwLDU0LjIwNjc4MDUgQzE0LjgzMzA4MTYsMzYuNTg5OTI5MyA0My4zMzg1Njg0LDI0LjYyNjQwNzMgNzUuOTc4NDU3OSwyNC42MjY0MDczIEw3NS45Nzg0NTc5LDI0LjYyNjQwNzMgWiIgLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-jupyter: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMzkiIGhlaWdodD0iNTEiIHZpZXdCb3g9IjAgMCAzOSA1MSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgtMTYzOCAtMjI4MSkiPgogICAgPGcgY2xhc3M9ImpwLWljb24td2FybjAiIGZpbGw9IiNGMzc3MjYiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5Ljc0IDIzMTEuOTgpIiBkPSJNIDE4LjI2NDYgNy4xMzQxMUMgMTAuNDE0NSA3LjEzNDExIDMuNTU4NzIgNC4yNTc2IDAgMEMgMS4zMjUzOSAzLjgyMDQgMy43OTU1NiA3LjEzMDgxIDcuMDY4NiA5LjQ3MzAzQyAxMC4zNDE3IDExLjgxNTIgMTQuMjU1NyAxMy4wNzM0IDE4LjI2OSAxMy4wNzM0QyAyMi4yODIzIDEzLjA3MzQgMjYuMTk2MyAxMS44MTUyIDI5LjQ2OTQgOS40NzMwM0MgMzIuNzQyNCA3LjEzMDgxIDM1LjIxMjYgMy44MjA0IDM2LjUzOCAwQyAzMi45NzA1IDQuMjU3NiAyNi4xMTQ4IDcuMTM0MTEgMTguMjY0NiA3LjEzNDExWiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM5LjczIDIyODUuNDgpIiBkPSJNIDE4LjI3MzMgNS45MzkzMUMgMjYuMTIzNSA1LjkzOTMxIDMyLjk3OTMgOC44MTU4MyAzNi41MzggMTMuMDczNEMgMzUuMjEyNiA5LjI1MzAzIDMyLjc0MjQgNS45NDI2MiAyOS40Njk0IDMuNjAwNEMgMjYuMTk2MyAxLjI1ODE4IDIyLjI4MjMgMCAxOC4yNjkgMEMgMTQuMjU1NyAwIDEwLjM0MTcgMS4yNTgxOCA3LjA2ODYgMy42MDA0QyAzLjc5NTU2IDUuOTQyNjIgMS4zMjUzOSA5LjI1MzAzIDAgMTMuMDczNEMgMy41Njc0NSA4LjgyNDYzIDEwLjQyMzIgNS45MzkzMSAxOC4yNzMzIDUuOTM5MzFaIi8+CiAgICA8L2c+CiAgICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjY5LjMgMjI4MS4zMSkiIGQ9Ik0gNS44OTM1MyAyLjg0NEMgNS45MTg4OSAzLjQzMTY1IDUuNzcwODUgNC4wMTM2NyA1LjQ2ODE1IDQuNTE2NDVDIDUuMTY1NDUgNS4wMTkyMiA0LjcyMTY4IDUuNDIwMTUgNC4xOTI5OSA1LjY2ODUxQyAzLjY2NDMgNS45MTY4OCAzLjA3NDQ0IDYuMDAxNTEgMi40OTgwNSA1LjkxMTcxQyAxLjkyMTY2IDUuODIxOSAxLjM4NDYzIDUuNTYxNyAwLjk1NDg5OCA1LjE2NDAxQyAwLjUyNTE3IDQuNzY2MzMgMC4yMjIwNTYgNC4yNDkwMyAwLjA4MzkwMzcgMy42Nzc1N0MgLTAuMDU0MjQ4MyAzLjEwNjExIC0wLjAyMTIzIDIuNTA2MTcgMC4xNzg3ODEgMS45NTM2NEMgMC4zNzg3OTMgMS40MDExIDAuNzM2ODA5IDAuOTIwODE3IDEuMjA3NTQgMC41NzM1MzhDIDEuNjc4MjYgMC4yMjYyNTkgMi4yNDA1NSAwLjAyNzU5MTkgMi44MjMyNiAwLjAwMjY3MjI5QyAzLjYwMzg5IC0wLjAzMDcxMTUgNC4zNjU3MyAwLjI0OTc4OSA0Ljk0MTQyIDAuNzgyNTUxQyA1LjUxNzExIDEuMzE1MzEgNS44NTk1NiAyLjA1Njc2IDUuODkzNTMgMi44NDRaIi8+CiAgICAgIDxwYXRoIHRyYW5zZm9ybT0idHJhbnNsYXRlKDE2MzkuOCAyMzIzLjgxKSIgZD0iTSA3LjQyNzg5IDMuNTgzMzhDIDcuNDYwMDggNC4zMjQzIDcuMjczNTUgNS4wNTgxOSA2Ljg5MTkzIDUuNjkyMTNDIDYuNTEwMzEgNi4zMjYwNyA1Ljk1MDc1IDYuODMxNTYgNS4yODQxMSA3LjE0NDZDIDQuNjE3NDcgNy40NTc2MyAzLjg3MzcxIDcuNTY0MTQgMy4xNDcwMiA3LjQ1MDYzQyAyLjQyMDMyIDcuMzM3MTIgMS43NDMzNiA3LjAwODcgMS4yMDE4NCA2LjUwNjk1QyAwLjY2MDMyOCA2LjAwNTIgMC4yNzg2MSA1LjM1MjY4IDAuMTA1MDE3IDQuNjMyMDJDIC0wLjA2ODU3NTcgMy45MTEzNSAtMC4wMjYyMzYxIDMuMTU0OTQgMC4yMjY2NzUgMi40NTg1NkMgMC40Nzk1ODcgMS43NjIxNyAwLjkzMTY5NyAxLjE1NzEzIDEuNTI1NzYgMC43MjAwMzNDIDIuMTE5ODMgMC4yODI5MzUgMi44MjkxNCAwLjAzMzQzOTUgMy41NjM4OSAwLjAwMzEzMzQ0QyA0LjU0NjY3IC0wLjAzNzQwMzMgNS41MDUyOSAwLjMxNjcwNiA2LjIyOTYxIDAuOTg3ODM1QyA2Ljk1MzkzIDEuNjU4OTYgNy4zODQ4NCAyLjU5MjM1IDcuNDI3ODkgMy41ODMzOEwgNy40Mjc4OSAzLjU4MzM4WiIvPgogICAgICA8cGF0aCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxNjM4LjM2IDIyODYuMDYpIiBkPSJNIDIuMjc0NzEgNC4zOTYyOUMgMS44NDM2MyA0LjQxNTA4IDEuNDE2NzEgNC4zMDQ0NSAxLjA0Nzk5IDQuMDc4NDNDIDAuNjc5MjY4IDMuODUyNCAwLjM4NTMyOCAzLjUyMTE0IDAuMjAzMzcxIDMuMTI2NTZDIDAuMDIxNDEzNiAyLjczMTk4IC0wLjA0MDM3OTggMi4yOTE4MyAwLjAyNTgxMTYgMS44NjE4MUMgMC4wOTIwMDMxIDEuNDMxOCAwLjI4MzIwNCAxLjAzMTI2IDAuNTc1MjEzIDAuNzEwODgzQyAwLjg2NzIyMiAwLjM5MDUxIDEuMjQ2OTEgMC4xNjQ3MDggMS42NjYyMiAwLjA2MjA1OTJDIDIuMDg1NTMgLTAuMDQwNTg5NyAyLjUyNTYxIC0wLjAxNTQ3MTQgMi45MzA3NiAwLjEzNDIzNUMgMy4zMzU5MSAwLjI4Mzk0MSAzLjY4NzkyIDAuNTUxNTA1IDMuOTQyMjIgMC45MDMwNkMgNC4xOTY1MiAxLjI1NDYyIDQuMzQxNjkgMS42NzQzNiA0LjM1OTM1IDIuMTA5MTZDIDQuMzgyOTkgMi42OTEwNyA0LjE3Njc4IDMuMjU4NjkgMy43ODU5NyAzLjY4NzQ2QyAzLjM5NTE2IDQuMTE2MjQgMi44NTE2NiA0LjM3MTE2IDIuMjc0NzEgNC4zOTYyOUwgMi4yNzQ3MSA0LjM5NjI5WiIvPgogICAgPC9nPgogIDwvZz4+Cjwvc3ZnPgo=);
  --jp-icon-jupyterlab-wordmark: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyMDAiIHZpZXdCb3g9IjAgMCAxODYwLjggNDc1Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjIiIGZpbGw9IiM0RTRFNEUiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDQ4MC4xMzY0MDEsIDY0LjI3MTQ5MykiPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC4wMDAwMDAsIDU4Ljg3NTU2NikiPgogICAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgwLjA4NzYwMywgMC4xNDAyOTQpIj4KICAgICAgICA8cGF0aCBkPSJNLTQyNi45LDE2OS44YzAsNDguNy0zLjcsNjQuNy0xMy42LDc2LjRjLTEwLjgsMTAtMjUsMTUuNS0zOS43LDE1LjVsMy43LDI5IGMyMi44LDAuMyw0NC44LTcuOSw2MS45LTIzLjFjMTcuOC0xOC41LDI0LTQ0LjEsMjQtODMuM1YwSC00Mjd2MTcwLjFMLTQyNi45LDE2OS44TC00MjYuOSwxNjkuOHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTU1LjA0NTI5NiwgNTYuODM3MTA0KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuNTYyNDUzLCAxLjc5OTg0MikiPgogICAgICAgIDxwYXRoIGQ9Ik0tMzEyLDE0OGMwLDIxLDAsMzkuNSwxLjcsNTUuNGgtMzEuOGwtMi4xLTMzLjNoLTAuOGMtNi43LDExLjYtMTYuNCwyMS4zLTI4LDI3LjkgYy0xMS42LDYuNi0yNC44LDEwLTM4LjIsOS44Yy0zMS40LDAtNjktMTcuNy02OS04OVYwaDM2LjR2MTEyLjdjMCwzOC43LDExLjYsNjQuNyw0NC42LDY0LjdjMTAuMy0wLjIsMjAuNC0zLjUsMjguOS05LjQgYzguNS01LjksMTUuMS0xNC4zLDE4LjktMjMuOWMyLjItNi4xLDMuMy0xMi41LDMuMy0xOC45VjAuMmgzNi40VjE0OEgtMzEyTC0zMTIsMTQ4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuMDEzMzIyLCA1My40Nzk2MzgpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS43MDY0NTgsIDAuMjMxNDI1KSI+CiAgICAgICAgPHBhdGggZD0iTS00NzguNiw3MS40YzAtMjYtMC44LTQ3LTEuNy02Ni43aDMyLjdsMS43LDM0LjhoMC44YzcuMS0xMi41LDE3LjUtMjIuOCwzMC4xLTI5LjcgYzEyLjUtNywyNi43LTEwLjMsNDEtOS44YzQ4LjMsMCw4NC43LDQxLjcsODQuNywxMDMuM2MwLDczLjEtNDMuNywxMDkuMi05MSwxMDkuMmMtMTIuMSwwLjUtMjQuMi0yLjItMzUtNy44IGMtMTAuOC01LjYtMTkuOS0xMy45LTI2LjYtMjQuMmgtMC44VjI5MWgtMzZ2LTIyMEwtNDc4LjYsNzEuNEwtNDc4LjYsNzEuNHogTS00NDIuNiwxMjUuNmMwLjEsNS4xLDAuNiwxMC4xLDEuNywxNS4xIGMzLDEyLjMsOS45LDIzLjMsMTkuOCwzMS4xYzkuOSw3LjgsMjIuMSwxMi4xLDM0LjcsMTIuMWMzOC41LDAsNjAuNy0zMS45LDYwLjctNzguNWMwLTQwLjctMjEuMS03NS42LTU5LjUtNzUuNiBjLTEyLjksMC40LTI1LjMsNS4xLTM1LjMsMTMuNGMtOS45LDguMy0xNi45LDE5LjctMTkuNiwzMi40Yy0xLjUsNC45LTIuMywxMC0yLjUsMTUuMVYxMjUuNkwtNDQyLjYsMTI1LjZMLTQ0Mi42LDEyNS42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSg2MDYuNzQwNzI2LCA1Ni44MzcxMDQpIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMC43NTEyMjYsIDEuOTg5Mjk5KSI+CiAgICAgICAgPHBhdGggZD0iTS00NDAuOCwwbDQzLjcsMTIwLjFjNC41LDEzLjQsOS41LDI5LjQsMTIuOCw0MS43aDAuOGMzLjctMTIuMiw3LjktMjcuNywxMi44LTQyLjQgbDM5LjctMTE5LjJoMzguNUwtMzQ2LjksMTQ1Yy0yNiw2OS43LTQzLjcsMTA1LjQtNjguNiwxMjcuMmMtMTIuNSwxMS43LTI3LjksMjAtNDQuNiwyMy45bC05LjEtMzEuMSBjMTEuNy0zLjksMjIuNS0xMC4xLDMxLjgtMTguMWMxMy4yLTExLjEsMjMuNy0yNS4yLDMwLjYtNDEuMmMxLjUtMi44LDIuNS01LjcsMi45LTguOGMtMC4zLTMuMy0xLjItNi42LTIuNS05LjdMLTQ4MC4yLDAuMSBoMzkuN0wtNDQwLjgsMEwtNDQwLjgsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoODIyLjc0ODEwNCwgMC4wMDAwMDApIj4KICAgICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMS40NjQwNTAsIDAuMzc4OTE0KSI+CiAgICAgICAgPHBhdGggZD0iTS00MTMuNywwdjU4LjNoNTJ2MjguMmgtNTJWMTk2YzAsMjUsNywzOS41LDI3LjMsMzkuNWM3LjEsMC4xLDE0LjItMC43LDIxLjEtMi41IGwxLjcsMjcuN2MtMTAuMywzLjctMjEuMyw1LjQtMzIuMiw1Yy03LjMsMC40LTE0LjYtMC43LTIxLjMtMy40Yy02LjgtMi43LTEyLjktNi44LTE3LjktMTIuMWMtMTAuMy0xMC45LTE0LjEtMjktMTQuMS01Mi45IFY4Ni41aC0zMVY1OC4zaDMxVjkuNkwtNDEzLjcsMEwtNDEzLjcsMHoiLz4KICAgICAgPC9nPgogICAgPC9nPgogICAgPGcgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTc0LjQzMzI4NiwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDAuOTkwMDM0LCAwLjYxMDMzOSkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDQ1LjgsMTEzYzAuOCw1MCwzMi4yLDcwLjYsNjguNiw3MC42YzE5LDAuNiwzNy45LTMsNTUuMy0xMC41bDYuMiwyNi40IGMtMjAuOSw4LjktNDMuNSwxMy4xLTY2LjIsMTIuNmMtNjEuNSwwLTk4LjMtNDEuMi05OC4zLTEwMi41Qy00ODAuMiw0OC4yLTQ0NC43LDAtMzg2LjUsMGM2NS4yLDAsODIuNyw1OC4zLDgyLjcsOTUuNyBjLTAuMSw1LjgtMC41LDExLjUtMS4yLDE3LjJoLTE0MC42SC00NDUuOEwtNDQ1LjgsMTEzeiBNLTMzOS4yLDg2LjZjMC40LTIzLjUtOS41LTYwLjEtNTAuNC02MC4xIGMtMzYuOCwwLTUyLjgsMzQuNC01NS43LDYwLjFILTMzOS4yTC0zMzkuMiw4Ni42TC0zMzkuMiw4Ni42eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgICA8ZyB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAxLjk2MTA1OCwgNTMuNDc5NjM4KSI+CiAgICAgIDxnIHRyYW5zZm9ybT0idHJhbnNsYXRlKDEuMTc5NjQwLCAwLjcwNTA2OCkiPgogICAgICAgIDxwYXRoIGQ9Ik0tNDc4LjYsNjhjMC0yMy45LTAuNC00NC41LTEuNy02My40aDMxLjhsMS4yLDM5LjloMS43YzkuMS0yNy4zLDMxLTQ0LjUsNTUuMy00NC41IGMzLjUtMC4xLDcsMC40LDEwLjMsMS4ydjM0LjhjLTQuMS0wLjktOC4yLTEuMy0xMi40LTEuMmMtMjUuNiwwLTQzLjcsMTkuNy00OC43LDQ3LjRjLTEsNS43LTEuNiwxMS41LTEuNywxNy4ydjEwOC4zaC0zNlY2OCBMLTQ3OC42LDY4eiIvPgogICAgICA8L2c+CiAgICA8L2c+CiAgPC9nPgoKICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCIgZmlsbD0iI0YzNzcyNiI+CiAgICA8cGF0aCBkPSJNMTM1Mi4zLDMyNi4yaDM3VjI4aC0zN1YzMjYuMnogTTE2MDQuOCwzMjYuMmMtMi41LTEzLjktMy40LTMxLjEtMy40LTQ4Ljd2LTc2IGMwLTQwLjctMTUuMS04My4xLTc3LjMtODMuMWMtMjUuNiwwLTUwLDcuMS02Ni44LDE4LjFsOC40LDI0LjRjMTQuMy05LjIsMzQtMTUuMSw1My0xNS4xYzQxLjYsMCw0Ni4yLDMwLjIsNDYuMiw0N3Y0LjIgYy03OC42LTAuNC0xMjIuMywyNi41LTEyMi4zLDc1LjZjMCwyOS40LDIxLDU4LjQsNjIuMiw1OC40YzI5LDAsNTAuOS0xNC4zLDYyLjItMzAuMmgxLjNsMi45LDI1LjZIMTYwNC44eiBNMTU2NS43LDI1Ny43IGMwLDMuOC0wLjgsOC0yLjEsMTEuOGMtNS45LDE3LjItMjIuNywzNC00OS4yLDM0Yy0xOC45LDAtMzQuOS0xMS4zLTM0LjktMzUuM2MwLTM5LjUsNDUuOC00Ni42LDg2LjItNDUuOFYyNTcuN3ogTTE2OTguNSwzMjYuMiBsMS43LTMzLjZoMS4zYzE1LjEsMjYuOSwzOC43LDM4LjIsNjguMSwzOC4yYzQ1LjQsMCw5MS4yLTM2LjEsOTEuMi0xMDguOGMwLjQtNjEuNy0zNS4zLTEwMy43LTg1LjctMTAzLjcgYy0zMi44LDAtNTYuMywxNC43LTY5LjMsMzcuNGgtMC44VjI4aC0zNi42djI0NS43YzAsMTguMS0wLjgsMzguNi0xLjcsNTIuNUgxNjk4LjV6IE0xNzA0LjgsMjA4LjJjMC01LjksMS4zLTEwLjksMi4xLTE1LjEgYzcuNi0yOC4xLDMxLjEtNDUuNCw1Ni4zLTQ1LjRjMzkuNSwwLDYwLjUsMzQuOSw2MC41LDc1LjZjMCw0Ni42LTIzLjEsNzguMS02MS44LDc4LjFjLTI2LjksMC00OC4zLTE3LjYtNTUuNS00My4zIGMtMC44LTQuMi0xLjctOC44LTEuNy0xMy40VjIwOC4yeiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgZmlsbD0iIzYxNjE2MSIgZD0iTTE1IDlIOXY2aDZWOXptLTIgNGgtMnYtMmgydjJ6bTgtMlY5aC0yVjdjMC0xLjEtLjktMi0yLTJoLTJWM2gtMnYyaC0yVjNIOXYySDdjLTEuMSAwLTIgLjktMiAydjJIM3YyaDJ2MkgzdjJoMnYyYzAgMS4xLjkgMiAyIDJoMnYyaDJ2LTJoMnYyaDJ2LTJoMmMxLjEgMCAyLS45IDItMnYtMmgydi0yaC0ydi0yaDJ6bS00IDZIN1Y3aDEwdjEweiIvPgo8L3N2Zz4K);
  --jp-icon-keyboard: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMjAgNUg0Yy0xLjEgMC0xLjk5LjktMS45OSAyTDIgMTdjMCAxLjEuOSAyIDIgMmgxNmMxLjEgMCAyLS45IDItMlY3YzAtMS4xLS45LTItMi0yem0tOSAzaDJ2MmgtMlY4em0wIDNoMnYyaC0ydi0yek04IDhoMnYySDhWOHptMCAzaDJ2Mkg4di0yem0tMSAySDV2LTJoMnYyem0wLTNINVY4aDJ2MnptOSA3SDh2LTJoOHYyem0wLTRoLTJ2LTJoMnYyem0wLTNoLTJWOGgydjJ6bTMgM2gtMnYtMmgydjJ6bTAtM2gtMlY4aDJ2MnoiLz4KPC9zdmc+Cg==);
  --jp-icon-launcher: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTkgMTlINVY1aDdWM0g1YTIgMiAwIDAwLTIgMnYxNGEyIDIgMCAwMDIgMmgxNGMxLjEgMCAyLS45IDItMnYtN2gtMnY3ek0xNCAzdjJoMy41OWwtOS44MyA5LjgzIDEuNDEgMS40MUwxOSA2LjQxVjEwaDJWM2gtN3oiLz4KPC9zdmc+Cg==);
  --jp-icon-line-form: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGZpbGw9IndoaXRlIiBkPSJNNS44OCA0LjEyTDEzLjc2IDEybC03Ljg4IDcuODhMOCAyMmwxMC0xMEw4IDJ6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-link: url(data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIxNiIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTMuOSAxMmMwLTEuNzEgMS4zOS0zLjEgMy4xLTMuMWg0VjdIN2MtMi43NiAwLTUgMi4yNC01IDVzMi4yNCA1IDUgNWg0di0xLjlIN2MtMS43MSAwLTMuMS0xLjM5LTMuMS0zLjF6TTggMTNoOHYtMkg4djJ6bTktNmgtNHYxLjloNGMxLjcxIDAgMy4xIDEuMzkgMy4xIDMuMXMtMS4zOSAzLjEtMy4xIDMuMWgtNFYxN2g0YzIuNzYgMCA1LTIuMjQgNS01cy0yLjI0LTUtNS01eiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-list: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiM2MTYxNjEiIGQ9Ik0xOSA1djE0SDVWNWgxNG0xLjEtMkgzLjljLS41IDAtLjkuNC0uOS45djE2LjJjMCAuNC40LjkuOS45aDE2LjJjLjQgMCAuOS0uNS45LS45VjMuOWMwLS41LS41LS45LS45LS45ek0xMSA3aDZ2MmgtNlY3em0wIDRoNnYyaC02di0yem0wIDRoNnYyaC02ek03IDdoMnYySDd6bTAgNGgydjJIN3ptMCA0aDJ2Mkg3eiIvPgo8L3N2Zz4=);
  --jp-icon-listings-info: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MC45NzggNTAuOTc4IiBzdHlsZT0iZW5hYmxlLWJhY2tncm91bmQ6bmV3IDAgMCA1MC45NzggNTAuOTc4OyIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSI+Cgk8Zz4KCQk8cGF0aCBzdHlsZT0iZmlsbDojMDEwMDAyOyIgZD0iTTQzLjUyLDcuNDU4QzM4LjcxMSwyLjY0OCwzMi4zMDcsMCwyNS40ODksMEMxOC42NywwLDEyLjI2NiwyLjY0OCw3LjQ1OCw3LjQ1OAoJCQljLTkuOTQzLDkuOTQxLTkuOTQzLDI2LjExOSwwLDM2LjA2MmM0LjgwOSw0LjgwOSwxMS4yMTIsNy40NTYsMTguMDMxLDcuNDU4YzAsMCwwLjAwMSwwLDAuMDAyLDAKCQkJYzYuODE2LDAsMTMuMjIxLTIuNjQ4LDE4LjAyOS03LjQ1OGM0LjgwOS00LjgwOSw3LjQ1Ny0xMS4yMTIsNy40NTctMTguMDNDNTAuOTc3LDE4LjY3LDQ4LjMyOCwxMi4yNjYsNDMuNTIsNy40NTh6CgkJCSBNNDIuMTA2LDQyLjEwNWMtNC40MzIsNC40MzEtMTAuMzMyLDYuODcyLTE2LjYxNSw2Ljg3MmgtMC4wMDJjLTYuMjg1LTAuMDAxLTEyLjE4Ny0yLjQ0MS0xNi42MTctNi44NzIKCQkJYy05LjE2Mi05LjE2My05LjE2Mi0yNC4wNzEsMC0zMy4yMzNDMTMuMzAzLDQuNDQsMTkuMjA0LDIsMjUuNDg5LDJjNi4yODQsMCwxMi4xODYsMi40NCwxNi42MTcsNi44NzIKCQkJYzQuNDMxLDQuNDMxLDYuODcxLDEwLjMzMiw2Ljg3MSwxNi42MTdDNDguOTc3LDMxLjc3Miw0Ni41MzYsMzcuNjc1LDQyLjEwNiw0Mi4xMDV6Ii8+CgkJPHBhdGggc3R5bGU9ImZpbGw6IzAxMDAwMjsiIGQ9Ik0yMy41NzgsMzIuMjE4Yy0wLjAyMy0xLjczNCwwLjE0My0zLjA1OSwwLjQ5Ni0zLjk3MmMwLjM1My0wLjkxMywxLjExLTEuOTk3LDIuMjcyLTMuMjUzCgkJCWMwLjQ2OC0wLjUzNiwwLjkyMy0xLjA2MiwxLjM2Ny0xLjU3NWMwLjYyNi0wLjc1MywxLjEwNC0xLjQ3OCwxLjQzNi0yLjE3NWMwLjMzMS0wLjcwNywwLjQ5NS0xLjU0MSwwLjQ5NS0yLjUKCQkJYzAtMS4wOTYtMC4yNi0yLjA4OC0wLjc3OS0yLjk3OWMtMC41NjUtMC44NzktMS41MDEtMS4zMzYtMi44MDYtMS4zNjljLTEuODAyLDAuMDU3LTIuOTg1LDAuNjY3LTMuNTUsMS44MzIKCQkJYy0wLjMwMSwwLjUzNS0wLjUwMywxLjE0MS0wLjYwNywxLjgxNGMtMC4xMzksMC43MDctMC4yMDcsMS40MzItMC4yMDcsMi4xNzRoLTIuOTM3Yy0wLjA5MS0yLjIwOCwwLjQwNy00LjExNCwxLjQ5My01LjcxOQoJCQljMS4wNjItMS42NCwyLjg1NS0yLjQ4MSw1LjM3OC0yLjUyN2MyLjE2LDAuMDIzLDMuODc0LDAuNjA4LDUuMTQxLDEuNzU4YzEuMjc4LDEuMTYsMS45MjksMi43NjQsMS45NSw0LjgxMQoJCQljMCwxLjE0Mi0wLjEzNywyLjExMS0wLjQxLDIuOTExYy0wLjMwOSwwLjg0NS0wLjczMSwxLjU5My0xLjI2OCwyLjI0M2MtMC40OTIsMC42NS0xLjA2OCwxLjMxOC0xLjczLDIuMDAyCgkJCWMtMC42NSwwLjY5Ny0xLjMxMywxLjQ3OS0xLjk4NywyLjM0NmMtMC4yMzksMC4zNzctMC40MjksMC43NzctMC41NjUsMS4xOTljLTAuMTYsMC45NTktMC4yMTcsMS45NTEtMC4xNzEsMi45NzkKCQkJQzI2LjU4OSwzMi4yMTgsMjMuNTc4LDMyLjIxOCwyMy41NzgsMzIuMjE4eiBNMjMuNTc4LDM4LjIydi0zLjQ4NGgzLjA3NnYzLjQ4NEgyMy41Nzh6Ii8+Cgk8L2c+Cjwvc3ZnPgo=);
  --jp-icon-markdown: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjN0IxRkEyIiBkPSJNNSAxNC45aDEybC02LjEgNnptOS40LTYuOGMwLTEuMy0uMS0yLjktLjEtNC41LS40IDEuNC0uOSAyLjktMS4zIDQuM2wtMS4zIDQuM2gtMkw4LjUgNy45Yy0uNC0xLjMtLjctMi45LTEtNC4zLS4xIDEuNi0uMSAzLjItLjIgNC42TDcgMTIuNEg0LjhsLjctMTFoMy4zTDEwIDVjLjQgMS4yLjcgMi43IDEgMy45LjMtMS4yLjctMi42IDEtMy45bDEuMi0zLjdoMy4zbC42IDExaC0yLjRsLS4zLTQuMnoiLz4KPC9zdmc+Cg==);
  --jp-icon-new-folder: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTIwIDZoLThsLTItMkg0Yy0xLjExIDAtMS45OS44OS0xLjk5IDJMMiAxOGMwIDEuMTEuODkgMiAyIDJoMTZjMS4xMSAwIDItLjg5IDItMlY4YzAtMS4xMS0uODktMi0yLTJ6bS0xIDhoLTN2M2gtMnYtM2gtM3YtMmgzVjloMnYzaDN2MnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-not-trusted: url(data:image/svg+xml;base64,PHN2ZyBmaWxsPSJub25lIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI1IDI1Ij4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDMgMykiIGQ9Ik0xLjg2MDk0IDExLjQ0MDlDMC44MjY0NDggOC43NzAyNyAwLjg2Mzc3OSA2LjA1NzY0IDEuMjQ5MDcgNC4xOTkzMkMyLjQ4MjA2IDMuOTMzNDcgNC4wODA2OCAzLjQwMzQ3IDUuNjAxMDIgMi44NDQ5QzcuMjM1NDkgMi4yNDQ0IDguODU2NjYgMS41ODE1IDkuOTg3NiAxLjA5NTM5QzExLjA1OTcgMS41ODM0MSAxMi42MDk0IDIuMjQ0NCAxNC4yMTggMi44NDMzOUMxNS43NTAzIDMuNDEzOTQgMTcuMzk5NSAzLjk1MjU4IDE4Ljc1MzkgNC4yMTM4NUMxOS4xMzY0IDYuMDcxNzcgMTkuMTcwOSA4Ljc3NzIyIDE4LjEzOSAxMS40NDA5QzE3LjAzMDMgMTQuMzAzMiAxNC42NjY4IDE3LjE4NDQgOS45OTk5OSAxOC45MzU0QzUuMzMzMTkgMTcuMTg0NCAyLjk2OTY4IDE0LjMwMzIgMS44NjA5NCAxMS40NDA5WiIvPgogICAgPHBhdGggY2xhc3M9ImpwLWljb24yIiBzdHJva2U9IiMzMzMzMzMiIHN0cm9rZS13aWR0aD0iMiIgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOS4zMTU5MiA5LjMyMDMxKSIgZD0iTTcuMzY4NDIgMEwwIDcuMzY0NzkiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uMiIgc3Ryb2tlPSIjMzMzMzMzIiBzdHJva2Utd2lkdGg9IjIiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDkuMzE1OTIgMTYuNjgzNikgc2NhbGUoMSAtMSkiIGQ9Ik03LjM2ODQyIDBMMCA3LjM2NDc5Ii8+Cjwvc3ZnPgo=);
  --jp-icon-notebook: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi13YXJuMCBqcC1pY29uLXNlbGVjdGFibGUiIGZpbGw9IiNFRjZDMDAiPgogICAgPHBhdGggZD0iTTE4LjcgMy4zdjE1LjRIMy4zVjMuM2gxNS40bTEuNS0xLjVIMS44djE4LjNoMTguM2wuMS0xOC4zeiIvPgogICAgPHBhdGggZD0iTTE2LjUgMTYuNWwtNS40LTQuMy01LjYgNC4zdi0xMWgxMXoiLz4KICA8L2c+Cjwvc3ZnPgo=);
  --jp-icon-numbering: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjIiIGhlaWdodD0iMjIiIHZpZXdCb3g9IjAgMCAyOCAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTQgMTlINlYxOS41SDVWMjAuNUg2VjIxSDRWMjJIN1YxOEg0VjE5Wk01IDEwSDZWNkg0VjdINVYxMFpNNCAxM0g1LjhMNCAxNS4xVjE2SDdWMTVINS4yTDcgMTIuOVYxMkg0VjEzWk05IDdWOUgyM1Y3SDlaTTkgMjFIMjNWMTlIOVYyMVpNOSAxNUgyM1YxM0g5VjE1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-offline-bolt: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTEyIDIuMDJjLTUuNTEgMC05Ljk4IDQuNDctOS45OCA5Ljk4czQuNDcgOS45OCA5Ljk4IDkuOTggOS45OC00LjQ3IDkuOTgtOS45OFMxNy41MSAyLjAyIDEyIDIuMDJ6TTExLjQ4IDIwdi02LjI2SDhMMTMgNHY2LjI2aDMuMzVMMTEuNDggMjB6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-palette: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgPHBhdGggZD0iTTE4IDEzVjIwSDRWNkg5LjAyQzkuMDcgNS4yOSA5LjI0IDQuNjIgOS41IDRINEMyLjkgNCAyIDQuOSAyIDZWMjBDMiAyMS4xIDIuOSAyMiA0IDIySDE4QzE5LjEgMjIgMjAgMjEuMSAyMCAyMFYxNUwxOCAxM1pNMTkuMyA4Ljg5QzE5Ljc0IDguMTkgMjAgNy4zOCAyMCA2LjVDMjAgNC4wMSAxNy45OSAyIDE1LjUgMkMxMy4wMSAyIDExIDQuMDEgMTEgNi41QzExIDguOTkgMTMuMDEgMTEgMTUuNDkgMTFDMTYuMzcgMTEgMTcuMTkgMTAuNzQgMTcuODggMTAuM0wyMSAxMy40MkwyMi40MiAxMkwxOS4zIDguODlaTTE1LjUgOUMxNC4xMiA5IDEzIDcuODggMTMgNi41QzEzIDUuMTIgMTQuMTIgNCAxNS41IDRDMTYuODggNCAxOCA1LjEyIDE4IDYuNUMxOCA3Ljg4IDE2Ljg4IDkgMTUuNSA5WiIvPgogICAgPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik00IDZIOS4wMTg5NEM5LjAwNjM5IDYuMTY1MDIgOSA2LjMzMTc2IDkgNi41QzkgOC44MTU3NyAxMC4yMTEgMTAuODQ4NyAxMi4wMzQzIDEySDlWMTRIMTZWMTIuOTgxMUMxNi41NzAzIDEyLjkzNzcgMTcuMTIgMTIuODIwNyAxNy42Mzk2IDEyLjYzOTZMMTggMTNWMjBINFY2Wk04IDhINlYxMEg4VjhaTTYgMTJIOFYxNEg2VjEyWk04IDE2SDZWMThIOFYxNlpNOSAxNkgxNlYxOEg5VjE2WiIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-paste: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTE5IDJoLTQuMThDMTQuNC44NCAxMy4zIDAgMTIgMGMtMS4zIDAtMi40Ljg0LTIuODIgMkg1Yy0xLjEgMC0yIC45LTIgMnYxNmMwIDEuMS45IDIgMiAyaDE0YzEuMSAwIDItLjkgMi0yVjRjMC0xLjEtLjktMi0yLTJ6bS03IDBjLjU1IDAgMSAuNDUgMSAxcy0uNDUgMS0xIDEtMS0uNDUtMS0xIC40NS0xIDEtMXptNyAxOEg1VjRoMnYzaDEwVjRoMnYxNnoiLz4KICAgIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-pdf: url(data:image/svg+xml;base64,PHN2ZwogICB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyMiAyMiIgd2lkdGg9IjE2Ij4KICAgIDxwYXRoIHRyYW5zZm9ybT0icm90YXRlKDQ1KSIgY2xhc3M9ImpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iI0ZGMkEyQSIKICAgICAgIGQ9Im0gMjIuMzQ0MzY5LC0zLjAxNjM2NDIgaCA1LjYzODYwNCB2IDEuNTc5MjQzMyBoIC0zLjU0OTIyNyB2IDEuNTA4NjkyOTkgaCAzLjMzNzU3NiBWIDEuNjUwODE1NCBoIC0zLjMzNzU3NiB2IDMuNDM1MjYxMyBoIC0yLjA4OTM3NyB6IG0gLTcuMTM2NDQ0LDEuNTc5MjQzMyB2IDQuOTQzOTU0MyBoIDAuNzQ4OTIgcSAxLjI4MDc2MSwwIDEuOTUzNzAzLC0wLjYzNDk1MzUgMC42NzgzNjksLTAuNjM0OTUzNSAwLjY3ODM2OSwtMS44NDUxNjQxIDAsLTEuMjA0NzgzNTUgLTAuNjcyOTQyLC0xLjgzNDMxMDExIC0wLjY3Mjk0MiwtMC42Mjk1MjY1OSAtMS45NTkxMywtMC42Mjk1MjY1OSB6IG0gLTIuMDg5Mzc3LC0xLjU3OTI0MzMgaCAyLjIwMzM0MyBxIDEuODQ1MTY0LDAgMi43NDYwMzksMC4yNjU5MjA3IDAuOTA2MzAxLDAuMjYwNDkzNyAxLjU1MjEwOCwwLjg5MDAyMDMgMC41Njk4MywwLjU0ODEyMjMgMC44NDY2MDUsMS4yNjQ0ODAwNiAwLjI3Njc3NCwwLjcxNjM1NzgxIDAuMjc2Nzc0LDEuNjIyNjU4OTQgMCwwLjkxNzE1NTEgLTAuMjc2Nzc0LDEuNjM4OTM5OSAtMC4yNzY3NzUsMC43MTYzNTc4IC0wLjg0NjYwNSwxLjI2NDQ4IC0wLjY1MTIzNCwwLjYyOTUyNjYgLTEuNTYyOTYyLDAuODk1NDQ3MyAtMC45MTE3MjgsMC4yNjA0OTM3IC0yLjczNTE4NSwwLjI2MDQ5MzcgaCAtMi4yMDMzNDMgeiBtIC04LjE0NTg1NjUsMCBoIDMuNDY3ODIzIHEgMS41NDY2ODE2LDAgMi4zNzE1Nzg1LDAuNjg5MjIzIDAuODMwMzI0LDAuNjgzNzk2MSAwLjgzMDMyNCwxLjk1MzcwMzE0IDAsMS4yNzUzMzM5NyAtMC44MzAzMjQsMS45NjQ1NTcwNiBRIDkuOTg3MTk2MSwyLjI3NDkxNSA4LjQ0MDUxNDUsMi4yNzQ5MTUgSCA3LjA2MjA2ODQgViA1LjA4NjA3NjcgSCA0Ljk3MjY5MTUgWiBtIDIuMDg5Mzc2OSwxLjUxNDExOTkgdiAyLjI2MzAzOTQzIGggMS4xNTU5NDEgcSAwLjYwNzgxODgsMCAwLjkzODg2MjksLTAuMjkzMDU1NDcgMC4zMzEwNDQxLC0wLjI5ODQ4MjQxIDAuMzMxMDQ0MSwtMC44NDExNzc3MiAwLC0wLjU0MjY5NTMxIC0wLjMzMTA0NDEsLTAuODM1NzUwNzQgLTAuMzMxMDQ0MSwtMC4yOTMwNTU1IC0wLjkzODg2MjksLTAuMjkzMDU1NSB6IgovPgo8L3N2Zz4K);
  --jp-icon-python: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8ZyBjbGFzcz0ianAtaWNvbi1icmFuZDAganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMEQ0N0ExIj4KICAgIDxwYXRoIGQ9Ik0xMS4xIDYuOVY1LjhINi45YzAtLjUgMC0xLjMuMi0xLjYuNC0uNy44LTEuMSAxLjctMS40IDEuNy0uMyAyLjUtLjMgMy45LS4xIDEgLjEgMS45LjkgMS45IDEuOXY0LjJjMCAuNS0uOSAxLjYtMiAxLjZIOC44Yy0xLjUgMC0yLjQgMS40LTIuNCAyLjh2Mi4ySDQuN0MzLjUgMTUuMSAzIDE0IDMgMTMuMVY5Yy0uMS0xIC42LTIgMS44LTIgMS41LS4xIDYuMy0uMSA2LjMtLjF6Ii8+CiAgICA8cGF0aCBkPSJNMTAuOSAxNS4xdjEuMWg0LjJjMCAuNSAwIDEuMy0uMiAxLjYtLjQuNy0uOCAxLjEtMS43IDEuNC0xLjcuMy0yLjUuMy0zLjkuMS0xLS4xLTEuOS0uOS0xLjktMS45di00LjJjMC0uNS45LTEuNiAyLTEuNmgzLjhjMS41IDAgMi40LTEuNCAyLjQtMi44VjYuNmgxLjdDMTguNSA2LjkgMTkgOCAxOSA4LjlWMTNjMCAxLS43IDIuMS0xLjkgMi4xaC02LjJ6Ii8+CiAgPC9nPgo8L3N2Zz4K);
  --jp-icon-r-kernel: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDIyIDIyIj4KICA8cGF0aCBjbGFzcz0ianAtaWNvbi1jb250cmFzdDMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjMjE5NkYzIiBkPSJNNC40IDIuNWMxLjItLjEgMi45LS4zIDQuOS0uMyAyLjUgMCA0LjEuNCA1LjIgMS4zIDEgLjcgMS41IDEuOSAxLjUgMy41IDAgMi0xLjQgMy41LTIuOSA0LjEgMS4yLjQgMS43IDEuNiAyLjIgMyAuNiAxLjkgMSAzLjkgMS4zIDQuNmgtMy44Yy0uMy0uNC0uOC0xLjctMS4yLTMuN3MtMS4yLTIuNi0yLjYtMi42aC0uOXY2LjRINC40VjIuNXptMy43IDYuOWgxLjRjMS45IDAgMi45LS45IDIuOS0yLjNzLTEtMi4zLTIuOC0yLjNjLS43IDAtMS4zIDAtMS42LjJ2NC41aC4xdi0uMXoiLz4KPC9zdmc+Cg==);
  --jp-icon-react: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMTUwIDE1MCA1NDEuOSAyOTUuMyI+CiAgPGcgY2xhc3M9ImpwLWljb24tYnJhbmQyIGpwLWljb24tc2VsZWN0YWJsZSIgZmlsbD0iIzYxREFGQiI+CiAgICA8cGF0aCBkPSJNNjY2LjMgMjk2LjVjMC0zMi41LTQwLjctNjMuMy0xMDMuMS04Mi40IDE0LjQtNjMuNiA4LTExNC4yLTIwLjItMTMwLjQtNi41LTMuOC0xNC4xLTUuNi0yMi40LTUuNnYyMi4zYzQuNiAwIDguMy45IDExLjQgMi42IDEzLjYgNy44IDE5LjUgMzcuNSAxNC45IDc1LjctMS4xIDkuNC0yLjkgMTkuMy01LjEgMjkuNC0xOS42LTQuOC00MS04LjUtNjMuNS0xMC45LTEzLjUtMTguNS0yNy41LTM1LjMtNDEuNi01MCAzMi42LTMwLjMgNjMuMi00Ni45IDg0LTQ2LjlWNzhjLTI3LjUgMC02My41IDE5LjYtOTkuOSA1My42LTM2LjQtMzMuOC03Mi40LTUzLjItOTkuOS01My4ydjIyLjNjMjAuNyAwIDUxLjQgMTYuNSA4NCA0Ni42LTE0IDE0LjctMjggMzEuNC00MS4zIDQ5LjktMjIuNiAyLjQtNDQgNi4xLTYzLjYgMTEtMi4zLTEwLTQtMTkuNy01LjItMjktNC43LTM4LjIgMS4xLTY3LjkgMTQuNi03NS44IDMtMS44IDYuOS0yLjYgMTEuNS0yLjZWNzguNWMtOC40IDAtMTYgMS44LTIyLjYgNS42LTI4LjEgMTYuMi0zNC40IDY2LjctMTkuOSAxMzAuMS02Mi4yIDE5LjItMTAyLjcgNDkuOS0xMDIuNyA4Mi4zIDAgMzIuNSA0MC43IDYzLjMgMTAzLjEgODIuNC0xNC40IDYzLjYtOCAxMTQuMiAyMC4yIDEzMC40IDYuNSAzLjggMTQuMSA1LjYgMjIuNSA1LjYgMjcuNSAwIDYzLjUtMTkuNiA5OS45LTUzLjYgMzYuNCAzMy44IDcyLjQgNTMuMiA5OS45IDUzLjIgOC40IDAgMTYtMS44IDIyLjYtNS42IDI4LjEtMTYuMiAzNC40LTY2LjcgMTkuOS0xMzAuMSA2Mi0xOS4xIDEwMi41LTQ5LjkgMTAyLjUtODIuM3ptLTEzMC4yLTY2LjdjLTMuNyAxMi45LTguMyAyNi4yLTEzLjUgMzkuNS00LjEtOC04LjQtMTYtMTMuMS0yNC00LjYtOC05LjUtMTUuOC0xNC40LTIzLjQgMTQuMiAyLjEgMjcuOSA0LjcgNDEgNy45em0tNDUuOCAxMDYuNWMtNy44IDEzLjUtMTUuOCAyNi4zLTI0LjEgMzguMi0xNC45IDEuMy0zMCAyLTQ1LjIgMi0xNS4xIDAtMzAuMi0uNy00NS0xLjktOC4zLTExLjktMTYuNC0yNC42LTI0LjItMzgtNy42LTEzLjEtMTQuNS0yNi40LTIwLjgtMzkuOCA2LjItMTMuNCAxMy4yLTI2LjggMjAuNy0zOS45IDcuOC0xMy41IDE1LjgtMjYuMyAyNC4xLTM4LjIgMTQuOS0xLjMgMzAtMiA0NS4yLTIgMTUuMSAwIDMwLjIuNyA0NSAxLjkgOC4zIDExLjkgMTYuNCAyNC42IDI0LjIgMzggNy42IDEzLjEgMTQuNSAyNi40IDIwLjggMzkuOC02LjMgMTMuNC0xMy4yIDI2LjgtMjAuNyAzOS45em0zMi4zLTEzYzUuNCAxMy40IDEwIDI2LjggMTMuOCAzOS44LTEzLjEgMy4yLTI2LjkgNS45LTQxLjIgOCA0LjktNy43IDkuOC0xNS42IDE0LjQtMjMuNyA0LjYtOCA4LjktMTYuMSAxMy0yNC4xek00MjEuMiA0MzBjLTkuMy05LjYtMTguNi0yMC4zLTI3LjgtMzIgOSAuNCAxOC4yLjcgMjcuNS43IDkuNCAwIDE4LjctLjIgMjcuOC0uNy05IDExLjctMTguMyAyMi40LTI3LjUgMzJ6bS03NC40LTU4LjljLTE0LjItMi4xLTI3LjktNC43LTQxLTcuOSAzLjctMTIuOSA4LjMtMjYuMiAxMy41LTM5LjUgNC4xIDggOC40IDE2IDEzLjEgMjQgNC43IDggOS41IDE1LjggMTQuNCAyMy40ek00MjAuNyAxNjNjOS4zIDkuNiAxOC42IDIwLjMgMjcuOCAzMi05LS40LTE4LjItLjctMjcuNS0uNy05LjQgMC0xOC43LjItMjcuOC43IDktMTEuNyAxOC4zLTIyLjQgMjcuNS0zMnptLTc0IDU4LjljLTQuOSA3LjctOS44IDE1LjYtMTQuNCAyMy43LTQuNiA4LTguOSAxNi0xMyAyNC01LjQtMTMuNC0xMC0yNi44LTEzLjgtMzkuOCAxMy4xLTMuMSAyNi45LTUuOCA0MS4yLTcuOXptLTkwLjUgMTI1LjJjLTM1LjQtMTUuMS01OC4zLTM0LjktNTguMy01MC42IDAtMTUuNyAyMi45LTM1LjYgNTguMy01MC42IDguNi0zLjcgMTgtNyAyNy43LTEwLjEgNS43IDE5LjYgMTMuMiA0MCAyMi41IDYwLjktOS4yIDIwLjgtMTYuNiA0MS4xLTIyLjIgNjAuNi05LjktMy4xLTE5LjMtNi41LTI4LTEwLjJ6TTMxMCA0OTBjLTEzLjYtNy44LTE5LjUtMzcuNS0xNC45LTc1LjcgMS4xLTkuNCAyLjktMTkuMyA1LjEtMjkuNCAxOS42IDQuOCA0MSA4LjUgNjMuNSAxMC45IDEzLjUgMTguNSAyNy41IDM1LjMgNDEuNiA1MC0zMi42IDMwLjMtNjMuMiA0Ni45LTg0IDQ2LjktNC41LS4xLTguMy0xLTExLjMtMi43em0yMzcuMi03Ni4yYzQuNyAzOC4yLTEuMSA2Ny45LTE0LjYgNzUuOC0zIDEuOC02LjkgMi42LTExLjUgMi42LTIwLjcgMC01MS40LTE2LjUtODQtNDYuNiAxNC0xNC43IDI4LTMxLjQgNDEuMy00OS45IDIyLjYtMi40IDQ0LTYuMSA2My42LTExIDIuMyAxMC4xIDQuMSAxOS44IDUuMiAyOS4xem0zOC41LTY2LjdjLTguNiAzLjctMTggNy0yNy43IDEwLjEtNS43LTE5LjYtMTMuMi00MC0yMi41LTYwLjkgOS4yLTIwLjggMTYuNi00MS4xIDIyLjItNjAuNiA5LjkgMy4xIDE5LjMgNi41IDI4LjEgMTAuMiAzNS40IDE1LjEgNTguMyAzNC45IDU4LjMgNTAuNi0uMSAxNS43LTIzIDM1LjYtNTguNCA1MC42ek0zMjAuOCA3OC40eiIvPgogICAgPGNpcmNsZSBjeD0iNDIwLjkiIGN5PSIyOTYuNSIgcj0iNDUuNyIvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-redo: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGhlaWdodD0iMjQiIHZpZXdCb3g9IjAgMCAyNCAyNCIgd2lkdGg9IjE2Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMiIGZpbGw9IiM2MTYxNjEiPgogICAgICA8cGF0aCBkPSJNMCAwaDI0djI0SDB6IiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTE4LjQgMTAuNkMxNi41NSA4Ljk5IDE0LjE1IDggMTEuNSA4Yy00LjY1IDAtOC41OCAzLjAzLTkuOTYgNy4yMkwzLjkgMTZjMS4wNS0zLjE5IDQuMDUtNS41IDcuNi01LjUgMS45NSAwIDMuNzMuNzIgNS4xMiAxLjg4TDEzIDE2aDlWN2wtMy42IDMuNnoiLz4KICA8L2c+Cjwvc3ZnPgo=);
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
  --jp-icon-table-rows: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMSw4SDNWNGgxOFY4eiBNMjEsMTBIM3Y0aDE4VjEweiBNMjEsMTZIM3Y0aDE4VjE2eiIvPgogICAgPC9nPgo8L3N2Zz4=);
  --jp-icon-tag: url(data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMjgiIGhlaWdodD0iMjgiIHZpZXdCb3g9IjAgMCA0MyAyOCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KCTxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CgkJPHBhdGggZD0iTTI4LjgzMzIgMTIuMzM0TDMyLjk5OTggMTYuNTAwN0wzNy4xNjY1IDEyLjMzNEgyOC44MzMyWiIvPgoJCTxwYXRoIGQ9Ik0xNi4yMDk1IDIxLjYxMDRDMTUuNjg3MyAyMi4xMjk5IDE0Ljg0NDMgMjIuMTI5OSAxNC4zMjQ4IDIxLjYxMDRMNi45ODI5IDE0LjcyNDVDNi41NzI0IDE0LjMzOTQgNi4wODMxMyAxMy42MDk4IDYuMDQ3ODYgMTMuMDQ4MkM1Ljk1MzQ3IDExLjUyODggNi4wMjAwMiA4LjYxOTQ0IDYuMDY2MjEgNy4wNzY5NUM2LjA4MjgxIDYuNTE0NzcgNi41NTU0OCA2LjA0MzQ3IDcuMTE4MDQgNi4wMzA1NUM5LjA4ODYzIDUuOTg0NzMgMTMuMjYzOCA1LjkzNTc5IDEzLjY1MTggNi4zMjQyNUwyMS43MzY5IDEzLjYzOUMyMi4yNTYgMTQuMTU4NSAyMS43ODUxIDE1LjQ3MjQgMjEuMjYyIDE1Ljk5NDZMMTYuMjA5NSAyMS42MTA0Wk05Ljc3NTg1IDguMjY1QzkuMzM1NTEgNy44MjU2NiA4LjYyMzUxIDcuODI1NjYgOC4xODI4IDguMjY1QzcuNzQzNDYgOC43MDU3MSA3Ljc0MzQ2IDkuNDE3MzMgOC4xODI4IDkuODU2NjdDOC42MjM4MiAxMC4yOTY0IDkuMzM1ODIgMTAuMjk2NCA5Ljc3NTg1IDkuODU2NjdDMTAuMjE1NiA5LjQxNzMzIDEwLjIxNTYgOC43MDUzMyA5Ljc3NTg1IDguMjY1WiIvPgoJPC9nPgo8L3N2Zz4K);
  --jp-icon-terminal: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0IiA+CiAgICA8cmVjdCBjbGFzcz0ianAtaWNvbjIganAtaWNvbi1zZWxlY3RhYmxlIiB3aWR0aD0iMjAiIGhlaWdodD0iMjAiIHRyYW5zZm9ybT0idHJhbnNsYXRlKDIgMikiIGZpbGw9IiMzMzMzMzMiLz4KICAgIDxwYXRoIGNsYXNzPSJqcC1pY29uLWFjY2VudDIganAtaWNvbi1zZWxlY3RhYmxlLWludmVyc2UiIGQ9Ik01LjA1NjY0IDguNzYxNzJDNS4wNTY2NCA4LjU5NzY2IDUuMDMxMjUgOC40NTMxMiA0Ljk4MDQ3IDguMzI4MTJDNC45MzM1OSA4LjE5OTIyIDQuODU1NDcgOC4wODIwMyA0Ljc0NjA5IDcuOTc2NTZDNC42NDA2MiA3Ljg3MTA5IDQuNSA3Ljc3NTM5IDQuMzI0MjIgNy42ODk0NUM0LjE1MjM0IDcuNTk5NjEgMy45NDMzNiA3LjUxMTcyIDMuNjk3MjcgNy40MjU3OEMzLjMwMjczIDcuMjg1MTYgMi45NDMzNiA3LjEzNjcyIDIuNjE5MTQgNi45ODA0N0MyLjI5NDkyIDYuODI0MjIgMi4wMTc1OCA2LjY0MjU4IDEuNzg3MTEgNi40MzU1NUMxLjU2MDU1IDYuMjI4NTIgMS4zODQ3NyA1Ljk4ODI4IDEuMjU5NzcgNS43MTQ4NEMxLjEzNDc3IDUuNDM3NSAxLjA3MjI3IDUuMTA5MzggMS4wNzIyNyA0LjczMDQ3QzEuMDcyMjcgNC4zOTg0NCAxLjEyODkxIDQuMDk1NyAxLjI0MjE5IDMuODIyMjdDMS4zNTU0NyAzLjU0NDkyIDEuNTE1NjIgMy4zMDQ2OSAxLjcyMjY2IDMuMTAxNTZDMS45Mjk2OSAyLjg5ODQ0IDIuMTc5NjkgMi43MzQzNyAyLjQ3MjY2IDIuNjA5MzhDMi43NjU2MiAyLjQ4NDM4IDMuMDkxOCAyLjQwNDMgMy40NTExNyAyLjM2OTE0VjEuMTA5MzhINC4zODg2N1YyLjM4MDg2QzQuNzQwMjMgMi40Mjc3MyA1LjA1NjY0IDIuNTIzNDQgNS4zMzc4OSAyLjY2Nzk3QzUuNjE5MTQgMi44MTI1IDUuODU3NDIgMy4wMDE5NSA2LjA1MjczIDMuMjM2MzNDNi4yNTE5NSAzLjQ2NjggNi40MDQzIDMuNzQwMjMgNi41MDk3NyA0LjA1NjY0QzYuNjE5MTQgNC4zNjkxNCA2LjY3MzgzIDQuNzIwNyA2LjY3MzgzIDUuMTExMzNINS4wNDQ5MkM1LjA0NDkyIDQuNjM4NjcgNC45Mzc1IDQuMjgxMjUgNC43MjI2NiA0LjAzOTA2QzQuNTA3ODEgMy43OTI5NyA0LjIxNjggMy42Njk5MiAzLjg0OTYxIDMuNjY5OTJDMy42NTAzOSAzLjY2OTkyIDMuNDc2NTYgMy42OTcyNyAzLjMyODEyIDMuNzUxOTVDMy4xODM1OSAzLjgwMjczIDMuMDY0NDUgMy44NzY5NSAyLjk3MDcgMy45NzQ2MUMyLjg3Njk1IDQuMDY4MzYgMi44MDY2NCA0LjE3OTY5IDIuNzU5NzcgNC4zMDg1OUMyLjcxNjggNC40Mzc1IDIuNjk1MzEgNC41NzgxMiAyLjY5NTMxIDQuNzMwNDdDMi42OTUzMSA0Ljg4MjgxIDIuNzE2OCA1LjAxOTUzIDIuNzU5NzcgNS4xNDA2MkMyLjgwNjY0IDUuMjU3ODEgMi44ODI4MSA1LjM2NzE5IDIuOTg4MjggNS40Njg3NUMzLjA5NzY2IDUuNTcwMzEgMy4yNDAyMyA1LjY2Nzk3IDMuNDE2MDIgNS43NjE3MkMzLjU5MTggNS44NTE1NiAzLjgxMDU1IDUuOTQzMzYgNC4wNzIyNyA2LjAzNzExQzQuNDY2OCA2LjE4NTU1IDQuODI0MjIgNi4zMzk4NCA1LjE0NDUzIDYuNUM1LjQ2NDg0IDYuNjU2MjUgNS43MzgyOCA2LjgzOTg0IDUuOTY0ODQgNy4wNTA3OEM2LjE5NTMxIDcuMjU3ODEgNi4zNzEwOSA3LjUgNi40OTIxOSA3Ljc3NzM0QzYuNjE3MTkgOC4wNTA3OCA2LjY3OTY5IDguMzc1IDYuNjc5NjkgOC43NUM2LjY3OTY5IDkuMDkzNzUgNi42MjMwNSA5LjQwNDMgNi41MDk3NyA5LjY4MTY0QzYuMzk2NDggOS45NTUwOCA2LjIzNDM4IDEwLjE5MTQgNi4wMjM0NCAxMC4zOTA2QzUuODEyNSAxMC41ODk4IDUuNTU4NTkgMTAuNzUgNS4yNjE3MiAxMC44NzExQzQuOTY0ODQgMTAuOTg4MyA0LjYzMjgxIDExLjA2NDUgNC4yNjU2MiAxMS4wOTk2VjEyLjI0OEgzLjMzMzk4VjExLjA5OTZDMy4wMDE5NSAxMS4wNjg0IDIuNjc5NjkgMTAuOTk2MSAyLjM2NzE5IDEwLjg4MjhDMi4wNTQ2OSAxMC43NjU2IDEuNzc3MzQgMTAuNTk3NyAxLjUzNTE2IDEwLjM3ODlDMS4yOTY4OCAxMC4xNjAyIDEuMTA1NDcgOS44ODQ3NyAwLjk2MDkzOCA5LjU1MjczQzAuODE2NDA2IDkuMjE2OCAwLjc0NDE0MSA4LjgxNDQ1IDAuNzQ0MTQxIDguMzQ1N0gyLjM3ODkxQzIuMzc4OTEgOC42MjY5NSAyLjQxOTkyIDguODYzMjggMi41MDE5NSA5LjA1NDY5QzIuNTgzOTggOS4yNDIxOSAyLjY4OTQ1IDkuMzkyNTggMi44MTgzNiA5LjUwNTg2QzIuOTUxMTcgOS42MTUyMyAzLjEwMTU2IDkuNjkzMzYgMy4yNjk1MyA5Ljc0MDIzQzMuNDM3NSA5Ljc4NzExIDMuNjA5MzggOS44MTA1NSAzLjc4NTE2IDkuODEwNTVDNC4yMDMxMiA5LjgxMDU1IDQuNTE5NTMgOS43MTI4OSA0LjczNDM4IDkuNTE3NThDNC45NDkyMiA5LjMyMjI3IDUuMDU2NjQgOS4wNzAzMSA1LjA1NjY0IDguNzYxNzJaTTEzLjQxOCAxMi4yNzE1SDguMDc0MjJWMTFIMTMuNDE4VjEyLjI3MTVaIiB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzLjk1MjY0IDYpIiBmaWxsPSJ3aGl0ZSIvPgo8L3N2Zz4K);
  --jp-icon-text-editor: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNiIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8cGF0aCBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIiBkPSJNMTUgMTVIM3YyaDEydi0yem0wLThIM3YyaDEyVjd6TTMgMTNoMTh2LTJIM3Yyem0wIDhoMTh2LTJIM3Yyek0zIDN2MmgxOFYzSDN6Ii8+Cjwvc3ZnPgo=);
  --jp-icon-toc: url(data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4KICA8ZyBjbGFzcz0ianAtaWNvbjMganAtaWNvbi1zZWxlY3RhYmxlIiBmaWxsPSIjNjE2MTYxIj4KICAgIDxwYXRoIGQ9Ik03LDVIMjFWN0g3VjVNNywxM1YxMUgyMVYxM0g3TTQsNC41QTEuNSwxLjUgMCAwLDEgNS41LDZBMS41LDEuNSAwIDAsMSA0LDcuNUExLjUsMS41IDAgMCwxIDIuNSw2QTEuNSwxLjUgMCAwLDEgNCw0LjVNNCwxMC41QTEuNSwxLjUgMCAwLDEgNS41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMy41QTEuNSwxLjUgMCAwLDEgMi41LDEyQTEuNSwxLjUgMCAwLDEgNCwxMC41TTcsMTlWMTdIMjFWMTlIN000LDE2LjVBMS41LDEuNSAwIDAsMSA1LjUsMThBMS41LDEuNSAwIDAsMSA0LDE5LjVBMS41LDEuNSAwIDAsMSAyLjUsMThBMS41LDEuNSAwIDAsMSA0LDE2LjVaIiAvPgogIDwvZz4KPC9zdmc+Cg==);
  --jp-icon-tree-view: url(data:image/svg+xml;base64,PHN2ZyBoZWlnaHQ9IjI0IiB2aWV3Qm94PSIwIDAgMjQgMjQiIHdpZHRoPSIyNCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KICAgIDxnIGNsYXNzPSJqcC1pY29uMyIgZmlsbD0iIzYxNjE2MSI+CiAgICAgICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPgogICAgICAgIDxwYXRoIGQ9Ik0yMiAxMVYzaC03djNIOVYzSDJ2OGg3VjhoMnYxMGg0djNoN3YtOGgtN3YzaC0yVjhoMnYzeiIvPgogICAgPC9nPgo8L3N2Zz4=);
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
.jp-CodeIcon {
  background-image: var(--jp-icon-code);
}
.jp-ConsoleIcon {
  background-image: var(--jp-icon-console);
}
.jp-CopyIcon {
  background-image: var(--jp-icon-copy);
}
.jp-CopyrightIcon {
  background-image: var(--jp-icon-copyright);
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
.jp-JuliaIcon {
  background-image: var(--jp-icon-julia);
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
.jp-NumberingIcon {
  background-image: var(--jp-icon-numbering);
}
.jp-OfflineBoltIcon {
  background-image: var(--jp-icon-offline-bolt);
}
.jp-PaletteIcon {
  background-image: var(--jp-icon-palette);
}
.jp-PasteIcon {
  background-image: var(--jp-icon-paste);
}
.jp-PdfIcon {
  background-image: var(--jp-icon-pdf);
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
.jp-RedoIcon {
  background-image: var(--jp-icon-redo);
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
.jp-TableRowsIcon {
  background-image: var(--jp-icon-table-rows);
}
.jp-TagIcon {
  background-image: var(--jp-icon-tag);
}
.jp-TerminalIcon {
  background-image: var(--jp-icon-terminal);
}
.jp-TextEditorIcon {
  background-image: var(--jp-icon-text-editor);
}
.jp-TocIcon {
  background-image: var(--jp-icon-toc);
}
.jp-TreeViewIcon {
  background-image: var(--jp-icon-tree-view);
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

.jp-switch {
  display: flex;
  align-items: center;
  padding-left: 4px;
  padding-right: 4px;
  font-size: var(--jp-ui-font-size1);
  background-color: transparent;
  color: var(--jp-ui-font-color1);
  border: none;
  height: 20px;
}

.jp-switch:hover {
  background-color: var(--jp-layout-color2);
}

.jp-switch-label {
  margin-right: 5px;
}

.jp-switch-track {
  cursor: pointer;
  background-color: var(--jp-border-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 34px;
  height: 16px;
  width: 35px;
  position: relative;
}

.jp-switch-track::before {
  content: '';
  position: absolute;
  height: 10px;
  width: 10px;
  margin: 3px;
  left: 0px;
  background-color: var(--jp-ui-inverse-font-color1);
  -webkit-transition: 0.4s;
  transition: 0.4s;
  border-radius: 50%;
}

.jp-switch[aria-checked='true'] .jp-switch-track {
  background-color: var(--jp-warn-color0);
}

.jp-switch[aria-checked='true'] .jp-switch-track::before {
  /* track width (35) - margins (3 + 3) - thumb width (10) */
  left: 19px;
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
| Modal variant
|----------------------------------------------------------------------------*/

.jp-ModalCommandPalette {
  position: absolute;
  z-index: 10000;
  top: 38px;
  left: 30%;
  margin: 0;
  padding: 4px;
  width: 40%;
  box-shadow: var(--jp-elevation-z4);
  border-radius: 4px;
  background: var(--jp-layout-color0);
}

.jp-ModalCommandPalette .lm-CommandPalette {
  max-height: 40vh;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-close-icon::after {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-header {
  display: none;
}

.jp-ModalCommandPalette .lm-CommandPalette .lm-CommandPalette-item {
  margin-left: 4px;
  margin-right: 4px;
}

.jp-ModalCommandPalette
  .lm-CommandPalette
  .lm-CommandPalette-item.lm-mod-disabled {
  display: none;
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

.jp-SearchIconGroup {
  color: white;
  background-color: var(--jp-brand-color1);
  position: absolute;
  top: 4px;
  right: 4px;
  padding: 5px 5px 1px 5px;
}

.jp-SearchIconGroup svg {
  height: 20px;
  width: 20px;
}

.jp-SearchIconGroup .jp-icon3[fill] {
  fill: var(--jp-layout-color0);
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
  color: var(--jp-ui-font-color2);
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
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item.lm-mod-active {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active .jp-icon-selectable[fill] {
  fill: var(--jp-layout-color0);
}

.lm-CommandPalette-item.lm-mod-active .lm-CommandPalette-itemLabel > mark {
  color: var(--jp-ui-inverse-font-color0);
}

.lm-CommandPalette-item.lm-mod-active:hover:not(.lm-mod-disabled) {
  color: var(--jp-ui-inverse-font-color1);
  background: var(--jp-brand-color1);
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
  color: var(--jp-ui-font-color2);
}

.lm-CommandPalette-item .lm-CommandPalette-itemIcon {
  margin: 0 4px 0 0;
  position: relative;
  width: 16px;
  top: 2px;
  flex: 0 0 auto;
}

.lm-CommandPalette-item.lm-mod-disabled .lm-CommandPalette-itemIcon {
  opacity: 0.6;
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
  resize: both;
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

button.jp-Dialog-close-button {
  padding: 0;
  height: 100%;
  min-width: unset;
  min-height: unset;
}

.jp-Dialog-header {
  display: flex;
  justify-content: space-between;
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

.jp-Input-Boolean-Dialog {
  flex-direction: row-reverse;
  align-items: end;
  width: 100%;
}

.jp-Input-Boolean-Dialog > label {
  flex: 1 1 auto;
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

input[type='checkbox'].jp-mod-styled {
  appearance: checkbox;
  -webkit-appearance: checkbox;
  -moz-appearance: checkbox;
  height: auto;
}

input.jp-mod-styled:focus {
  border: var(--jp-border-width) solid var(--md-blue-500);
  box-shadow: inset 0 0 4px var(--md-blue-300);
}

.jp-FileDialog-Checkbox {
  margin-top: 35px;
  display: flex;
  flex-direction: row;
  align-items: end;
  width: 100%;
}

.jp-FileDialog-Checkbox > label {
  flex: 1 1 auto;
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
  overflow-x: auto;
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

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar.jp-Toolbar-micro {
  padding: 0;
  min-height: 0;
}

#jp-main-dock-panel[data-mode='single-document']
  .jp-MainAreaWidget
  > .jp-Toolbar {
  border: none;
  box-shadow: none;
}

/*-----------------------------------------------------------------------------
| Copyright (c) 2014-2017, Jupyter Development Team.
|
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

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
  /* 50px is the magic margin used to hide the element's real scrollbars */
  /* See overflow: hidden in .CodeMirror */
  margin-bottom: -50px; margin-right: -50px;
  padding-bottom: 50px;
  height: 100%;
  outline: none; /* Prevent dragging from highlighting the element */
  position: relative;
}
.CodeMirror-sizer {
  position: relative;
  border-right: 50px solid transparent;
}

/* The fake, visible scrollbars. Used to force redraw during scrolling
   before actual scrolling happens, thus preventing shaking and
   flickering artifacts. */
.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  position: absolute;
  z-index: 6;
  display: none;
  outline: none;
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
  margin-bottom: -50px;
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

.jp-CodeMirrorEditor {
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

/* Styles for shared cursors (remote cursor locations and selected ranges) */
.jp-CodeMirrorEditor .remote-caret {
  position: relative;
  border-left: 2px solid black;
  margin-left: -1px;
  margin-right: -1px;
  box-sizing: border-box;
}

.jp-CodeMirrorEditor .remote-caret > div {
  white-space: nowrap;
  position: absolute;
  top: -1.15em;
  padding-bottom: 0.05em;
  left: -2px;
  font-size: 0.95em;
  background-color: rgb(250, 129, 0);
  font-family: var(--jp-ui-font-family);
  font-weight: bold;
  line-height: normal;
  user-select: none;
  color: white;
  padding-left: 2px;
  padding-right: 2px;
  z-index: 3;
  transition: opacity 0.3s ease-in-out;
}

.jp-CodeMirrorEditor .remote-caret.hide-name > div {
  transition-delay: 0.7s;
  opacity: 0;
}

.jp-CodeMirrorEditor .remote-caret:hover > div {
  opacity: 1;
  transition-delay: 0s;
}

/*-----------------------------------------------------------------------------
| Copyright (c) Jupyter Development Team.
| Distributed under the terms of the Modified BSD License.
|----------------------------------------------------------------------------*/

/*-----------------------------------------------------------------------------
| RenderedText
|----------------------------------------------------------------------------*/

:root {
  /* This is the padding value to fill the gaps between lines containing spans with background color. */
  --jp-private-code-span-padding: calc(
    (var(--jp-code-line-height) - 1) * var(--jp-code-font-size) / 2
  );
}

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
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-red-bg {
  background-color: #e75c58;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-green-bg {
  background-color: #00a250;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-yellow-bg {
  background-color: #ddb62b;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-blue-bg {
  background-color: #208ffb;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-magenta-bg {
  background-color: #d160c4;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-cyan-bg {
  background-color: #60c6c8;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-white-bg {
  background-color: #c5c1b4;
  padding: var(--jp-private-code-span-padding) 0;
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
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-red-intense-bg {
  background-color: #b22b31;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-green-intense-bg {
  background-color: #007427;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-yellow-intense-bg {
  background-color: #b27d12;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-blue-intense-bg {
  background-color: #0065ca;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-magenta-intense-bg {
  background-color: #a03196;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-cyan-intense-bg {
  background-color: #258f8f;
  padding: var(--jp-private-code-span-padding) 0;
}
.jp-RenderedText pre .ansi-white-intense-bg {
  background-color: #a1a6b2;
  padding: var(--jp-private-code-span-padding) 0;
}

.jp-RenderedText pre .ansi-default-inverse-fg {
  color: var(--jp-ui-inverse-font-color0);
}
.jp-RenderedText pre .ansi-default-inverse-bg {
  background-color: var(--jp-inverse-layout-color0);
  padding: var(--jp-private-code-span-padding) 0;
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

.jp-MimeDocument {
  outline: none;
}

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
  margin: 8px 12px 8px 12px;
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
  margin: 8px 12px 0px 12px;
}

.jp-FileBrowser-toolbar.jp-Toolbar {
  justify-content: flex-start;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-Toolbar-item {
  flex: 0 0 auto;
  padding-left: 0px;
  padding-right: 2px;
}

.jp-FileBrowser-toolbar.jp-Toolbar .jp-ToolbarButtonComponent {
  width: 40px;
}

.jp-FileBrowser-toolbar.jp-Toolbar
  .jp-Toolbar-item:first-child
  .jp-ToolbarButtonComponent {
  width: 72px;
  background: var(--jp-brand-color1);
}

.jp-FileBrowser-toolbar.jp-Toolbar
  .jp-Toolbar-item:first-child
  .jp-ToolbarButtonComponent:focus-visible {
  background-color: var(--jp-brand-color0);
}

.jp-FileBrowser-toolbar.jp-Toolbar
  .jp-Toolbar-item:first-child
  .jp-ToolbarButtonComponent
  .jp-icon3 {
  fill: white;
}

/*-----------------------------------------------------------------------------
| Other styles
|----------------------------------------------------------------------------*/

.jp-FileDialog.jp-mod-conflict input {
  color: var(--jp-error-color1);
}

.jp-FileDialog .jp-new-name-title {
  margin-top: 12px;
}

.jp-LastModified-hidden {
  display: none;
}

.jp-FileBrowser-filterBox {
  padding: 0px;
  flex: 0 0 auto;
  margin: 8px 12px 0px 12px;
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

.jp-DirListing:focus-visible {
  border: 1px solid var(--jp-brand-color1);
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

.jp-id-narrow {
  display: none;
  flex: 0 0 5px;
  padding: 4px 4px;
  border-left: var(--jp-border-width) solid var(--jp-border-color2);
  text-align: right;
  color: var(--jp-border-color2);
}

.jp-DirListing-narrow .jp-id-narrow {
  display: block;
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

.jp-DirListing-content mark {
  color: var(--jp-ui-font-color0);
  background-color: transparent;
  font-weight: bold;
}

.jp-DirListing-content .jp-DirListing-item.jp-mod-selected mark {
  color: var(--jp-ui-inverse-font-color0);
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

.jp-DirListing-item[data-is-dot] {
  opacity: 75%;
}

.jp-DirListing-item.jp-mod-selected {
  color: var(--jp-ui-inverse-font-color1);
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
  color: var(--jp-success-color1);
  content: '\25CF';
  font-size: 8px;
  position: absolute;
  left: -8px;
}

.jp-DirListing-item.jp-mod-running.jp-mod-selected
  .jp-DirListing-itemIcon:before {
  color: var(--jp-ui-inverse-font-color1);
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

body[data-format='mobile'] .jp-OutputArea-child {
  flex-direction: column;
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

body[data-format='mobile'] .jp-OutputPrompt {
  flex: 0 0 auto;
  text-align: left;
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

body[data-format='mobile'] .jp-OutputArea-child .jp-OutputArea-output {
  margin-left: var(--jp-notebook-padding);
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

/* Text output with the Out[] prompt needs a top padding to match the
 * alignment of the Out[] prompt itself.
 */
.jp-OutputArea-executeResult .jp-RenderedText.jp-OutputArea-output {
  padding-top: var(--jp-code-padding);
  border-top: var(--jp-border-width) solid transparent;
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
  overflow: hidden;
}

body[data-format='mobile'] .jp-InputArea {
  flex-direction: column;
}

.jp-InputArea-editor {
  flex: 1 1 auto;
  overflow: hidden;
}

.jp-InputArea-editor {
  /* This is the non-active, default styling */
  border: var(--jp-border-width) solid var(--jp-cell-editor-border-color);
  border-radius: 0px;
  background: var(--jp-cell-editor-background);
}

body[data-format='mobile'] .jp-InputArea-editor {
  margin-left: var(--jp-notebook-padding);
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

body[data-format='mobile'] .jp-InputPrompt {
  flex: 0 0 auto;
  text-align: left;
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

.jp-showHiddenCellsButton {
  margin-left: calc(var(--jp-cell-prompt-width) + 2 * var(--jp-code-padding));
  margin-top: var(--jp-code-padding);
  border: 1px solid var(--jp-border-color2);
  background-color: var(--jp-border-color3) !important;
  color: var(--jp-content-font-color0) !important;
}

.jp-showHiddenCellsButton:hover {
  background-color: var(--jp-border-color2) !important;
}

.jp-collapseHeadingButton {
  display: none;
}

.jp-MarkdownCell:hover .jp-collapseHeadingButton {
  display: flex;
  min-height: var(--jp-cell-collapser-min-height);
  position: absolute;
  right: 0;
  top: 0;
  bottom: 0;
}

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

.jp-MainAreaWidget-ContainStrict .jp-Notebook * {
  contain: strict;
}

.jp-Notebook-render * {
  contain: none !important;
}

.jp-Notebook .jp-Cell {
  overflow: visible;
}

.jp-Notebook .jp-Cell .jp-InputPrompt {
  cursor: move;
  float: left;
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

/* cell is dirty */
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt {
  color: var(--jp-warn-color1);
}
.jp-Notebook .jp-Cell.jp-mod-dirty .jp-InputPrompt:before {
  color: var(--jp-warn-color1);
  content: '•';
}

.jp-Notebook .jp-Cell.jp-mod-active.jp-mod-dirty .jp-Collapser {
  background: var(--jp-warn-color1);
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
  display: block;
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

.jp-NotebookTools .jp-select-wrapper {
  margin-top: 4px;
  margin-bottom: 0px;
}

.jp-NotebookTools .jp-Collapse {
  margin-top: 16px;
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
| Placeholder
|----------------------------------------------------------------------------*/

.jp-Cell-Placeholder {
  padding-left: 55px;
}

.jp-Cell-Placeholder-wrapper {
  background: #fff;
  border: 1px solid;
  border-color: #e5e6e9 #dfe0e4 #d0d1d5;
  border-radius: 4px;
  -webkit-border-radius: 4px;
  margin: 10px 15px;
}

.jp-Cell-Placeholder-wrapper-inner {
  padding: 15px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body {
  background-repeat: repeat;
  background-size: 50% auto;
}

.jp-Cell-Placeholder-wrapper-body div {
  background: #f6f7f8;
  background-image: -webkit-linear-gradient(
    left,
    #f6f7f8 0%,
    #edeef1 20%,
    #f6f7f8 40%,
    #f6f7f8 100%
  );
  background-repeat: no-repeat;
  background-size: 800px 104px;
  height: 104px;
  position: relative;
}

.jp-Cell-Placeholder-wrapper-body div {
  position: absolute;
  right: 15px;
  left: 15px;
  top: 15px;
}

div.jp-Cell-Placeholder-h1 {
  top: 20px;
  height: 20px;
  left: 15px;
  width: 150px;
}

div.jp-Cell-Placeholder-h2 {
  left: 15px;
  top: 50px;
  height: 10px;
  width: 100px;
}

div.jp-Cell-Placeholder-content-1,
div.jp-Cell-Placeholder-content-2,
div.jp-Cell-Placeholder-content-3 {
  left: 15px;
  right: 15px;
  height: 10px;
}

div.jp-Cell-Placeholder-content-1 {
  top: 100px;
}

div.jp-Cell-Placeholder-content-2 {
  top: 120px;
}

div.jp-Cell-Placeholder-content-3 {
  top: 140px;
}

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

  --jp-brand-color0: var(--md-blue-900);
  --jp-brand-color1: var(--md-blue-700);
  --jp-brand-color2: var(--md-blue-300);
  --jp-brand-color3: var(--md-blue-100);
  --jp-brand-color4: var(--md-blue-50);

  --jp-accent-color0: var(--md-green-900);
  --jp-accent-color1: var(--md-green-700);
  --jp-accent-color2: var(--md-green-300);
  --jp-accent-color3: var(--md-green-100);

  /* State colors (warn, error, success, info) */

  --jp-warn-color0: var(--md-orange-900);
  --jp-warn-color1: var(--md-orange-700);
  --jp-warn-color2: var(--md-orange-300);
  --jp-warn-color3: var(--md-orange-100);

  --jp-error-color0: var(--md-red-900);
  --jp-error-color1: var(--md-red-700);
  --jp-error-color2: var(--md-red-300);
  --jp-error-color3: var(--md-red-100);

  --jp-success-color0: var(--md-green-900);
  --jp-success-color1: var(--md-green-700);
  --jp-success-color2: var(--md-green-300);
  --jp-success-color3: var(--md-green-100);

  --jp-info-color0: var(--md-cyan-900);
  --jp-info-color1: var(--md-cyan-700);
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
  --jp-cell-prompt-font-family: var(--jp-code-font-family-default);
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

  /* Statusbar specific styles */

  --jp-statusbar-height: 24px;

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

  --jp-sidebar-min-width: 250px;

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
/* Force rendering true colors when outputing to pdf */
* {
  -webkit-print-color-adjust: exact;
}

/* Misc */
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

.CodeMirror pre {
  margin: 0;
  padding: 0;
}

/* Using table instead of flexbox so that we can use break-inside property */
/* CSS rules under this comment should not be required anymore after we move to the JupyterLab 4.0 CSS */


.jp-CodeCell.jp-mod-outputsScrolled .jp-OutputArea-prompt {
  min-width: calc(
    var(--jp-cell-prompt-width) - var(--jp-private-cell-scrolling-output-offset)
  );
}

.jp-OutputArea-child {
  display: table;
  width: 100%;
}

.jp-OutputPrompt {
  display: table-cell;
  vertical-align: top;
  min-width: var(--jp-cell-prompt-width);
}

body[data-format='mobile'] .jp-OutputPrompt {
  display: table-row;
}

.jp-OutputArea-output {
  display: table-cell;
  width: 100%;
}

body[data-format='mobile'] .jp-OutputArea-child .jp-OutputArea-output {
  display: table-row;
}

.jp-OutputArea-output.jp-OutputArea-executeResult {
  width: 100%;
}

/* Hiding the collapser by default */
.jp-Collapser {
  display: none;
}

@media print {
  .jp-Cell-inputWrapper,
  .jp-Cell-outputWrapper {
    display: block;
  }

  .jp-OutputArea-child {
    break-inside: avoid-page;
  }
}
</style>

<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/latest.js?config=TeX-AMS_CHTML-full,Safe"> </script>
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
                }
            });

            MathJax.Hub.Queue(["Typeset", MathJax.Hub]);
        }
    }
    init_mathjax();
    </script>
    <!-- End of mathjax configuration --></head>
<body class="jp-Notebook" data-jp-theme-light="true" data-jp-theme-name="JupyterLab Light">

<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="The-Most-Famous-Musicians-You've-Never-Heard-of">The Most Famous Musicians You've Never Heard of<a class="anchor-link" href="#The-Most-Famous-Musicians-You've-Never-Heard-of">&#182;</a></h1><p>By Sarah Helmbrecht and JT McDermott</p>
<p><a href="https://skhelmbrecht.github.io/datasciencefinal">https://skhelmbrecht.github.io/datasciencefinal</a></p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h2 id="I.-Introduction"><strong>I. Introduction</strong><a class="anchor-link" href="#I.-Introduction">&#182;</a></h2>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>With the advent of music streaming services such as Spotify, Apple Music, and others, it has never been easier to discover new music and artists than it is today. Despite the overall trend towards globalization and unprecedented access to historic catalogs, music tastes are still largely stratified by demographics. This inspired our question: <strong>who are the most famous artists and bands that we have never heard of?</strong></p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="An-Example:-Cultural-Disparities"><strong>An Example: Cultural Disparities</strong><a class="anchor-link" href="#An-Example:-Cultural-Disparities">&#182;</a></h4><p>Do you recognize the person in this artist? If you aren't from India, probably not. This is King, one of the most popular artists in India, gaining more than 17 million streams this week alone. He's one of many examples of a popular artist that is relatively unknown outside of their primary target audience, in this case based on nationality and language.</p>
<p><img src="data:image/jpeg;base64,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" alt="King.jpg"></p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Context"><strong>Context</strong><a class="anchor-link" href="#Context">&#182;</a></h4><p>To understand our approach to answering this question, it helps to understand the perspective of us, the authors. We are both Gen-Z college students that were raised in the United States and primarily speak English.</p>
<p>The main factors that might hide an otherwise popular artist from us are language, geography, time, and our own personal preferences. Language and geography are simple to understand; people are generally unlikely to be exposed to media in a language they don't speak from a foreign country. This is increasingly changing with the advent of the international stars like Bad Bunny and others, but there are still many artists hidden from the rest of the world behind cultural barriers.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Motivation"><strong>Motivation</strong><a class="anchor-link" href="#Motivation">&#182;</a></h4><p>The initial motivation for this study was pure curiosity, stemming from a desire to better understand the world and the people who live in it. There are practical motivations as well, namely:</p>
<ol>
<li>Identifying potential partners for advertisers</li>
<li>Understanding global trends in media and entertainment</li>
</ol>
<p>Celebrity endorsements continue to be a major tool for advertisers, and can dramatically improve the ethos of a company when trying to penetrate a new market. Knowledge of famous musicians and particularly where and why they are famous is important for a successful partnership. For creators and producers of music, understanding trends and expanding horizons invites new influences, new ideas, and ultimately a better end product.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Our-Model"><strong>Our Model</strong><a class="anchor-link" href="#Our-Model">&#182;</a></h4><p>In our exploration, we decided use our data to relate international trends in musician popularity to understand domestic trends. Using streaming data from dozens of countries, our model captures which countries are the best predictors of an artist's fame among US Millenials.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="II.-Our-Data">II. Our Data<a class="anchor-link" href="#II.-Our-Data">&#182;</a></h1><p>The rise of the internet and ubiquity of streaming services has created vast amounts of data about music habits. For our analysis, we focused on data that relates demographic factors to listening patterns. Our data comes from three main sources:</p>
<ul>
<li><a href="https://kworb.net/spotify/">Spotify</a> (via Kworb) - data of top 200 streamed artistis in countries around the world</li>
<li><a href="https://today.yougov.com/ratings/entertainment/popularity/all-time-music-artists/millennials">YouGov</a> - polling of Millenials regarding their familiarity with 200 popular artists</li>
<li><a href="http://www.acclaimedmusic.net/">Acclaimed Music</a> - Collection of top 1000 artists of all time and decade-by-decade data of their releases</li>
</ul>
<p>The importation of this data was done primarily with webscraping. We explain in more detail the unique challenges each data set presented below.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="III.-ETL-&amp;-EDA"><strong>III. ETL &amp; EDA</strong><a class="anchor-link" href="#III.-ETL-&amp;-EDA">&#182;</a></h1>
</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#Mount Google Drive and move into correct directory</span>
<span class="kn">from</span> <span class="nn">google.colab</span> <span class="kn">import</span> <span class="n">drive</span>
<span class="n">drive</span><span class="o">.</span><span class="n">mount</span><span class="p">(</span><span class="s1">'/content/drive'</span><span class="p">)</span>
<span class="o">%</span><span class="n">cd</span> <span class="o">/</span><span class="n">content</span><span class="o">/</span><span class="n">drive</span><span class="o">/</span><span class="n">MyDrive</span><span class="o">/</span><span class="n">cmps3160</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Drive already mounted at /content/drive; to attempt to forcibly remount, call drive.mount(&#34;/content/drive&#34;, force_remount=True).
/content/drive/MyDrive/cmps3160
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Tools-for-Analysis"><strong>Tools for Analysis</strong><a class="anchor-link" href="#Tools-for-Analysis">&#182;</a></h4><p>This section will keep track of the tools we will use for our analysis, namely imported Python libraries.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#This cell imports libraries for analysis</span>

<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">from</span> <span class="nn">bs4</span> <span class="kn">import</span> <span class="n">BeautifulSoup</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">import</span> <span class="nn">requests</span>
<span class="kn">import</span> <span class="nn">re</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="YouGov-Music-Artists-Poll"><strong>YouGov Music Artists Poll</strong><a class="anchor-link" href="#YouGov-Music-Artists-Poll">&#182;</a></h3><p>The following section will use a national poll to identify what percentage of American millenials have heard of certain musical artists.</p>
<p>The dataset, sourced from <a href="https://today.yougov.com/ratings/entertainment/fame/contemporary-music-artists/millennials">YouGov</a>, ranks artists by the percentage of people polled (born from 1949 to 1999) who have heard of them, as of 2022. This website is particularly difficult to scrape because it has a "Load More" button and does not store the data in tabular format. We typed the data into an Excel spreadsheet instead of scraping it.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="err">!</span><span class="n">pwd</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>/content/drive/MyDrive/cmps3160
</pre>
</div>
</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#Read and display YouGov data from Excel spreadsheet</span>
<span class="n">df_yougov</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_excel</span><span class="p">(</span><span class="s2">"/content/drive/MyDrive/cmps3160/yougovdata.xlsx"</span><span class="p">)</span>
<span class="n">df_yougov</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-ee47fffb-8a71-468b-be81-12dfc4aaa13e">
    <div class="colab-df-container">
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
      <th>Name</th>
      <th>Fame</th>
      <th>Popularity</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Adele</td>
      <td>98</td>
      <td>70</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Selena Gomez</td>
      <td>98</td>
      <td>62</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Katy Perry</td>
      <td>97</td>
      <td>59</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Rihanna</td>
      <td>96</td>
      <td>61</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Billie Eilish</td>
      <td>96</td>
      <td>58</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>245</th>
      <td>Chris Stapleton</td>
      <td>59</td>
      <td>37</td>
    </tr>
    <tr>
      <th>246</th>
      <td>Tiesto</td>
      <td>59</td>
      <td>36</td>
    </tr>
    <tr>
      <th>247</th>
      <td>The 1975</td>
      <td>59</td>
      <td>36</td>
    </tr>
    <tr>
      <th>248</th>
      <td>Greta Van Fleet</td>
      <td>59</td>
      <td>31</td>
    </tr>
    <tr>
      <th>249</th>
      <td>Neon Trees</td>
      <td>59</td>
      <td>37</td>
    </tr>
  </tbody>
</table>
<p>250 rows × 3 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-ee47fffb-8a71-468b-be81-12dfc4aaa13e')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-ee47fffb-8a71-468b-be81-12dfc4aaa13e button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-ee47fffb-8a71-468b-be81-12dfc4aaa13e');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="International-Music"><strong>International Music</strong><a class="anchor-link" href="#International-Music">&#182;</a></h3><p>The following analysis considers data from Spotify of daily streaming trends, sourced from kworb.net, which has the global daily rank of songs as well as the country-by-country breakdown.The data can be viewed <a href="https://kworb.net/spotify/">here</a>.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Importing-our-data">Importing our data<a class="anchor-link" href="#Importing-our-data">&#182;</a></h4><p>Let's first take a look at our international Spotify data from Kworb. Accessing and using this data is a bit tricky because each different country has a different table with its own national data on its own page. The following cell uses a for-loop along with some string comprehension in order to read each table from their respective URL. Each URL is identical except a two-letter country identifier, so using a regular expression and slicing we can iterate over each, reformatting it to be tidy, and adding each table to one large table we can use for analysis.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#Scrape Spotify Weekly Streams Data from each country</span>

<span class="c1">#Use requests and BeautifulSoup to access the main Spotify page</span>
<span class="c1">#which has a table with links to each country table</span>
<span class="n">r</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">"https://kworb.net/spotify/"</span><span class="p">)</span>

<span class="n">soup</span> <span class="o">=</span> <span class="n">BeautifulSoup</span><span class="p">(</span><span class="n">r</span><span class="o">.</span><span class="n">content</span><span class="p">)</span>
<span class="n">soup</span><span class="o">.</span><span class="n">prettify</span><span class="p">()</span>

<span class="c1">#Use soup.findall() with a RegEx to grab every weekly URL and store as a list of</span>
<span class="c1">#HTML</span>
<span class="n">kworb_spotify</span> <span class="o">=</span> <span class="n">soup</span><span class="o">.</span><span class="n">findAll</span><span class="p">(</span><span class="s1">'a'</span><span class="p">,</span> <span class="n">attrs</span><span class="o">=</span><span class="p">{</span><span class="s1">'href'</span><span class="p">:</span> <span class="n">re</span><span class="o">.</span><span class="n">compile</span><span class="p">(</span><span class="s2">"country/.._weekly.html"</span><span class="p">)})</span>

<span class="c1">#This dataframe will store all of our data</span>
<span class="n">df_spotify</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">()</span>

<span class="c1">#This for loop iterates over each link in kworb_spotify, importing each, reformatting</span>
<span class="c1">#and finally joining with our df_spotify</span>
<span class="k">for</span> <span class="n">link</span> <span class="ow">in</span> <span class="n">kworb_spotify</span><span class="p">:</span>

  <span class="c1">#Read in each URL to a dataframe</span>
  <span class="n">tempstr</span> <span class="o">=</span> <span class="nb">str</span><span class="p">(</span><span class="n">link</span><span class="p">)</span>
  <span class="c1">#Select the part of the string that contains the variable part of the URL</span>
  <span class="n">tempstr</span> <span class="o">=</span> <span class="n">tempstr</span><span class="p">[</span><span class="mi">9</span><span class="p">:</span><span class="mi">31</span><span class="p">]</span>
  <span class="c1">#Grab the two-character country code for each table</span>
  <span class="n">country_mark</span> <span class="o">=</span> <span class="n">tempstr</span><span class="p">[</span><span class="mi">8</span><span class="p">:</span><span class="mi">10</span><span class="p">]</span>
  <span class="c1">#Create a string of the URL to pass to pandas to read</span>
  <span class="n">tempURL</span> <span class="o">=</span> <span class="s2">"https://kworb.net/spotify/"</span> <span class="o">+</span> <span class="n">tempstr</span>
  <span class="c1">#Read the URL and then add table to a temporary dataframe</span>
  <span class="n">tempdf</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_html</span><span class="p">(</span><span class="n">tempURL</span><span class="p">)</span>
  <span class="n">df_temp</span> <span class="o">=</span> <span class="n">tempdf</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
  <span class="c1">#Adjust dataframes as they come in</span>

  <span class="c1">#Split the "Artist and Title" column into two separate columns</span>
  <span class="n">new_cols</span> <span class="o">=</span> <span class="n">df_temp</span><span class="p">[</span><span class="s2">"Artist and Title"</span><span class="p">]</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="s2">" - "</span><span class="p">,</span> <span class="n">expand</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
  <span class="n">df_temp</span><span class="p">[</span><span class="s2">"Artist"</span><span class="p">],</span> <span class="n">df_temp</span><span class="p">[</span><span class="s2">"Title"</span><span class="p">]</span> <span class="o">=</span> <span class="n">new_cols</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">new_cols</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span>

<span class="c1">#Create df with relevant columns in proper order</span>
  <span class="n">df_temp</span> <span class="o">=</span> <span class="n">df_temp</span><span class="p">[[</span><span class="s2">"Pos"</span><span class="p">,</span>
                         <span class="s2">"P+"</span><span class="p">,</span>
                         <span class="s2">"Artist"</span><span class="p">,</span>
                         <span class="s2">"Title"</span><span class="p">,</span>
                         <span class="s2">"Streams"</span>
                         <span class="p">]]</span>
  <span class="n">df_temp</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">]</span> <span class="o">=</span> <span class="n">country_mark</span>
  <span class="n">df_spotify</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">df_spotify</span><span class="p">,</span> <span class="n">df_temp</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">ignore_index</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>

<span class="c1">#Display our resulting dataframe</span>
<span class="n">df_spotify</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>&lt;ipython-input-54-f20365b2652f&gt;:45: SettingWithCopyWarning:
A value is trying to be set on a copy of a slice from a DataFrame.
Try using .loc[row_indexer,col_indexer] = value instead

See the caveats in the documentation: https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#returning-a-view-versus-a-copy
  df_temp[&#34;Country&#34;] = country_mark
</pre>
</div>
</div>

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-63b103c4-d613-499a-b02a-8e5046274b60">
    <div class="colab-df-container">
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
      <th>Pos</th>
      <th>P+</th>
      <th>Artist</th>
      <th>Title</th>
      <th>Streams</th>
      <th>Country</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>NEW</td>
      <td>Metro Boomin</td>
      <td>Creepin'</td>
      <td>13367331</td>
      <td>us</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>NEW</td>
      <td>Metro Boomin</td>
      <td>Superhero (Heroes &amp; Villains) [with Future &amp; C...</td>
      <td>11500298</td>
      <td>us</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>-1</td>
      <td>Brenda Lee</td>
      <td>Rockin' Around The Christmas Tree</td>
      <td>11338691</td>
      <td>us</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>-3</td>
      <td>Drake</td>
      <td>Rich Flex</td>
      <td>10352357</td>
      <td>us</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>-1</td>
      <td>Mariah Carey</td>
      <td>All I Want for Christmas Is You</td>
      <td>9246348</td>
      <td>us</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>14053</th>
      <td>196</td>
      <td>-17</td>
      <td>HIEUTHUHAI</td>
      <td>Bật Nhạc Lên</td>
      <td>58422</td>
      <td>vn</td>
    </tr>
    <tr>
      <th>14054</th>
      <td>197</td>
      <td>-42</td>
      <td>Mai Tiến Dũng</td>
      <td>Người Như Anh</td>
      <td>58223</td>
      <td>vn</td>
    </tr>
    <tr>
      <th>14055</th>
      <td>198</td>
      <td>-1</td>
      <td>Suni Hạ Linh</td>
      <td>Em Đã Biết</td>
      <td>58120</td>
      <td>vn</td>
    </tr>
    <tr>
      <th>14056</th>
      <td>199</td>
      <td>-15</td>
      <td>benny blanco</td>
      <td>Bad Decisions</td>
      <td>57763</td>
      <td>vn</td>
    </tr>
    <tr>
      <th>14057</th>
      <td>200</td>
      <td>RE</td>
      <td>Brenda Lee</td>
      <td>Rockin' Around The Christmas Tree</td>
      <td>57359</td>
      <td>vn</td>
    </tr>
  </tbody>
</table>
<p>14058 rows × 6 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-63b103c4-d613-499a-b02a-8e5046274b60')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-63b103c4-d613-499a-b02a-8e5046274b60 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-63b103c4-d613-499a-b02a-8e5046274b60');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>The dataframe above features 14,058 rows, with each row representing a particular song's performance in a given country. The "Pos" and "P+" columns show the track's position and position change in its respective country's chart.
Let's familiarize ourself with this data by looking at some summary statistics about streams:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#use .describe to get summary statistics</span>
<span class="n">df_spotify</span><span class="p">[</span><span class="s1">'Streams'</span><span class="p">]</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>count    1.405800e+04
mean     3.313521e+05
std      6.984888e+05
min      1.008000e+03
25%      3.394925e+04
50%      8.355000e+04
75%      3.347408e+05
max      1.336733e+07
Name: Streams, dtype: float64</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>At first glance, we see a wide range of orders of magnitude, ranging from hundreds to millions of streams. This is a result of the inclusion of countries as small as Andorra (pop. 77,000) and Malta (pop. 550,000). Looking at the graph below, we can see just how top-heavy it really is:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">df_spotify</span><span class="p">[</span><span class="s1">'Streams'</span><span class="p">]</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">title</span><span class="o">=</span><span class="s1">'Spotify Data Summary Stats'</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f77262dde80&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
class="
jp-needs-light-background
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>This tells us that in general, listens are concentrated in smash hit songs in large markets, which aligns with common intuition about how fame works. However,this data still includes data from the USA and other English-speaking countries, so it doesn't tell us much about artists and listening patterns outside the Anglosphere. Let's change this by dropping English-speaking countries and looking at the results.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#This cell filters out </span>
<span class="n">df_spotify_nonAnglo</span> <span class="o">=</span> <span class="n">df_spotify</span><span class="p">[</span><span class="n">df_spotify</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">]</span> <span class="o">!=</span> <span class="s1">'us'</span><span class="p">]</span> <span class="c1">#USA</span>
<span class="n">df_spotify_nonAnglo</span> <span class="o">=</span> <span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="n">df_spotify</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">]</span> <span class="o">!=</span> <span class="s1">'gb'</span><span class="p">]</span> <span class="c1">#United Kingdom</span>
<span class="n">df_spotify_nonAnglo</span> <span class="o">=</span> <span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="n">df_spotify</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">]</span> <span class="o">!=</span> <span class="s1">'ca'</span><span class="p">]</span> <span class="c1">#Canada</span>
<span class="n">df_spotify_nonAnglo</span> <span class="o">=</span> <span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="n">df_spotify</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">]</span> <span class="o">!=</span> <span class="s1">'au'</span><span class="p">]</span> <span class="c1">#Australia</span>
<span class="n">df_spotify_nonAnglo</span> <span class="o">=</span> <span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="n">df_spotify</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">]</span> <span class="o">!=</span> <span class="s1">'nz'</span><span class="p">]</span> <span class="c1">#New Zealand</span>
<span class="n">df_spotify_nonAnglo</span> <span class="o">=</span> <span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="n">df_spotify</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">]</span> <span class="o">!=</span> <span class="s1">'ie'</span><span class="p">]</span> <span class="c1">#Ireland</span>

<span class="c1">#Sort the datafram by streams in descending order and display the first 10 rows</span>
<span class="n">df_spotify_nonAnglo</span><span class="o">.</span><span class="n">sort_values</span><span class="p">(</span><span class="s2">"Streams"</span><span class="p">,</span> <span class="n">ascending</span><span class="o">=</span><span class="kc">False</span><span class="p">)</span><span class="o">.</span><span class="n">head</span><span class="p">(</span><span class="n">n</span><span class="o">=</span><span class="mi">10</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="application/vnd.jupyter.stderr">
<pre>&lt;ipython-input-57-cc362f745abe&gt;:3: UserWarning: Boolean Series key will be reindexed to match DataFrame index.
  df_spotify_nonAnglo = df_spotify_nonAnglo[df_spotify[&#34;Country&#34;] != &#39;gb&#39;] #United Kingdom
&lt;ipython-input-57-cc362f745abe&gt;:4: UserWarning: Boolean Series key will be reindexed to match DataFrame index.
  df_spotify_nonAnglo = df_spotify_nonAnglo[df_spotify[&#34;Country&#34;] != &#39;ca&#39;] #Canada
&lt;ipython-input-57-cc362f745abe&gt;:5: UserWarning: Boolean Series key will be reindexed to match DataFrame index.
  df_spotify_nonAnglo = df_spotify_nonAnglo[df_spotify[&#34;Country&#34;] != &#39;au&#39;] #Australia
&lt;ipython-input-57-cc362f745abe&gt;:6: UserWarning: Boolean Series key will be reindexed to match DataFrame index.
  df_spotify_nonAnglo = df_spotify_nonAnglo[df_spotify[&#34;Country&#34;] != &#39;nz&#39;] #New Zealand
&lt;ipython-input-57-cc362f745abe&gt;:7: UserWarning: Boolean Series key will be reindexed to match DataFrame index.
  df_spotify_nonAnglo = df_spotify_nonAnglo[df_spotify[&#34;Country&#34;] != &#39;ie&#39;] #Ireland
</pre>
</div>
</div>

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-bd65b56d-dcde-4e92-a7d8-d8d3954418d4">
    <div class="colab-df-container">
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
      <th>Pos</th>
      <th>P+</th>
      <th>Artist</th>
      <th>Title</th>
      <th>Streams</th>
      <th>Country</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>6058</th>
      <td>1</td>
      <td>=</td>
      <td>King</td>
      <td>Maan Meri Jaan</td>
      <td>12487947</td>
      <td>in</td>
    </tr>
    <tr>
      <th>1458</th>
      <td>1</td>
      <td>=</td>
      <td>MC MENOR HR</td>
      <td>Evoque Prata</td>
      <td>8874752</td>
      <td>br</td>
    </tr>
    <tr>
      <th>13058</th>
      <td>1</td>
      <td>+1</td>
      <td>Mert Demir</td>
      <td>Antidepresan</td>
      <td>8163927</td>
      <td>tr</td>
    </tr>
    <tr>
      <th>1459</th>
      <td>2</td>
      <td>+1</td>
      <td>Israel &amp; Rodolffo</td>
      <td>Bombonzinho</td>
      <td>7330459</td>
      <td>br</td>
    </tr>
    <tr>
      <th>1460</th>
      <td>3</td>
      <td>-1</td>
      <td>Gustavo Mioto</td>
      <td>Eu Gosto Assim</td>
      <td>7084349</td>
      <td>br</td>
    </tr>
    <tr>
      <th>8258</th>
      <td>1</td>
      <td>=</td>
      <td>Manuel Turizo</td>
      <td>La Bachata</td>
      <td>6995865</td>
      <td>mx</td>
    </tr>
    <tr>
      <th>8259</th>
      <td>2</td>
      <td>+1</td>
      <td>Bellakath</td>
      <td>Gatita</td>
      <td>6380641</td>
      <td>mx</td>
    </tr>
    <tr>
      <th>6059</th>
      <td>2</td>
      <td>=</td>
      <td>Pritam</td>
      <td>Kesariya</td>
      <td>6360181</td>
      <td>in</td>
    </tr>
    <tr>
      <th>8260</th>
      <td>3</td>
      <td>+1</td>
      <td>Bad Bunny</td>
      <td>Me Porto Bonito</td>
      <td>6302217</td>
      <td>mx</td>
    </tr>
    <tr>
      <th>8261</th>
      <td>4</td>
      <td>-2</td>
      <td>Grupo Frontera</td>
      <td>No Se Va</td>
      <td>6147330</td>
      <td>mx</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-bd65b56d-dcde-4e92-a7d8-d8d3954418d4')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-bd65b56d-dcde-4e92-a7d8-d8d3954418d4 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-bd65b56d-dcde-4e92-a7d8-d8d3954418d4');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>By sorting the non-Anglosphere table in descending order like above, we can see the top performing tracks of the week that we, the creators, likely haven't heard. Here we see King again at the top of the list. In general, we see that the most streamed songs are streamed in large countries like India, Brazil, and Mexico. We can also compare the distribution of streams to the original below:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#Plot non-Anglo summary stats</span>
<span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="s1">'Streams'</span><span class="p">]</span><span class="o">.</span><span class="n">describe</span><span class="p">()</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">title</span><span class="o">=</span><span class="s1">'Spotify non-Anglo Data Summary Stats'</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"red"</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f7725f69220&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
class="
jp-needs-light-background
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>The global market minus English-speaking countries is still quite top heavy. Streams by song by country provide some interesting insight, but more important to our question is Artists. Let's take a count of each time an artist appears in our frame:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#Get the value counts of each different artist name in our dataframe:</span>
<span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="s2">"Artist"</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>Bad Bunny           543
Metro Boomin        394
The Weeknd          247
RM                  145
Feid                140
                   ...
Hamo ElTikha          1
Ramy Sabry            1
Disco Misr            1
Manuel Rodriguez      1
Mai Tiến Dũng         1
Name: Artist, Length: 2854, dtype: int64</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>These values are important because while they don't necessarily reflect which artists are most popular in total, they show which artists are popular in many different countries, and ultimatlely have the most international appeal. Let's plot the top 10 artists on this list on a bar graph to visualize:</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#Restrict our series to the top 10 artists</span>
<span class="n">top10_artist_series</span> <span class="o">=</span> <span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="s2">"Artist"</span><span class="p">]</span><span class="o">.</span><span class="n">value_counts</span><span class="p">()[:</span><span class="mi">10</span><span class="p">]</span>

<span class="c1">#Plot a horizontal bar graph</span>
<span class="n">top10_artist_series</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">title</span><span class="o">=</span><span class="s2">"Top Artists by Appearance - non-Anglo"</span><span class="p">,</span> <span class="n">color</span><span class="o">=</span><span class="s2">"green"</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f7725f43d30&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
class="
jp-needs-light-background
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We see some familiar names like The Weeknd and Taylor Swift, along with some unknowns like RM, Feid, and Morat. Overall, this is fairly insightful as we can see known and unknown artists alike and their international appeal. Next, let's consider aggregate stream numbers by grouping songs together by artist in a pivot table.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">nonAnglo_cube</span> <span class="o">=</span> <span class="n">df_spotify_nonAnglo</span><span class="o">.</span><span class="n">pivot_table</span><span class="p">(</span><span class="n">index</span><span class="o">=</span><span class="s2">"Artist"</span><span class="p">,</span>
                                                <span class="n">columns</span><span class="o">=</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">],</span>
                                                <span class="n">values</span><span class="o">=</span><span class="s2">"Streams"</span><span class="p">,</span>
                                                <span class="n">aggfunc</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">,</span>
                                                <span class="n">fill_value</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>


<span class="p">)</span>

<span class="n">nonAnglo_cube</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-344d8408-6ecf-4d9d-b6a0-3152423bf883">
    <div class="colab-df-container">
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
      <th>Country</th>
      <th>ad</th>
      <th>ae</th>
      <th>ar</th>
      <th>at</th>
      <th>be</th>
      <th>bg</th>
      <th>bo</th>
      <th>br</th>
      <th>ch</th>
      <th>cl</th>
      <th>...</th>
      <th>sg</th>
      <th>sk</th>
      <th>sv</th>
      <th>th</th>
      <th>tr</th>
      <th>tw</th>
      <th>ua</th>
      <th>uy</th>
      <th>vn</th>
      <th>za</th>
    </tr>
    <tr>
      <th>Artist</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>$uicideboy$</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>(G)I-DLE</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>159201</td>
      <td>0</td>
      <td>0</td>
      <td>109303</td>
      <td>0</td>
      <td>280676</td>
      <td>0</td>
      <td>0</td>
      <td>60074</td>
      <td>0</td>
    </tr>
    <tr>
      <th>01099</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>070 Shake</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1.Cuz</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
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
      <th>陳華</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>106325</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>音田 雅則</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>颜人中</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>160255</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>高爾宣 OSN</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>528098</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>데이먼스 이어 Damons year</th>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>2854 rows × 65 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-344d8408-6ecf-4d9d-b6a0-3152423bf883')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-344d8408-6ecf-4d9d-b6a0-3152423bf883 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-344d8408-6ecf-4d9d-b6a0-3152423bf883');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>That's a lot of zeros! And a lot of rows, so we should narrow down our search for our visualization. All those zeros mean the artist doesn't show up in a given country's Spotify Weekly Top 200, helping to illustrate the stratification of international tastes. We'll consider artists with more than 5 million streams below and graph by country of streams.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1">#Drop rows with less than 5 million streams, then recreate pivot table</span>
<span class="n">df_spotify_nonAnglo</span> <span class="o">=</span> <span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="n">df_spotify_nonAnglo</span><span class="p">[</span><span class="s1">'Streams'</span><span class="p">]</span> <span class="o">&gt;=</span> <span class="mi">5000000</span><span class="p">]</span>
<span class="n">nonAnglo_cube</span> <span class="o">=</span> <span class="n">df_spotify_nonAnglo</span><span class="o">.</span><span class="n">pivot_table</span><span class="p">(</span><span class="n">index</span><span class="o">=</span><span class="s2">"Artist"</span><span class="p">,</span>
                                                <span class="n">columns</span><span class="o">=</span><span class="p">[</span><span class="s2">"Country"</span><span class="p">],</span>
                                                <span class="n">values</span><span class="o">=</span><span class="s2">"Streams"</span><span class="p">,</span>
                                                <span class="n">aggfunc</span><span class="o">=</span><span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">,</span>
                                                <span class="n">fill_value</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span>
<span class="p">)</span>
<span class="c1">#Make a horizontal plot of top streamed artist and streams by country</span>
<span class="n">nonAnglo_cube</span><span class="o">.</span><span class="n">plot</span><span class="o">.</span><span class="n">barh</span><span class="p">(</span><span class="n">width</span><span class="o">=</span><span class="mf">0.8</span><span class="p">,</span> <span class="n">title</span><span class="o">=</span><span class="s2">"Most Streamed Non-Anglo Artists"</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7f7725eaac40&gt;</pre>
</div>

</div>

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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CBwdEQOB44Hza+jGrIjYDDgXOCsvOxs4MyIGA3sDF1Xo/xGSxkka19K/zMzMrDpPEbfNr4CpETGmaNku+atQFLsnKeDeU2b/BVPEucTV1sC1RX8pLVtDH64q+n5mfr0z0LeonZUk9YyI2cU7RsSFpKDOoEGDnJTazNrVq6++yrHHHsujjz7KyiuvzBprrMFZZ53FxhtvXJf2x44dyzLLLMPWW29dl/ZaygG2lSQNJY0OtypdBZwSEX9sYZNLATMjYkAL94syr5cCvhARnf/WPTPrkiKCvfbai+HDh3P11VcDMGnSJF577bW6BtiePXuWDbBz585l6aUbGwIdYFtB0irApcBBEfFeyerbgF9JujIiZktaC/gkIl6v1mZEvCvpeUn7RsS1SsPPzSNiUjPd2R84NX9/MC/7J3A0cFru74CImFitkckvz6LpxL83c6iuZfqpX+voLpgtse6++266d+/OkUceuWDZFltsQUTwox/9iFtuuQVJnHTSSey///6MHTuW008/nZtvvhmA73//+wwaNIgRI0bQ1NTE8OHDuemmm/jkk0+49tpr6dGjBxdccAHdunXjiiuu4JxzzuHiiy+mR48ePPbYY2yzzTbcdNNNPPDAA6y22mrMnz+fjTfemAcffJDVViubWrjFHGBb50hgdeAPJRe+T4mIMZL6AA/mdbOBg4GqATYblts8CegOXA00F2BXkfQ48BFwYF72A+C8vHxp0vT0kRX2NzNrd1OmTGHgwIGfWn799dczceJEJk2axJtvvsngwYPZfvtKt7EstOqqqzJhwgTOP/98Tj/9dC666CKOPPJIevbsyfHHHw/AxRdfzIwZM3jggQfo1q0bvXr14sorr+TYY4/ljjvuYIsttqhbcAUH2FaJiFOAU6qsP5t0o1G1NprKLHse+EqZ5SOLXo8oWX1aRPy4ZPs3SSPamm22Vi/GeURnZh3svvvu48ADD6Rbt26sscYafOlLX+LRRx9lpZVWqrrfN77xDQAGDhzI9ddfX3G7fffdl27dugFw6KGHsueee3LsscdyySWXcMghh9TvRPBdxGZm1gH69evH+PHja95+6aWXZv78+Qvel2aHWnbZdE9ot27dmDt3bsV2VlhhhQWv11lnHdZYYw3uuusuHnnkEXbdddea+1MLB9hOLCKaWpqowsxscbDjjjvy0UcfceGFFy5Y9vjj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
"
class="
jp-needs-light-background
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>This chart show not only top artists, but also <em>where</em> most of their streams come from. An advertiser looking for a potential spokesperson could look at this to determine if a given musician is appropriate for their target audience.</p>
<p>Next, we will pair this data with polling data from YouGov to begin building our model.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Linking-Spotify-International-Weekly-Top-Charts-with-YouGov-Polling-Data"><strong>Linking Spotify International Weekly Top Charts with YouGov Polling Data</strong><a class="anchor-link" href="#Linking-Spotify-International-Weekly-Top-Charts-with-YouGov-Polling-Data">&#182;</a></h3>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>First, we need to re-import the Spotify Weekly data to get it into a format that can be easily merged with the YouGov data.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="kn">import</span> <span class="nn">re</span>

<span class="n">r</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">"https://kworb.net/spotify/"</span><span class="p">)</span>

<span class="n">soup</span> <span class="o">=</span> <span class="n">BeautifulSoup</span><span class="p">(</span><span class="n">r</span><span class="o">.</span><span class="n">content</span><span class="p">)</span>
<span class="n">soup</span><span class="o">.</span><span class="n">prettify</span><span class="p">()</span>

<span class="n">kworb_spotify</span> <span class="o">=</span> <span class="n">soup</span><span class="o">.</span><span class="n">findAll</span><span class="p">(</span><span class="s1">'a'</span><span class="p">,</span> <span class="n">attrs</span><span class="o">=</span><span class="p">{</span><span class="s1">'href'</span><span class="p">:</span> <span class="n">re</span><span class="o">.</span><span class="n">compile</span><span class="p">(</span><span class="s2">"country/.._weekly.html"</span><span class="p">)})</span>

<span class="n">df_spotify</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">()</span>
<span class="n">countries</span> <span class="o">=</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">link</span> <span class="ow">in</span> <span class="n">kworb_spotify</span><span class="p">:</span>

  <span class="c1">#Read in each URL to a dataframe</span>
  <span class="n">tempstr</span> <span class="o">=</span> <span class="nb">str</span><span class="p">(</span><span class="n">link</span><span class="p">)</span>
  <span class="c1">#print(tempstr[9:31])</span>
  <span class="n">tempstr</span> <span class="o">=</span> <span class="n">tempstr</span><span class="p">[</span><span class="mi">9</span><span class="p">:</span><span class="mi">31</span><span class="p">]</span>
  <span class="c1">#Grab the two-character country code for each table</span>
  <span class="n">country_mark</span> <span class="o">=</span> <span class="n">tempstr</span><span class="p">[</span><span class="mi">8</span><span class="p">:</span><span class="mi">10</span><span class="p">]</span>
  <span class="c1">#print(country_mark)</span>
  <span class="n">tempURL</span> <span class="o">=</span> <span class="s2">"https://kworb.net/spotify/"</span> <span class="o">+</span> <span class="n">tempstr</span>
  <span class="c1">#print(tempURL)</span>
  <span class="n">tempdf</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_html</span><span class="p">(</span><span class="n">tempURL</span><span class="p">)</span>
  <span class="n">df_temp</span> <span class="o">=</span> <span class="n">tempdf</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
  <span class="c1">#Adjust dataframes as they come in</span>

  <span class="c1">#Split the "Artist and Title" column into two separate columns</span>
  <span class="n">new_cols</span> <span class="o">=</span> <span class="n">df_temp</span><span class="p">[</span><span class="s2">"Artist and Title"</span><span class="p">]</span><span class="o">.</span><span class="n">str</span><span class="o">.</span><span class="n">split</span><span class="p">(</span><span class="s2">" - "</span><span class="p">,</span> <span class="n">expand</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
  <span class="n">df_temp</span><span class="p">[</span><span class="s2">"Artist"</span><span class="p">],</span> <span class="n">df_temp</span><span class="p">[</span><span class="s2">"Title"</span><span class="p">]</span> <span class="o">=</span> <span class="n">new_cols</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="n">new_cols</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span>

  <span class="c1"># Append country codes to list</span>
  <span class="n">countries</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">country_mark</span><span class="p">)</span>
  <span class="c1"># Narrow down dataframe to country streams, artist, and title</span>
  <span class="n">df_temp</span><span class="p">[</span><span class="n">country_mark</span> <span class="o">+</span> <span class="s2">" Streams"</span><span class="p">]</span> <span class="o">=</span> <span class="n">df_temp</span><span class="p">[</span><span class="s2">"Streams"</span><span class="p">]</span>
  <span class="n">df_temp</span> <span class="o">=</span> <span class="n">df_temp</span><span class="p">[[</span><span class="s2">"Artist"</span><span class="p">,</span> <span class="s2">"Title"</span><span class="p">,</span> <span class="n">country_mark</span> <span class="o">+</span> <span class="s2">" Streams"</span><span class="p">]]</span>
  <span class="c1"># Concatenate dataframes</span>
  <span class="n">df_spotify</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">df_spotify</span><span class="p">,</span> <span class="n">df_temp</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">ignore_index</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>

<span class="n">df_spotify</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-d2162c6c-3d5c-43f1-9cc9-9f4ba138a4ff">
    <div class="colab-df-container">
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
      <th>Artist</th>
      <th>Title</th>
      <th>us Streams</th>
      <th>gb Streams</th>
      <th>ad Streams</th>
      <th>ar Streams</th>
      <th>au Streams</th>
      <th>at Streams</th>
      <th>be Streams</th>
      <th>bo Streams</th>
      <th>...</th>
      <th>es Streams</th>
      <th>se Streams</th>
      <th>ch Streams</th>
      <th>tw Streams</th>
      <th>th Streams</th>
      <th>tr Streams</th>
      <th>ua Streams</th>
      <th>ae Streams</th>
      <th>uy Streams</th>
      <th>vn Streams</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Metro Boomin</td>
      <td>Creepin'</td>
      <td>13367331.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Metro Boomin</td>
      <td>Superhero (Heroes &amp; Villains) [with Future &amp; C...</td>
      <td>11500298.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Brenda Lee</td>
      <td>Rockin' Around The Christmas Tree</td>
      <td>11338691.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Drake</td>
      <td>Rich Flex</td>
      <td>10352357.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Mariah Carey</td>
      <td>All I Want for Christmas Is You</td>
      <td>9246348.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
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
      <th>14053</th>
      <td>HIEUTHUHAI</td>
      <td>Bật Nhạc Lên</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>58422.0</td>
    </tr>
    <tr>
      <th>14054</th>
      <td>Mai Tiến Dũng</td>
      <td>Người Như Anh</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>58223.0</td>
    </tr>
    <tr>
      <th>14055</th>
      <td>Suni Hạ Linh</td>
      <td>Em Đã Biết</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>58120.0</td>
    </tr>
    <tr>
      <th>14056</th>
      <td>benny blanco</td>
      <td>Bad Decisions</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>57763.0</td>
    </tr>
    <tr>
      <th>14057</th>
      <td>Brenda Lee</td>
      <td>Rockin' Around The Christmas Tree</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>57359.0</td>
    </tr>
  </tbody>
</table>
<p>14058 rows × 73 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-d2162c6c-3d5c-43f1-9cc9-9f4ba138a4ff')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-d2162c6c-3d5c-43f1-9cc9-9f4ba138a4ff button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-d2162c6c-3d5c-43f1-9cc9-9f4ba138a4ff');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Next, we clean the data by filling N/A values with 0 and combining rows with the same artist by adding streams by country.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">df_spotify</span> <span class="o">=</span> <span class="n">df_spotify</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
<span class="n">df_spotify</span> <span class="o">=</span> <span class="n">df_spotify</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">"Title"</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="k">for</span> <span class="n">c</span> <span class="ow">in</span> <span class="n">countries</span><span class="p">:</span>
  <span class="n">df_spotify</span><span class="p">[</span><span class="n">c</span><span class="p">]</span> <span class="o">=</span> <span class="n">df_spotify</span><span class="o">.</span><span class="n">groupby</span><span class="p">([</span><span class="s2">"Artist"</span><span class="p">])[</span><span class="n">c</span> <span class="o">+</span> <span class="s2">" Streams"</span><span class="p">]</span><span class="o">.</span><span class="n">transform</span><span class="p">(</span><span class="s2">"sum"</span><span class="p">)</span>
<span class="k">for</span> <span class="n">c</span> <span class="ow">in</span> <span class="n">countries</span><span class="p">:</span>
  <span class="n">df_spotify</span> <span class="o">=</span> <span class="n">df_spotify</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="n">c</span> <span class="o">+</span> <span class="s2">" Streams"</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df_spotify</span> <span class="o">=</span> <span class="n">df_spotify</span><span class="o">.</span><span class="n">drop_duplicates</span><span class="p">()</span>
<span class="n">df_spotify</span> <span class="o">=</span> <span class="n">df_spotify</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">df_spotify</span> <span class="o">=</span> <span class="n">df_spotify</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">"index"</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df_spotify</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-a562ca65-8f26-446d-989d-9cc7ed764446">
    <div class="colab-df-container">
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
      <th>Artist</th>
      <th>us</th>
      <th>gb</th>
      <th>ad</th>
      <th>ar</th>
      <th>au</th>
      <th>at</th>
      <th>be</th>
      <th>bo</th>
      <th>br</th>
      <th>...</th>
      <th>es</th>
      <th>se</th>
      <th>ch</th>
      <th>tw</th>
      <th>th</th>
      <th>tr</th>
      <th>ua</th>
      <th>ae</th>
      <th>uy</th>
      <th>vn</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Metro Boomin</td>
      <td>103210991.0</td>
      <td>11552927.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>5591652.0</td>
      <td>799536.0</td>
      <td>993846.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>986741.0</td>
      <td>1558196.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1191451.0</td>
      <td>99847.0</td>
      <td>528173.0</td>
      <td>0.0</td>
      <td>85851.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Brenda Lee</td>
      <td>11338691.0</td>
      <td>3601199.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1002049.0</td>
      <td>343441.0</td>
      <td>179753.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>359191.0</td>
      <td>704293.0</td>
      <td>275190.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>31589.0</td>
      <td>0.0</td>
      <td>57359.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Drake</td>
      <td>39754913.0</td>
      <td>2195614.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>2321183.0</td>
      <td>137172.0</td>
      <td>126636.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>226335.0</td>
      <td>174699.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>28793.0</td>
      <td>126733.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Mariah Carey</td>
      <td>12127792.0</td>
      <td>5104622.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1285537.0</td>
      <td>480178.0</td>
      <td>406480.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>880081.0</td>
      <td>1163102.0</td>
      <td>429045.0</td>
      <td>79088.0</td>
      <td>105312.0</td>
      <td>0.0</td>
      <td>25911.0</td>
      <td>42601.0</td>
      <td>0.0</td>
      <td>113698.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Bobby Helms</td>
      <td>8432197.0</td>
      <td>2837096.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>805163.0</td>
      <td>271058.0</td>
      <td>155574.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>377714.0</td>
      <td>648371.0</td>
      <td>244200.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>27601.0</td>
      <td>0.0</td>
      <td>59257.0</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
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
      <th>2931</th>
      <td>Orange</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>59426.0</td>
    </tr>
    <tr>
      <th>2932</th>
      <td>SOOBIN</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>59312.0</td>
    </tr>
    <tr>
      <th>2933</th>
      <td>Uyên Linh</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>58978.0</td>
    </tr>
    <tr>
      <th>2934</th>
      <td>Ha Anh Tuan</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>58842.0</td>
    </tr>
    <tr>
      <th>2935</th>
      <td>Mai Tiến Dũng</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>58223.0</td>
    </tr>
  </tbody>
</table>
<p>2936 rows × 72 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-a562ca65-8f26-446d-989d-9cc7ed764446')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-a562ca65-8f26-446d-989d-9cc7ed764446 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-a562ca65-8f26-446d-989d-9cc7ed764446');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="YouGov-vs.-Spotify-Global-Weekly-Charts"><strong>YouGov vs. Spotify Global Weekly Charts</strong><a class="anchor-link" href="#YouGov-vs.-Spotify-Global-Weekly-Charts">&#182;</a></h3><p>First, we will merge the Spotify weekly data with the YouGov poll data. The data is aligned to provide the number of streams within each country, broken down by artist.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">df_spotify</span><span class="p">[</span><span class="s2">"Name"</span><span class="p">]</span> <span class="o">=</span> <span class="n">df_spotify</span><span class="p">[</span><span class="s2">"Artist"</span><span class="p">]</span>
<span class="n">df_spotify_yougov</span> <span class="o">=</span> <span class="n">df_yougov</span><span class="o">.</span><span class="n">merge</span><span class="p">(</span><span class="n">df_spotify</span><span class="p">,</span> <span class="n">on</span><span class="o">=</span><span class="p">[</span><span class="s2">"Name"</span><span class="p">,</span> <span class="s2">"Name"</span><span class="p">],</span> <span class="n">how</span><span class="o">=</span><span class="s2">"outer"</span><span class="p">)</span>
<span class="n">df_spotify_yougov</span> <span class="o">=</span> <span class="n">df_spotify_yougov</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
<span class="n">df_spotify_yougov</span> <span class="o">=</span> <span class="n">df_spotify_yougov</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">"Artist"</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df_spotify_yougov</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-ab26a629-df24-48d1-8278-76426a417dd9">
    <div class="colab-df-container">
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
      <th>Name</th>
      <th>Fame</th>
      <th>Popularity</th>
      <th>us</th>
      <th>gb</th>
      <th>ad</th>
      <th>ar</th>
      <th>au</th>
      <th>at</th>
      <th>be</th>
      <th>...</th>
      <th>es</th>
      <th>se</th>
      <th>ch</th>
      <th>tw</th>
      <th>th</th>
      <th>tr</th>
      <th>ua</th>
      <th>ae</th>
      <th>uy</th>
      <th>vn</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Adele</td>
      <td>98.0</td>
      <td>70.0</td>
      <td>0.0</td>
      <td>549377.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>349096.0</td>
      <td>0.0</td>
      <td>158690.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>159594.0</td>
      <td>61990.0</td>
      <td>72281.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>18561.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Selena Gomez</td>
      <td>98.0</td>
      <td>62.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>2484.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Katy Perry</td>
      <td>97.0</td>
      <td>59.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>69294.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Rihanna</td>
      <td>96.0</td>
      <td>61.0</td>
      <td>0.0</td>
      <td>642194.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>411205.0</td>
      <td>0.0</td>
      <td>230398.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>233342.0</td>
      <td>126824.0</td>
      <td>76827.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>20575.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Billie Eilish</td>
      <td>96.0</td>
      <td>58.0</td>
      <td>2284356.0</td>
      <td>509188.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>606425.0</td>
      <td>0.0</td>
      <td>101632.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>151783.0</td>
      <td>67601.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>33851.0</td>
      <td>0.0</td>
      <td>0.0</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
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
      <th>3086</th>
      <td>Orange</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>59426.0</td>
    </tr>
    <tr>
      <th>3087</th>
      <td>SOOBIN</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>59312.0</td>
    </tr>
    <tr>
      <th>3088</th>
      <td>Uyên Linh</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>58978.0</td>
    </tr>
    <tr>
      <th>3089</th>
      <td>Ha Anh Tuan</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>58842.0</td>
    </tr>
    <tr>
      <th>3090</th>
      <td>Mai Tiến Dũng</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>58223.0</td>
    </tr>
  </tbody>
</table>
<p>3091 rows × 74 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-ab26a629-df24-48d1-8278-76426a417dd9')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-ab26a629-df24-48d1-8278-76426a417dd9 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-ab26a629-df24-48d1-8278-76426a417dd9');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We predict that the best predictor of fame among U.S. millenials will be streams in the United States.</p>
<p>The following scatterplot visualizes this relationship.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">df_spotify_yougov</span><span class="p">[</span><span class="s2">"us"</span><span class="p">]</span><span class="o">.</span><span class="n">corr</span><span class="p">(</span><span class="n">df_spotify_yougov</span><span class="p">[</span><span class="s2">"Fame"</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>0.10797305485754818</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">df_spotify_yougov</span><span class="p">[</span><span class="s2">"us"</span><span class="p">],</span> <span class="n">df_spotify_yougov</span><span class="p">[</span><span class="s2">"Fame"</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">"Fame Among Millenials vs. Streams in the U.S."</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">"Streams in the U.S."</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">"Fame Among Millenials"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
class="
jp-needs-light-background
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>It's clear from the low correlation and non-linear relationship in the scatterplot that an artist's streams in the US this week are not a strong predictor of whether American millenials have heard of them.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Now, we'll create a dataset of all the artists who are ranked #1 in any country in the world this week on the Spotify charts.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">df_unknown_artists</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">DataFrame</span><span class="p">()</span>
<span class="k">for</span> <span class="n">c</span> <span class="ow">in</span> <span class="n">countries</span><span class="p">:</span>
  <span class="nb">max</span> <span class="o">=</span> <span class="n">df_spotify_yougov</span><span class="p">[</span><span class="n">c</span><span class="p">]</span><span class="o">.</span><span class="n">idxmax</span><span class="p">()</span>
  <span class="n">df_unknown_artists</span> <span class="o">=</span> <span class="n">df_unknown_artists</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">df_spotify_yougov</span><span class="o">.</span><span class="n">iloc</span><span class="p">[</span><span class="nb">max</span><span class="p">],</span> <span class="n">ignore_index</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
<span class="n">df_unknown_artists</span> <span class="o">=</span> <span class="n">df_unknown_artists</span><span class="o">.</span><span class="n">drop_duplicates</span><span class="p">()</span>
<span class="n">df_unknown_artists</span> <span class="o">=</span> <span class="n">df_unknown_artists</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">df_unknown_artists</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-e94937c1-8bd2-4579-a6a4-a5483cdeccd3">
    <div class="colab-df-container">
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
      <th>index</th>
      <th>Name</th>
      <th>Fame</th>
      <th>Popularity</th>
      <th>us</th>
      <th>gb</th>
      <th>ad</th>
      <th>ar</th>
      <th>au</th>
      <th>at</th>
      <th>...</th>
      <th>es</th>
      <th>se</th>
      <th>ch</th>
      <th>tw</th>
      <th>th</th>
      <th>tr</th>
      <th>ua</th>
      <th>ae</th>
      <th>uy</th>
      <th>vn</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Metro Boomin</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>103210991.0</td>
      <td>11552927.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>5591652.0</td>
      <td>799536.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>986741.0</td>
      <td>1558196.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1191451.0</td>
      <td>99847.0</td>
      <td>528173.0</td>
      <td>0.0</td>
      <td>85851.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>C. Tangana</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>7843.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>1812611.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>YSY A</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>12331458.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>532530.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7</td>
      <td>Bad Bunny</td>
      <td>70.0</td>
      <td>34.0</td>
      <td>18846024.0</td>
      <td>0.0</td>
      <td>6256.0</td>
      <td>9244177.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>11275926.0</td>
      <td>0.0</td>
      <td>133324.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>13553.0</td>
      <td>569191.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>8</td>
      <td>Guilherme &amp; Benuto</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>12</td>
      <td>Feid</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1343304.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>7290402.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>254780.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>15</td>
      <td>Calin</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>22</td>
      <td>Gettomasa</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>23</td>
      <td>SDM</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>25</td>
      <td>SIDARTA</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>10</th>
      <td>28</td>
      <td>Keung To</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>29</td>
      <td>Azahriah</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>31</td>
      <td>King</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>26723.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>13</th>
      <td>32</td>
      <td>Tulus</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>14</th>
      <td>34</td>
      <td>Tuna</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>15</th>
      <td>35</td>
      <td>Shiva</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>16</th>
      <td>36</td>
      <td>Official HIGE DANdism</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>17</th>
      <td>40</td>
      <td>The Weeknd</td>
      <td>84.0</td>
      <td>55.0</td>
      <td>14774261.0</td>
      <td>3476704.0</td>
      <td>2970.0</td>
      <td>0.0</td>
      <td>1497616.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>319606.0</td>
      <td>367622.0</td>
      <td>0.0</td>
      <td>207346.0</td>
      <td>817250.0</td>
      <td>55312.0</td>
      <td>246742.0</td>
      <td>0.0</td>
      <td>160187.0</td>
    </tr>
    <tr>
      <th>18</th>
      <td>43</td>
      <td>ElGrandeToto</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>19</th>
      <td>44</td>
      <td>Lijpe</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>20</th>
      <td>51</td>
      <td>Taylor Swift</td>
      <td>94.0</td>
      <td>55.0</td>
      <td>45741588.0</td>
      <td>6542563.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>4374456.0</td>
      <td>165715.0</td>
      <td>...</td>
      <td>415866.0</td>
      <td>393057.0</td>
      <td>120138.0</td>
      <td>271648.0</td>
      <td>385345.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>199176.0</td>
      <td>22846.0</td>
      <td>230851.0</td>
    </tr>
    <tr>
      <th>21</th>
      <td>52</td>
      <td>Mata</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>22</th>
      <td>55</td>
      <td>shadowraze</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>146222.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>23</th>
      <td>60</td>
      <td>RM</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>2107923.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>346199.0</td>
      <td>2491927.0</td>
      <td>0.0</td>
      <td>26019.0</td>
      <td>118118.0</td>
      <td>31005.0</td>
      <td>3221607.0</td>
    </tr>
    <tr>
      <th>24</th>
      <td>61</td>
      <td>Quevedo</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>4432878.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>12180438.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>433149.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>25</th>
      <td>62</td>
      <td>Hooja</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>1717176.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>26</th>
      <td>64</td>
      <td>告五人</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1039092.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>27</th>
      <td>66</td>
      <td>UZI</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>13066636.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>28</th>
      <td>67</td>
      <td>SadSvit</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>...</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>317272.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>29 rows × 75 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-e94937c1-8bd2-4579-a6a4-a5483cdeccd3')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-e94937c1-8bd2-4579-a6a4-a5483cdeccd3 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-e94937c1-8bd2-4579-a6a4-a5483cdeccd3');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>All but 3 of the top national artists do not make the list of artists whom millenials have heard of. This list allows us to identify which very famous artists are not known to American millenials.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Top-1000-Artists-of-All-Time"><strong>Top 1000 Artists of All Time</strong><a class="anchor-link" href="#Top-1000-Artists-of-All-Time">&#182;</a></h3><p>This dataset ranks the top 1000 artists of all time. It combines data across thousands of critics' reviews and lists to rank the artists. It is useful for identifying the all-time most well-regarded and successful artists.</p>
<p>The 1000 entries are divided between 5 pages, so we'll read in each page into a separate dataframe, then concatenate them.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="kn">import</span> <span class="nn">requests</span>

<span class="n">URL_FIRST200</span> <span class="o">=</span> <span class="s2">"http://www.acclaimedmusic.net/061024/1948-09art.htm"</span>
<span class="n">page</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">URL_FIRST200</span><span class="p">)</span>
<span class="n">soup</span> <span class="o">=</span> <span class="n">BeautifulSoup</span><span class="p">(</span><span class="n">page</span><span class="o">.</span><span class="n">content</span><span class="p">,</span> <span class="s2">"html.parser"</span><span class="p">)</span>
<span class="n">df_first200</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_html</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">soup</span><span class="o">.</span><span class="n">find</span><span class="p">(</span><span class="s2">"table"</span><span class="p">)))</span>
<span class="n">df_first200</span> <span class="o">=</span> <span class="n">df_first200</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>

<span class="n">URL_SECOND200</span> <span class="o">=</span> <span class="s2">"http://www.acclaimedmusic.net/061024/1948-09art2.htm"</span>
<span class="n">page</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">URL_SECOND200</span><span class="p">)</span>
<span class="n">soup</span> <span class="o">=</span> <span class="n">BeautifulSoup</span><span class="p">(</span><span class="n">page</span><span class="o">.</span><span class="n">content</span><span class="p">,</span> <span class="s2">"html.parser"</span><span class="p">)</span>
<span class="n">df_second200</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_html</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">soup</span><span class="o">.</span><span class="n">find</span><span class="p">(</span><span class="s2">"table"</span><span class="p">)))</span>
<span class="n">df_second200</span> <span class="o">=</span> <span class="n">df_second200</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>

<span class="n">URL_THIRD200</span> <span class="o">=</span> <span class="s2">"http://www.acclaimedmusic.net/061024/1948-09art3.htm"</span>
<span class="n">page</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">URL_THIRD200</span><span class="p">)</span>
<span class="n">soup</span> <span class="o">=</span> <span class="n">BeautifulSoup</span><span class="p">(</span><span class="n">page</span><span class="o">.</span><span class="n">content</span><span class="p">,</span> <span class="s2">"html.parser"</span><span class="p">)</span>
<span class="n">df_third200</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_html</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">soup</span><span class="o">.</span><span class="n">find</span><span class="p">(</span><span class="s2">"table"</span><span class="p">)))</span>
<span class="n">df_third200</span> <span class="o">=</span> <span class="n">df_third200</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>

<span class="n">URL_FOURTH200</span> <span class="o">=</span> <span class="s2">"http://www.acclaimedmusic.net/061024/1948-09art4.htm"</span>
<span class="n">page</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">URL_FOURTH200</span><span class="p">)</span>
<span class="n">soup</span> <span class="o">=</span> <span class="n">BeautifulSoup</span><span class="p">(</span><span class="n">page</span><span class="o">.</span><span class="n">content</span><span class="p">,</span> <span class="s2">"html.parser"</span><span class="p">)</span>
<span class="n">df_fourth200</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_html</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">soup</span><span class="o">.</span><span class="n">find</span><span class="p">(</span><span class="s2">"table"</span><span class="p">)))</span>
<span class="n">df_fourth200</span> <span class="o">=</span> <span class="n">df_fourth200</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>

<span class="n">URL_FIFTH200</span> <span class="o">=</span> <span class="s2">"http://www.acclaimedmusic.net/061024/1948-09art5.htm"</span>
<span class="n">page</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">URL_FIFTH200</span><span class="p">)</span>
<span class="n">soup</span> <span class="o">=</span> <span class="n">BeautifulSoup</span><span class="p">(</span><span class="n">page</span><span class="o">.</span><span class="n">content</span><span class="p">,</span> <span class="s2">"html.parser"</span><span class="p">)</span>
<span class="n">df_fifth200</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_html</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">soup</span><span class="o">.</span><span class="n">find</span><span class="p">(</span><span class="s2">"table"</span><span class="p">)))</span>
<span class="n">df_fifth200</span> <span class="o">=</span> <span class="n">df_fifth200</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>

<span class="n">df_alltime</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">concat</span><span class="p">([</span><span class="n">df_first200</span><span class="p">,</span> <span class="n">df_second200</span><span class="p">,</span> <span class="n">df_third200</span><span class="p">,</span> <span class="n">df_fourth200</span><span class="p">,</span>
                        <span class="n">df_fifth200</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>

<span class="n">df_alltime</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-e298ceba-5ff8-457a-aafa-379984f6f4e3">
    <div class="colab-df-container">
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
      <th>0</th>
      <th>1</th>
      <th>2</th>
      <th>3</th>
      <th>4</th>
      <th>5</th>
      <th>6</th>
      <th>7</th>
      <th>8</th>
      <th>9</th>
      <th>10</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Albums</td>
      <td>Songs</td>
      <td>1900-49</td>
      <td>50s</td>
      <td>60s</td>
      <td>70s</td>
      <td>80s</td>
      <td>90s</td>
      <td>00s</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1.0</td>
      <td>The Beatles</td>
      <td>1</td>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1</td>
      <td>94</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2.0</td>
      <td>The Rolling Stones</td>
      <td>3</td>
      <td>2</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2</td>
      <td>2</td>
      <td>98</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3.0</td>
      <td>Bob Dylan</td>
      <td>2</td>
      <td>6</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3</td>
      <td>16</td>
      <td>177</td>
      <td>41</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4.0</td>
      <td>David Bowie</td>
      <td>4</td>
      <td>9</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>113</td>
      <td>1</td>
      <td>47</td>
      <td>NaN</td>
      <td>NaN</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>205</th>
      <td>996.0</td>
      <td>The Sundays</td>
      <td>764</td>
      <td>1369</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>513</td>
      <td>238</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>206</th>
      <td>997.0</td>
      <td>Herbert</td>
      <td>738</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>439</td>
      <td>184</td>
    </tr>
    <tr>
      <th>207</th>
      <td>998.0</td>
      <td>Stephen Stills</td>
      <td>739</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>249</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>208</th>
      <td>999.0</td>
      <td>Mazzy Star</td>
      <td>970</td>
      <td>895</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>231</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>209</th>
      <td>1000.0</td>
      <td>Blind Lemon Jefferson</td>
      <td>NaN</td>
      <td>533</td>
      <td>28</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>1050 rows × 11 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-e298ceba-5ff8-457a-aafa-379984f6f4e3')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-e298ceba-5ff8-457a-aafa-379984f6f4e3 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-e298ceba-5ff8-457a-aafa-379984f6f4e3');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Adjusting-Our-Dataframe">Adjusting Our Dataframe<a class="anchor-link" href="#Adjusting-Our-Dataframe">&#182;</a></h4><p>The dataframe from the previous cell doesn't have descriptive column names, so we'll replace them with the original names that were read in as rows. There are also NaN values for each time period where an artist didn't have any hits, so we'll replace them with 0s. Throughout the dataset, we also have the column names stored as rows. We will drop all of these rows from the dataset.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Rename columns</span>
<span class="n">df_alltime</span><span class="o">.</span><span class="n">columns</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"Ranking"</span><span class="p">,</span> <span class="s2">"Artist"</span><span class="p">,</span> <span class="s2">"Albums"</span><span class="p">,</span> <span class="s2">"Songs"</span><span class="p">,</span> <span class="s2">"1900-49"</span><span class="p">,</span> <span class="s2">"50s"</span><span class="p">,</span>
                      <span class="s2">"60s"</span><span class="p">,</span> <span class="s2">"70s"</span><span class="p">,</span> <span class="s2">"80s"</span><span class="p">,</span> <span class="s2">"90s"</span><span class="p">,</span> <span class="s2">"00s"</span><span class="p">]</span>
<span class="c1"># Replace NA values with 0</span>
<span class="n">df_alltime</span> <span class="o">=</span> <span class="n">df_alltime</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
<span class="c1"># Drop any other rows containing column titles</span>
<span class="n">df_alltime</span> <span class="o">=</span> <span class="n">df_alltime</span><span class="p">[</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"1900-49"</span><span class="p">]</span> <span class="o">!=</span> <span class="s2">"1900-49"</span><span class="p">]</span>
<span class="c1"># Reset indices and drop "index" column</span>
<span class="n">df_alltime</span> <span class="o">=</span> <span class="n">df_alltime</span><span class="o">.</span><span class="n">reset_index</span><span class="p">()</span>
<span class="n">df_alltime</span> <span class="o">=</span> <span class="n">df_alltime</span><span class="o">.</span><span class="n">drop</span><span class="p">(</span><span class="n">labels</span><span class="o">=</span><span class="p">[</span><span class="s2">"index"</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df_alltime</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-cdf46a80-bd01-4af2-bb29-eedf1d711c34">
    <div class="colab-df-container">
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
      <th>Ranking</th>
      <th>Artist</th>
      <th>Albums</th>
      <th>Songs</th>
      <th>1900-49</th>
      <th>50s</th>
      <th>60s</th>
      <th>70s</th>
      <th>80s</th>
      <th>90s</th>
      <th>00s</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1.0</td>
      <td>The Beatles</td>
      <td>1</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>94</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2.0</td>
      <td>The Rolling Stones</td>
      <td>3</td>
      <td>2</td>
      <td>0</td>
      <td>0</td>
      <td>2</td>
      <td>2</td>
      <td>98</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3.0</td>
      <td>Bob Dylan</td>
      <td>2</td>
      <td>6</td>
      <td>0</td>
      <td>0</td>
      <td>3</td>
      <td>16</td>
      <td>177</td>
      <td>41</td>
      <td>23</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.0</td>
      <td>David Bowie</td>
      <td>4</td>
      <td>9</td>
      <td>0</td>
      <td>0</td>
      <td>113</td>
      <td>1</td>
      <td>47</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5.0</td>
      <td>Led Zeppelin</td>
      <td>5</td>
      <td>8</td>
      <td>0</td>
      <td>0</td>
      <td>16</td>
      <td>6</td>
      <td>0</td>
      <td>0</td>
      <td>252</td>
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
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>995</th>
      <td>996.0</td>
      <td>The Sundays</td>
      <td>764</td>
      <td>1369</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>513</td>
      <td>238</td>
      <td>0</td>
    </tr>
    <tr>
      <th>996</th>
      <td>997.0</td>
      <td>Herbert</td>
      <td>738</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>439</td>
      <td>184</td>
    </tr>
    <tr>
      <th>997</th>
      <td>998.0</td>
      <td>Stephen Stills</td>
      <td>739</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>249</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>998</th>
      <td>999.0</td>
      <td>Mazzy Star</td>
      <td>970</td>
      <td>895</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>231</td>
      <td>0</td>
    </tr>
    <tr>
      <th>999</th>
      <td>1000.0</td>
      <td>Blind Lemon Jefferson</td>
      <td>0</td>
      <td>533</td>
      <td>28</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>1000 rows × 11 columns</p>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-cdf46a80-bd01-4af2-bb29-eedf1d711c34')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-cdf46a80-bd01-4af2-bb29-eedf1d711c34 button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-cdf46a80-bd01-4af2-bb29-eedf1d711c34');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">df_alltime</span><span class="o">.</span><span class="n">dtypes</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>Ranking    float64
Artist      object
Albums      object
Songs       object
1900-49     object
50s         object
60s         object
70s         object
80s         object
90s         object
00s         object
dtype: object</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Since the counts of albums, hit songs, and songs by decade are recognized as objects, we will convert them to integers.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"Albums"</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"Albums"</span><span class="p">])</span>
<span class="n">df_alltime</span><span class="p">[</span><span class="s2">"Songs"</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"Songs"</span><span class="p">])</span>
<span class="n">df_alltime</span><span class="p">[</span><span class="s2">"1900-49"</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"1900-49"</span><span class="p">])</span>
<span class="n">df_alltime</span><span class="p">[</span><span class="s2">"50s"</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"50s"</span><span class="p">])</span>
<span class="n">df_alltime</span><span class="p">[</span><span class="s2">"60s"</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"60s"</span><span class="p">])</span>
<span class="n">df_alltime</span><span class="p">[</span><span class="s2">"70s"</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"70s"</span><span class="p">])</span>
<span class="n">df_alltime</span><span class="p">[</span><span class="s2">"80s"</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"80s"</span><span class="p">])</span>
<span class="n">df_alltime</span><span class="p">[</span><span class="s2">"90s"</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"90s"</span><span class="p">])</span>
<span class="n">df_alltime</span><span class="p">[</span><span class="s2">"00s"</span><span class="p">]</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">to_numeric</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"00s"</span><span class="p">])</span>
<span class="n">df_alltime</span><span class="o">.</span><span class="n">dtypes</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>Ranking    float64
Artist      object
Albums       int64
Songs        int64
1900-49      int64
50s          int64
60s          int64
70s          int64
80s          int64
90s          int64
00s          int64
dtype: object</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h4 id="Analyzing-Top-1000-Data">Analyzing Top 1000 Data<a class="anchor-link" href="#Analyzing-Top-1000-Data">&#182;</a></h4><p>Now, let's look at the distribution of song releases for the artists in the top 1000.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">features</span> <span class="o">=</span> <span class="p">[</span><span class="s2">"1900-49"</span><span class="p">,</span> <span class="s2">"50s"</span><span class="p">,</span> <span class="s2">"60s"</span><span class="p">,</span> <span class="s2">"70s"</span><span class="p">,</span> <span class="s2">"80s"</span><span class="p">,</span> <span class="s2">"90s"</span><span class="p">,</span> <span class="s2">"00s"</span><span class="p">]</span>
<span class="n">plt</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">features</span><span class="p">,</span> <span class="n">df_alltime</span><span class="p">[</span><span class="n">features</span><span class="p">]</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">0</span><span class="p">))</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">"Distribution of Critics' Favorite 1000 Artists Over Time"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">"Time Period"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">"Number of Artists"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
class="
jp-needs-light-background
"
>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s2">"Mean Rankings"</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"1900-49: "</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"1900-49"</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">][</span><span class="s2">"Ranking"</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()))</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"50s: "</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"50s"</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">][</span><span class="s2">"Ranking"</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()))</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"60s: "</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"60s"</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">][</span><span class="s2">"Ranking"</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()))</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"70s: "</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"70s"</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">][</span><span class="s2">"Ranking"</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()))</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"80s: "</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"80s"</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">][</span><span class="s2">"Ranking"</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()))</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"90s: "</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"90s"</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">][</span><span class="s2">"Ranking"</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()))</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">"00s: "</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">[</span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"00s"</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">][</span><span class="s2">"Ranking"</span><span class="p">]</span><span class="o">.</span><span class="n">mean</span><span class="p">()))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre>Mean Rankings
1900-49: 575.9444444444445
50s: 488.0990990990991
60s: 434.8884462151394
70s: 378.9563758389262
80s: 436.26027397260276
90s: 451.1048951048951
00s: 458.73762376237624
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>The bar graph shows that the artists on the top 1000 list primarily made music in the 70s, then the 80s, then the 90s. The means of the rankings for each time period demonstrate that on average, critics ranked artists who made music from 1900-49 the highest, followed by the 50s, then the 00s.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="YouGov-vs.-Critics'-Top-1000"><strong>YouGov vs. Critics' Top 1000</strong><a class="anchor-link" href="#YouGov-vs.-Critics'-Top-1000">&#182;</a></h3>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We will visualize the correlation between critics' ratings and which artists millenials have heard of.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">df_alltime</span><span class="p">[</span><span class="s2">"Name"</span><span class="p">]</span> <span class="o">=</span> <span class="n">df_alltime</span><span class="p">[</span><span class="s2">"Artist"</span><span class="p">]</span>
<span class="n">df_yougov_top1000</span> <span class="o">=</span> <span class="n">df_yougov</span><span class="o">.</span><span class="n">merge</span><span class="p">(</span><span class="n">df_alltime</span><span class="p">,</span> <span class="n">on</span><span class="o">=</span><span class="p">[</span><span class="s2">"Name"</span><span class="p">,</span> <span class="s2">"Name"</span><span class="p">],</span> <span class="n">how</span><span class="o">=</span><span class="s2">"inner"</span><span class="p">)</span>
<span class="n">df_yougov_top1000</span> <span class="o">=</span> <span class="n">df_yougov_top1000</span><span class="o">.</span><span class="n">fillna</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
<span class="n">df_yougov_top1000</span> <span class="o">=</span> <span class="n">df_yougov_top1000</span><span class="o">.</span><span class="n">drop</span><span class="p">([</span><span class="s2">"Artist"</span><span class="p">],</span> <span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">df_yougov_top1000</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>



<div class="jp-RenderedHTMLCommon jp-RenderedHTML jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/html">

  <div id="df-7049be75-89da-4719-a7ed-b532c9a231ea">
    <div class="colab-df-container">
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
      <th>Name</th>
      <th>Fame</th>
      <th>Popularity</th>
      <th>Ranking</th>
      <th>Albums</th>
      <th>Songs</th>
      <th>1900-49</th>
      <th>50s</th>
      <th>60s</th>
      <th>70s</th>
      <th>80s</th>
      <th>90s</th>
      <th>00s</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Justin Timberlake</td>
      <td>96</td>
      <td>56</td>
      <td>644.0</td>
      <td>1316</td>
      <td>301</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>90</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Alicia Keys</td>
      <td>96</td>
      <td>64</td>
      <td>620.0</td>
      <td>699</td>
      <td>555</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>82</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Kanye West</td>
      <td>95</td>
      <td>47</td>
      <td>125.0</td>
      <td>139</td>
      <td>133</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>7</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Beyonce</td>
      <td>94</td>
      <td>55</td>
      <td>477.0</td>
      <td>0</td>
      <td>187</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Kelly Clarkson</td>
      <td>94</td>
      <td>58</td>
      <td>709.0</td>
      <td>0</td>
      <td>326</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>107</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Coldplay</td>
      <td>91</td>
      <td>53</td>
      <td>138.0</td>
      <td>145</td>
      <td>173</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>9</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Pharrell Williams</td>
      <td>90</td>
      <td>62</td>
      <td>955.0</td>
      <td>0</td>
      <td>502</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>152</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Gwen Stefani</td>
      <td>89</td>
      <td>60</td>
      <td>774.0</td>
      <td>0</td>
      <td>371</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>117</td>
    </tr>
    <tr>
      <th>8</th>
      <td>The Eagles</td>
      <td>86</td>
      <td>56</td>
      <td>91.0</td>
      <td>137</td>
      <td>73</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>27</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Gorillaz</td>
      <td>79</td>
      <td>53</td>
      <td>216.0</td>
      <td>291</td>
      <td>151</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>13</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Kings of Leon</td>
      <td>78</td>
      <td>48</td>
      <td>882.0</td>
      <td>664</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>134</td>
    </tr>
    <tr>
      <th>11</th>
      <td>The Killers</td>
      <td>78</td>
      <td>52</td>
      <td>602.0</td>
      <td>846</td>
      <td>400</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>78</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Norah Jones</td>
      <td>70</td>
      <td>44</td>
      <td>708.0</td>
      <td>590</td>
      <td>1107</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>106</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Yeah Yeah Yeahs</td>
      <td>66</td>
      <td>41</td>
      <td>317.0</td>
      <td>378</td>
      <td>278</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>28</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Jill Scott</td>
      <td>63</td>
      <td>41</td>
      <td>887.0</td>
      <td>666</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>135</td>
    </tr>
    <tr>
      <th>15</th>
      <td>The Mars Volta</td>
      <td>61</td>
      <td>38</td>
      <td>564.0</td>
      <td>413</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>71</td>
    </tr>
  </tbody>
</table>
</div>
      <button class="colab-df-convert" onclick="convertToInteractive('df-7049be75-89da-4719-a7ed-b532c9a231ea')"
              title="Convert this dataframe to an interactive table."
              style="display:none;">

  <svg xmlns="http://www.w3.org/2000/svg" height="24px"viewBox="0 0 24 24"
       width="24px">
    <path d="M0 0h24v24H0V0z" fill="none"/>
    <path d="M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z"/><path d="M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z"/>
  </svg>
      </button>

  <style>
    .colab-df-container {
      display:flex;
      flex-wrap:wrap;
      gap: 12px;
    }

    .colab-df-convert {
      background-color: #E8F0FE;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: none;
      fill: #1967D2;
      height: 32px;
      padding: 0 0 0 0;
      width: 32px;
    }

    .colab-df-convert:hover {
      background-color: #E2EBFA;
      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);
      fill: #174EA6;
    }

    [theme=dark] .colab-df-convert {
      background-color: #3B4455;
      fill: #D2E3FC;
    }

    [theme=dark] .colab-df-convert:hover {
      background-color: #434B5C;
      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);
      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));
      fill: #FFFFFF;
    }
  </style>

      <script>
        const buttonEl =
          document.querySelector('#df-7049be75-89da-4719-a7ed-b532c9a231ea button.colab-df-convert');
        buttonEl.style.display =
          google.colab.kernel.accessAllowed ? 'block' : 'none';

        async function convertToInteractive(key) {
          const element = document.querySelector('#df-7049be75-89da-4719-a7ed-b532c9a231ea');
          const dataTable =
            await google.colab.kernel.invokeFunction('convertToInteractive',
                                                     [key], {});
          if (!dataTable) return;

          const docLinkHtml = 'Like what you see? Visit the ' +
            '<a target="_blank" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'
            + ' to learn more about interactive tables.';
          element.innerHTML = '';
          dataTable['output_type'] = 'display_data';
          await google.colab.output.renderOutput(dataTable, element);
          const docLink = document.createElement('div');
          docLink.innerHTML = docLinkHtml;
          element.appendChild(docLink);
        }
      </script>
    </div>
  </div>

</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>We can see that only 18 of the top 419 artists whom millenials had heard of even made the critics' top 1000.</p>
<p>Now, for these artists who appeared in both datasets, let's analyze the correlation between position in the critics' list and the percentage of millenials who had heard of an artist.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">df_yougov_top1000</span><span class="p">[</span><span class="s2">"Ranking"</span><span class="p">]</span><span class="o">.</span><span class="n">corr</span><span class="p">(</span><span class="n">df_yougov_top1000</span><span class="p">[</span><span class="s2">"Fame"</span><span class="p">])</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>-0.15508634448155484</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">scatter</span><span class="p">(</span><span class="n">df_yougov_top1000</span><span class="p">[</span><span class="s2">"Ranking"</span><span class="p">],</span> <span class="n">df_yougov_top1000</span><span class="p">[</span><span class="s2">"Fame"</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">"Fame Among Millenials vs. Critics' Rankings"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">"Critics' Rankings"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">"Fame Among Millenials"</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
class="
jp-needs-light-background
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>As we can see from the scatterplot and low correlation, there is no relationship between critics' rankings and which artists millenials have heard of. It seems that critics' rankings are not a predictor of fame among American millenials.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="IV.-Model"><strong>IV. Model</strong><a class="anchor-link" href="#IV.-Model">&#182;</a></h1>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>In the process of analyzing multiple datasets, we have yet to find a strong predictor of whether American millenials have heard of musical artists. Therefore, we are looking back to our Spotify Global Weekly data to see if certain countries' streams are a better predictor than others.</p>
<p>We want to know which countries' streams have the greatest and least predictive power for whether millenials have heard of an artist. We decided to fit a Random Forest Regressor to data from the Spotify Global Weekly and YouGov datasets. Random Forest for regression is similar to k-Nearest Neighbors, but it has a built-in "feature importances" attribute. This allows us to identify the countries whose streams are the best predictors of fame among millenials.</p>
<p>Although we know that the predictive power of streams in the U.S. is low, we hypothesize that it will still be the best predictor out of any country's streams. We think that the next-best predictors will be other English-speaking countries such as Great Britain and Australia.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Define features and output variable</span>
<span class="n">X</span> <span class="o">=</span> <span class="n">df_spotify_yougov</span><span class="p">[</span><span class="n">countries</span><span class="p">]</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df_spotify_yougov</span><span class="p">[</span><span class="s2">"Fame"</span><span class="p">]</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell jp-mod-noOutputs  ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">RandomForestRegressor</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">cross_val_score</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">GridSearchCV</span>
<span class="kn">from</span> <span class="nn">sklearn.preprocessing</span> <span class="kn">import</span> <span class="n">MinMaxScaler</span>

<span class="c1"># Use GridSearchCV to find the best parameters for our model</span>
<span class="n">gsc</span> <span class="o">=</span> <span class="n">GridSearchCV</span><span class="p">(</span><span class="n">estimator</span><span class="o">=</span><span class="n">RandomForestRegressor</span><span class="p">(</span><span class="n">random_state</span><span class="o">=</span><span class="mi">0</span><span class="p">),</span>
                   <span class="n">param_grid</span><span class="o">=</span><span class="p">{</span><span class="s2">"max_depth"</span><span class="p">:</span> <span class="p">(</span><span class="mi">2</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">10</span><span class="p">,</span><span class="mi">20</span><span class="p">,</span><span class="mi">25</span><span class="p">,</span><span class="mi">30</span><span class="p">,</span><span class="mi">35</span><span class="p">,</span><span class="mi">40</span><span class="p">),</span>
                               <span class="s2">"n_estimators"</span><span class="p">:</span> <span class="p">(</span><span class="mi">10</span><span class="p">,</span><span class="mi">20</span><span class="p">,</span><span class="mi">50</span><span class="p">,</span><span class="mi">100</span><span class="p">,</span><span class="mi">200</span><span class="p">,</span><span class="mi">225</span><span class="p">,</span><span class="mi">250</span><span class="p">,</span><span class="mi">275</span><span class="p">,</span><span class="mi">300</span><span class="p">,</span><span class="mi">325</span><span class="p">)},</span>
                   <span class="n">cv</span><span class="o">=</span><span class="mi">5</span><span class="p">,</span> <span class="n">scoring</span><span class="o">=</span><span class="s2">"neg_mean_squared_error"</span><span class="p">,</span> <span class="n">verbose</span><span class="o">=</span><span class="mi">0</span><span class="p">,</span> <span class="n">n_jobs</span><span class="o">=-</span><span class="mi">1</span><span class="p">)</span>
<span class="n">gsc_result</span> <span class="o">=</span> <span class="n">gsc</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X</span><span class="p">,</span> <span class="n">y</span><span class="p">)</span>
<span class="n">best_params</span> <span class="o">=</span> <span class="n">gsc_result</span><span class="o">.</span><span class="n">best_params_</span>
</pre></div>

     </div>
</div>
</div>
</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Output mean cross-validated score of the best model</span>
<span class="n">np</span><span class="o">.</span><span class="n">sqrt</span><span class="p">(</span><span class="o">-</span><span class="n">gsc_result</span><span class="o">.</span><span class="n">best_score_</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>23.24697771773195</pre>
</div>

</div>

</div>

</div>

</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="c1"># Instantiate new RandomForestRegressor with best parameters</span>
<span class="n">rnd</span> <span class="o">=</span> <span class="n">RandomForestRegressor</span><span class="p">(</span><span class="n">n_estimators</span><span class="o">=</span><span class="n">best_params</span><span class="p">[</span><span class="s2">"n_estimators"</span><span class="p">],</span>
                            <span class="n">max_depth</span><span class="o">=</span><span class="n">best_params</span><span class="p">[</span><span class="s2">"max_depth"</span><span class="p">],</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">0</span><span class="p">)</span>
<span class="n">rnd</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X</span><span class="p">,</span> <span class="n">y</span><span class="p">)</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt">Out[&nbsp;]:</div>




<div class="jp-RenderedText jp-OutputArea-output jp-OutputArea-executeResult" data-mime-type="text/plain">
<pre>RandomForestRegressor(max_depth=2, n_estimators=200, random_state=0)</pre>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Now, we can get the feature importances, which demonstrate which countries' streams had the greatest predictive power for fame among millenials.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">importances</span> <span class="o">=</span> <span class="n">rnd</span><span class="o">.</span><span class="n">feature_importances_</span>
<span class="n">sorted_indices</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">argsort</span><span class="p">(</span><span class="n">importances</span><span class="p">)[::</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
<span class="k">for</span> <span class="n">f</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">X</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">]):</span>
  <span class="nb">print</span><span class="p">(</span><span class="s2">"</span><span class="si">%2d</span><span class="s2">) </span><span class="si">%-*s</span><span class="s2"> </span><span class="si">%f</span><span class="s2">"</span> <span class="o">%</span> <span class="p">(</span><span class="n">f</span> <span class="o">+</span> <span class="mi">1</span><span class="p">,</span> <span class="mi">30</span><span class="p">,</span>
                            <span class="n">countries</span><span class="p">[</span><span class="n">sorted_indices</span><span class="p">[</span><span class="n">f</span><span class="p">]],</span>
                            <span class="n">importances</span><span class="p">[</span><span class="n">sorted_indices</span><span class="p">[</span><span class="n">f</span><span class="p">]]))</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>


<div class="jp-RenderedText jp-OutputArea-output" data-mime-type="text/plain">
<pre> 1) au                             0.504476
 2) mt                             0.286378
 3) ae                             0.040183
 4) nz                             0.029880
 5) za                             0.025249
 6) sg                             0.012368
 7) kr                             0.011880
 8) tw                             0.011831
 9) ca                             0.010154
10) my                             0.010001
11) ph                             0.009994
12) us                             0.009079
13) id                             0.007257
14) lv                             0.006899
15) gb                             0.004131
16) in                             0.003478
17) nl                             0.003193
18) ee                             0.002091
19) lt                             0.001883
20) sa                             0.001473
21) sk                             0.001374
22) ie                             0.001041
23) br                             0.000967
24) hk                             0.000847
25) de                             0.000817
26) se                             0.000785
27) mx                             0.000543
28) ni                             0.000469
29) hn                             0.000420
30) bo                             0.000331
31) ch                             0.000279
32) ad                             0.000250
33) at                             0.000000
34) sv                             0.000000
35) ar                             0.000000
36) eg                             0.000000
37) ec                             0.000000
38) do                             0.000000
39) fi                             0.000000
40) dk                             0.000000
41) cz                             0.000000
42) be                             0.000000
43) cy                             0.000000
44) bg                             0.000000
45) cl                             0.000000
46) cr                             0.000000
47) co                             0.000000
48) vn                             0.000000
49) fr                             0.000000
50) py                             0.000000
51) ua                             0.000000
52) tr                             0.000000
53) th                             0.000000
54) es                             0.000000
55) ru                             0.000000
56) ro                             0.000000
57) pt                             0.000000
58) pl                             0.000000
59) pe                             0.000000
60) pa                             0.000000
61) gr                             0.000000
62) no                             0.000000
63) ma                             0.000000
64) lu                             0.000000
65) jp                             0.000000
66) uy                             0.000000
67) il                             0.000000
68) is                             0.000000
69) hu                             0.000000
70) gt                             0.000000
71) it                             0.000000
</pre>
</div>
</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Let's graph the feature importances to visualize the relative impact of each feature.</p>

</div>
</div>
</div>
</div><div class="jp-Cell jp-CodeCell jp-Notebook-cell   ">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea">
<div class="jp-InputPrompt jp-InputArea-prompt">In&nbsp;[&nbsp;]:</div>
<div class="jp-CodeMirrorEditor jp-Editor jp-InputArea-editor" data-type="inline">
     <div class="CodeMirror cm-s-jupyter">
<div class=" highlight hl-python"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">'Feature Importances'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="n">X</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">]),</span> <span class="n">importances</span><span class="p">[</span><span class="n">sorted_indices</span><span class="p">],</span> <span class="n">align</span><span class="o">=</span><span class="s1">'center'</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xticks</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="n">X</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">1</span><span class="p">]),</span> <span class="n">X</span><span class="o">.</span><span class="n">columns</span><span class="p">[</span><span class="n">sorted_indices</span><span class="p">],</span> <span class="n">rotation</span><span class="o">=</span><span class="mi">90</span><span class="p">,</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">7</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">tight_layout</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

     </div>
</div>
</div>
</div>

<div class="jp-Cell-outputWrapper">
<div class="jp-Collapser jp-OutputCollapser jp-Cell-outputCollapser">
</div>


<div class="jp-OutputArea jp-Cell-outputArea">

<div class="jp-OutputArea-child">


    <div class="jp-OutputPrompt jp-OutputArea-prompt"></div>




<div class="jp-RenderedImage jp-OutputArea-output ">
<img src="data:image/png;base64,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
"
class="
jp-needs-light-background
"
>
</div>

</div>

</div>

</div>

</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>The best predictors are:</p>
<ol>
<li>Malta</li>
<li>Australia</li>
<li>The UAE</li>
<li>Singapore</li>
<li>The USA</li>
<li>Canada</li>
<li>South Africa</li>
<li>Malaysia</li>
<li>New Zealand</li>
<li>Taiwan</li>
</ol>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h1 id="V.-Conclusions"><strong>V. Conclusions</strong><a class="anchor-link" href="#V.-Conclusions">&#182;</a></h1>
</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<p>Throughout our analysis, our main dataset for comparison was the YouGov poll results including what percentage of American millenials had heard of contemporary music artists. We also looked at global Spotify weekly charts, as well as critics' rankings of the top 1000 artists of all time. We saw that critics' rankings did not significantly correlate with fame among millenials. We ruled out critics' rankings as a predictor of fame among millenials. We found the same result for the relationship between Spotify streams in the U.S. and fame among millenials, so we dug deeper into the streams by country.</p>
<p>We decided to look to the Spotify global weekly data to figure out which country's chart was the best predictor of fame among millenials. While 4 of the top 10 countries are English-speaking, which falls in line with our hypothesis, the US was only weighted as 1.2793% of the model. The sum of all the English-speaking countries' weights made up less than 40% of the model. Malta was weighted at 49.3714%, making them the most heavily-weighted country by far, with only Australia coming anywhere close.</p>
<p>We can conclude that the best predictor of whether American millenials have heard of an artist is their popularity in Malta.</p>

</div>
</div>
</div>
</div>
<div class="jp-Cell jp-MarkdownCell jp-Notebook-cell">
<div class="jp-Cell-inputWrapper">
<div class="jp-Collapser jp-InputCollapser jp-Cell-inputCollapser">
</div>
<div class="jp-InputArea jp-Cell-inputArea"><div class="jp-InputPrompt jp-InputArea-prompt">
</div><div class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput " data-mime-type="text/markdown">
<h3 id="Limitations"><strong>Limitations</strong><a class="anchor-link" href="#Limitations">&#182;</a></h3><p>The YouGov poll couldn't have asked each millenial about every artist in existence. We only have data on the fame among millenials of 419 artists. There are likely artists whom some millenials have heard of who didn't make the list. Artists who weren't on the list were given a millenial fame score of 0 in our analysis, based on the assumption that their fame score would have otherwise been low. This missing data could introduce bias in our model.</p>
<p>After merging with the YouGov data, we also filled missing streams in the Spotify data with 0. This means that if an artist was number 201 in a country, their streams are counted as 0. This could also introduce bias, as only the top 200 in each country are represented.</p>
<p>Feature importances also do not give us any information about the strength of the actual model, just the weights of the features relative to each other. The RMSE of our model is 26.07536, which does seem high. Overall, this indicates that our model lacks predictive power. Within the model, however, we are still able to tease out which countries' streams had the most impact.</p>

</div>
</div>
</div>
</div>
</body>







</html>
