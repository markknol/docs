---
title: Left Curly
keywords: left, curly
toc: false
---

Checks for the placement of left curly braces (`{`) for code blocks. The policy to verify is specified using the property `option`.

### Configuration

```json
{
	"type": "LeftCurly",
	"props": {
		"severity": "WARNING",
		"option": "eol",
		"ignoreEmptySingleline": "true",
		"tokens": [
			"CLASS_DEF",           // class definition     - class Test {}
			"ENUM_DEF",            // enum definition      - enum Test {}
			"ABSTRACT_DEF",        // abstract definition  - abstract Test {}
			"TYPEDEF_DEF",         // typdef definition    - typedef Test = {}
			"INTERFACE_DEF",       // interface definition - interface Test {}
			"OBJECT_DECL",         // object declaration   - { x: 0, y: 0, z: 0}
			"FUNCTION",            // function body        - function test () {}
			"FOR",                 // for body             - for (i in 0..10) {}
			"IF",                  // if / else body       - if (test) {} else {}
			"WHILE",               // while body           - while (test) {}
			"SWITCH",              // switch / case body   - switch (test) { case: {} default: {} }
			"TRY",                 // try body             - try {}
			"CATCH",               // catch body           - catch (e:Dynamic) {}
			"REIFICATION",         // macro reification    - $i{}
			"ARRAY_COMPREHENSION"  // array comprehension  - [for (i in 0...10) {i * 2}]
		]
	}
}
```

| Option | Description |
| ------ | ------------|
| `eol`  | end of line |
| `nl`   | new line |
| `nlow` | new line on wrap |

<br>

When `ignoreEmptySingleline` is to `true` (default) empty blocks in a single line will not produce a warning.

### Valid

If option was set to `eol`, with `ignoreEmptySingleline` set to `true`

```java
public function new() {
	super();
}
public function donothing() {}
```

### Invalid

If option was set to `eol`

```java
public function new()
{
	super();
}
```

`Left curly should be at EOL (only linebreak or comment after curly)`

<br>

With `ignoreEmptySingleline` set to `false`

```java
	public function donothing() {}
```

{{site.data.alerts.error}} Left curly should be at EOL (only linebreak or comment after curly) {{site.data.alerts.end}}