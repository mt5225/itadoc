.. _json-label:

JSON
======

The body of an HTTP request or response message is a document written in JavaScript Object Notation (JSON), which is a lightweight, text-based data interchange format. Although it has its roots in JavaScript, JSON is language independent and uses simple data structures. You can learn more about JSON and find JSON parsers for many languages at .. JSON.org: http://json.org . JSON parsers provide serialization and deserialization methods that make encoding and decoding the messages easier.


Elements of JSON documents
^^^^^^^^^^^^^^^^^^^^^^^^^^^

A JSON document represents one serialized object or array that is delineated as follows:
  - An object is a comma-separated series of name-value pairs enclosed in braces.
  - An array is a comma-separated series of values enclosed in brackets.
JSON documents conform to the following rules:
  - A name-value pair consists of a name enclosed in quotation marks separated from the corresponding value by a colon. For example, "identifier" : 25 is a name-value pair. Whitespace between the name and value is insignificant.
  - A value can be a string, a number, an array, an object, or one of the following literal values: `true`, `false`, or `null`.
  - Strings must be enclosed in quotation marks.
  - Objects and arrays can be nested.
