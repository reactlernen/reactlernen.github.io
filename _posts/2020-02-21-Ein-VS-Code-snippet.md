---
layout: post
title:  "Ein React Snippet für Visual Studio Code"
date:   2020-02-21 15:12:42 +0100
categories: vs-code tip react
---
Bei React dreht sich alles um die _Komponente_. Als Anwendungsentwickler müssen wir in der Regel sehr viele Komponenten entwickeln. Sofern man _TypeScript_ im Einsatz hat, kommt man nur schwer drumherum für jede Komponente mühselig viel sog. _Boilerplate code_ zu schreiben. 

Beim Entwickeln von React Anwendungen in _Visual Studio Code_ gibt es hierfür eine elegante Abhilfe in Form von [Snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets).

Code-Snippets sind Templates, die die Eingabe von sich wiederholenden Code-Mustern, wie z.B. Schleifen oder Conditional-Statements, erleichtern.
In Visual Studio Code erscheinen Snippets in IntelliSense (⌃Space) gemischt mit anderen Vorschlägen.

```json
{
  "React functional component": {
		"prefix": "cpt",
		"body": [
			"import React, { ReactElement } from 'react';",
			"",
			"export interface ${1:name}Props {",
			" children: ReactElement;"
			"}",
			"",
			"const ${1:name}: React.FC<${1:name}Props> = ({ children }: ${1:name}Props) => {",
			"	return (",
			"		<div>",
			"			Hello Foo",
			"			{children}",
			"		</div>",
			"	);",
			"};",
			"",
			"export default ${1:name};",
			""
		],
		"description": "Create a new functional component."
	}
}
```
