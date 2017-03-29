<?xml version="1.0"?>
<?xml-stylesheet type="text/xsl" href="../entries2html.xsl" ?>
<entry type="method" name="notDeepEqual">
	<title>notDeepEqual()</title>
	<signature>
		<argument name="actual" type="Object">
			<desc>Object or Expression being tested</desc>
		</argument>
		<argument name="expected" type="Object">
			<desc>Known comparison value</desc>
		</argument>
		<argument name="message" type="String" optional="true">
			<desc>A short description of the assertion</desc>
		</argument>
	</signature>
	<desc>
		An inverted deep recursive comparison, working on primitive types, arrays, objects, regular expressions, dates and functions.
	</desc>
	<longdesc>
		<p>The <code>notDeepEqual()</code> assertion can be used just like <code>equal()</code> when comparing the value of objects, such that <code>{ key: value }</code> is equal to <code>{ key: value }</code>. For non-scalar values, identity will be disregarded by <code>notDeepEqual</code>.</p>
		<p><a href="/deepEqual/"><code>deepEqual()</code></a> can be used to explicitly test deep, strict equality.</p>
	</longdesc>
	<example>
		<desc>Compare the value of two objects.</desc>
<code><![CDATA[
QUnit.test( "notDeepEqual test", function( assert ) {
	var obj = { foo: "bar" };

	assert.notDeepEqual( obj, { foo: "bla" }, "Different object, same key, different value, not equal" );
});
]]></code>
	</example>
	<category slug="assert"/>
</entry>
