# 1. Javascript Into

## Javascript History
- Javascript(JS) was created by Netscape and in 1996 they submitted the javascript code to ECMA (European Computer Manufacturer Association) which was a Non-Profit organization.
- Later they launched different version under ECMAScript:
	- 1997 - ECMAScript 1
	- 1998 - ECMAScript 2
	- 1999 - ECMAScript 3
	- 1999 - ECMAScript 3
	- ECMAScript 4 was not launched.
	- 2009 - ECMAScript 5
	- 2011 - ECMAScript 5.1
	- 2015 - ECMAScript 2015 (ES6)	-- major update
	- 2016 - ECMAScript 2016 (ES7)	-- minor update
	- 2017 - ECMAScript 2017 (ES8)	-- minor update
	- 2018 - ECMAScript 2018 (ES9)	-- minor update

## “let” and “const”

| var | let | const |
|----------|----------|----------|
| It is function scoped.    | It is block scoped.     | It is block scoped.     |
| can be declared without initialization.    | can be declared without initialization.     | value must be assigned when declared   |
| Gets hoisted to the top of its function, initialized as `undefined`.    | Hoisted but not initialized; accessing before declaration causes a **ReferenceError**.     | Hoisted but not initialized; accessing before declaration causes a **ReferenceError**.    |
| Can reassign? ✅ Yes <br> Can redeclare? ✅ Yes (even in the same scope).    | Can reassign? ✅ Yes <br> Can redeclare? ❌ No (in the same scope).     | Can reassign? ❌ No <br> Can redeclare? ❌ No.  |
- ⚠️ Avoid `var` in modern JS—`let` and `const` are safer and more predictable.
