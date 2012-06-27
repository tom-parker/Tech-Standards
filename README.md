#Mobile first builds

Basic setup for a document / CSS structure for a mobile first build pulled from http://adactio.com/journal/4494/

* Provide base stylesheet (global.css) that includes the styles required for the mobile build
* Include an additional stylesheet (layout.css) with a media query so that the floated layout / widths / desktop styles only kick in at desktop screen widths
* As versions of IE < 9 don't support media queries, it's necessary to include the layout.css file again in an IE conditional comment so that IE will get the proper desktop styles
* In addition to this it might also be necessary to include a !IEMobile switch in the conditional comment to force Windows phone 7 not to download the layout.css file

```html
	<link rel="stylesheet" href="/css/global.css" media="all">
	<link rel="stylesheet" href="/css/layout.css" media="all and (min-width: 30em)">
	<!--[if (lt IE 9)&(!IEMobile)]>
	<link rel="stylesheet" href="/css/layout.css" media="all">
	<![endif]-->
```
